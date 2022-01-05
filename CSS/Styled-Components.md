# Styled Components

<br>

## 목차

#### [1. Best Practices](#Best-Practices)

- CSS Variables
- Single Source Of Styles
- AS 활용
- 스타일 파일의 분리

<br>

## Best Practices

### CSS Variables 활용

#### 스타일링 props를 갖는 컴포넌트

- ```
  function Component ({ props1, props2, children }) {
    return (
      <Wrapper props1={props1} props2={props2}>
        {children}
      </Wrapper>
    )
  }
  const Wrapper = styled.div`
    property1: ${props => props.props1};
    property2: ${props => props.props2};
  `;
  ```

  - props 값의 변경이 있는 경우, 클래스를 다시 생성하고 주입하는 동작이 발생해 성능 저하 발생

- Using CSS Variables
  - ```
    function Component({props1, props2, children}) {
      return (
        <Wrapper
          style={{
            "--props1": props1,
            "--props2": props2,
          }}
        >
          {children}
        </Wrapper>
      )
    }
    const Wrapper = styled.div`
      props1: var(--props1, defaultValue);
      props2: var(--props2, defaultValue);
    `;
    ```

### Single Source Of Styles

#### 어떤 컴포넌트를 스타일이 다르게 적용해서 사용하는 경우

- ```
  // Component1.jsx
  const Component1 = style.tagName1`
    props1: var(--props1);
    props2: var(--props2);
  `;
  export default Component1;

  // Component2.jsx
  const Component2 = ({children}) => {
    return (
      <Wrapper>
        {children}
      </Wrapper>
    );
  }
  const Wrapper = styled.tagName2`
    tagName1 {
      props1: var(--props3);
      props2: var(--props4);
    }
  `;
  export default Component2;
  ```

- More Better Case Using Embedding

  ```
  // Component2.jsx
  import Component1 from ".../Component1";
  const Component2 = ({children}) => {
    return (
      <Wrapper>
        {children}
      </Wrapper>
    );
  }
  const Wrapper = styled.tagName2`
    ${Component1} {
      props1: var(--props3);
      props2: var(--props4);
    }
  `;
  export default Component2;
  ```

- More More More Better Case With SSOS

  ```
  // Component2.jsx
  const Component2 = ({children}) => {
    return (
      <Wrapper>
        {children}
      </Wrapper>
    );
  }
  const Wrapper = styled.tagName2``;
  export default Component2;

  // Component1.jsx
  import {Wrapper as Component2Wrapper} from ".../Component2";
  const Component1 = styled.tagName1`
    props1: var(--props1);
    props2: var(--props2);

    ${Component2Wrapper} & {
      props1: var(--props3);
      props2: var(--props4);
    }
  `;
  export default Component1;
  ```

### AS 활용

#### Keeping Semantic HTML

- ```
  const Wrapper = styled.h2`
    ...
  `;
  funciton Header({ level, children}) {
    const tag = `h{level}`;
    return (
      <Wrapper as={tag}>
        {children}
      </Wrapper>
    );
  }
  export default Header;
  ```
- ```
  function LinkButton({href, children}) {
    const tag = typeof href === "string" ? "a" : "button";
    return (
      <Wrapper as={tag} href={href}>
        {children}
      </Wrapper>
    );
  }
  ```

### 스타일 파일의 분리

- 디렉토리 구조
  - ComponentMame/  
    \--- index.jsx  
    \--- styles.js
- 스타일 임포팅
  - ```
    // index.jsx
    import * as Styled from "./styles";
    const Component = ({..., children}) {
      return (
        <>
          <Styled.Wrapper>{...}</Styled.Wrapper>
        </>
      );
    }
    ```

<br>
