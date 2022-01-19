# React Worst Practices

<br>

## 목차

#### [1. Using Logic Inside Render](#Using-Logic-Inside-Render)

#### [2. Polluting Render method using anonymous functions](#Polluting-Render-method-using-anonymous-functions)

#### [3. Using && to conditionally Render Component](#Using-&&-to-conditionally-Render-Component)

#### [4. Nesting Ternary in Render](#Nesting-Ternary-in-Render)

#### [5. Not Sorting Props](#Not-Sorting-Props)

#### [6. Not destructuring props and state](#Not-destructuring-props-and-state)

#### [7. Not using useCallback, useMemo hooks and React.memo](#Not-using-useCallback,-useMemo-hooks-and-React.memo)

#### [8. Not Cleaning event listeners and timers](#Not-Cleaning-event-listeners-and-timers)

#### [9. Passing props one by one](#Passing-props-one-by-one)

#### [10. Using Index as a key](#Using-Index-as-a-key)

#### [11. Avoiding React Dev Tools](#Avoiding-React-Dev-Tools)

#### [12. Summary](#Summary)

<br>

---

<br>

## Using Logic Inside Render

### Bad Practice

```
const Product = (props) => {
  const {addToCart, isGuest} = props;

  return (
    <div className={addToCart ? "active" : "inactive"}>
      <div>{isGuest ? "Login" : "Checkout"}</div>
    </div>
  );
}
```

### Good Practice

```
const Product = () => {
  const {addToCart, isGuest} = props;

  const className = addToCart ? "active" : "inactive";
  const text = isGuest ? "Login" : "Checkout";

  return (
    <div className={className}>
      <div>{text}</div>
    </div>
  );
}
```

<br>

## Polluting Render method using anonymous functions

### Bad Practice

```
const Product = (props) => {
  return (
    <button
      onClick={() => {
        updateProduct();
        showPayment();
      }}
    >
      Buy
    </button>
  );
}
```

### Good Practice

```
const Product = (props) => {
  const handleBuy = () => {
    updateProduct();
    showPayment();
  }}

  return (
    <button onClick={handleBuy}>
      Buy
    </button>
  );
}
```

<br>

## Using && to conditionally Render Component

### Bad Practice

```
const Product = (props) => {
  const {showTitle} = props;

  return (
    <div>{showTitle && <h1>Mac</h1>}</div>
  );
}
```

### Good Practice

```
const Product = (props) => {
  const {showTitle} = props;

  return (
    <div>{showTitle ? <h1>Mac</h1> : null}</div>
  );
}
```

<br>

## Nesting Ternary in Render

### Bad Practice

```
const Product = (props) => {
  const {showTitle, showData} = props;

  return (
    <div>{showTitle ? <h1>Mac</h1> : showData ? <Data /> : <NoData />}</div>
  );
}
```

### Good Practice

```
const Product = (props) => {
  const {showTitle, showData} = props;

  const getContent = () => {
    if(showTitle) {
      return <h1>Mac</h1>
    } else if(showData) {
      return <Data />
    } else {
      return <NoData />
    }
  };

  return (
    <div>{getContent()}</div>
  );
}
```

<br>

## Not Sorting Props

### Bad Practice

```
<Product
  price={price}
  isGuest={isGuest}
  product={product}
  onClick={onClick}
  addToCart={addToCart}
  query={query}
/>

const Product = ({price, addToCart, query, isGuest}) => {
  return <div></div>;
}
```

### Good Practice

```
<Product
  addToCart={addToCart}
  isGuest={isGuest}
  onClick={onClick}
  price={price}
  product={product}
  query={query}
/>

const Product = ({addToCart, isGuest, price, query}) => {
  return <div></div>;
}
```

<br>

## Not Destructuring props and state

### Bad Practice

```
const Product = (props) => {
  const fetchData = () => {
    getDefaultNormalizer(props.id, props.user);
  }

  return <div>
    <div>{props.title</div>
  </div>;
}
```

### Good Practice

```
const Product = (props) => {
  const {id="", user={}, title=""} = props;

  const fetchData = () => {
    getDefaultNormalizer(id, user);
  }

  return <div>
    <div>{title</div>
  </div>;
}
```

<br>

## Not using useCallback, useMemo hooks and React.memo

### Bad Practice

```
import {useState} from "react";

const Product = (props) => {
  const {count, setCount} = useState(0);

  const handleCount = () => {
    setCount(count+1);
  }

  return (
    <div>
      <h1 onClick={handleCount}>
        Click to increase Count {count}
      </h1>
      <Watch />
    </div>
  );
}

const Watch = () => {
  console.log("watch);

  return <div>Watch</div>
}

export default Product;
```

### Good Practice

```
import {useState, memo} from "react";

const Product = (props) => {
  const {count, setCount} = useState(0);

  const handleCount = () => {
    setCount(count+1);
  }

  return (
    <div>
      <h1 onClick={handleCount}>
        Click to increase Count {count}
      </h1>
      <Watch />
    </div>
  );
}

const Watch = memo(() => {
  console.log("watch);

  return <div>Watch</div>
});

export default Product;
```

<br>

## Not Cleaning event listeners and timers

### Bad Practice

```
const Product = (props) => {
  const onDocumentClick = () => {};

  useEffect(() => {
    document.addEventListener("click", onDocumentClick);
    const timer = setTimeout(()=> {
      // ...
    }, 5000);
  }, []);

  return <div>Product</div>;
}
```

### Good Practice

```
const Product = (props) => {
  const onDocumentClick = () => {};

  useEffect(() => {
    document.addEventListener("click", onDocumentClick);
    const timer = setTimeout(()=> {
      // ...
    }, 5000);

    return () => {
      document.removeEventListener("click", onDocumentClick);
      clearTimeout(timer);
    };
  }, []);

  return <div>Product</div>;
}
```

<br>

## Passing props one by one

### Bad Practice

```
const Product = (props) => {
  const {title} = props;

  return (
    <div>
      <h1>{title}</h1>
      <Watch
        addToCart={props.addToCart}
        data={props.data}
        isGuest={props.isGuest}
      />
    </div>
  );
}
```

### Good Practice

```
const Product = (props) => {
  const {title, ...restProps} = props;

  return (
    <div>
      <h1>{title}</h1>
      <Watch {...restProps} />
    </div>
  );
}
```

<br>

## Using Index as a key

### Applicatble Case Using Index as a Key

- The list is fully static
- No Rerendering & Deletion/Addition

<br>

## Avoiding React Dev Tools

<br>

## Summary

- 비즈니스 로직과 렌더링 처리 분리
- 스타일링 분리
- if else 조건 렌더링은 조건 연산자 사용
- if elseif else... 조건 렌더링은 if 조건문 사용
- props는 알파벳순으로 정렬
- props와 state는 비구조화 할당 사용
- 메모이제이션 사용
- 이벤트와 타이머는 언마운트 과정에서 제거
- List Key 속성 값으로 ID 사용
- React Dev Tools 사용

<br>
