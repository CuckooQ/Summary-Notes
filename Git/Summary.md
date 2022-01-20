# GIT

<br>

## 목차

#### [1. 정의](#정의)

#### [2. Github](#Github)

#### [3. State](#State)

#### [4. Branch](#Branch)

#### [5. Repository](#Repository)

#### [6. File](#File)

- .git
- .gitignore

#### [7. Word](#Word)

- Origin
- Head
- Commit
- Tag
- Push
- Clone
- Pull
- Fetch

#### [8. Command](#Command)

- 생성
- 원격 저장소 연결
- 파일 추적 추가
- 커밋
- 커밋 이력
- 커밋 선택 이력 보기
- 커밋 리셋
- 커밋 되돌리기
- 푸시
- 클론
- 풀
- 원격 브랜치 목록
- 원격 브랜치 선택
- 원격 브랜치 생성 & 선택
- 원격 브랜치 삭제
- 브랜치 병합

<br>

---

<br>

## 정의

- 분산 버전 관리 시스템

<br>

## Github

- Git을 사용한 원격 저장소 제공 서비스

<br>

## State

### Updated

- File Update

### Staged

- Git Add

### Commited

- Git Commit

<br>

## Branch

### Master

- 최상위 브랜치
- 배포 가능한 상태로만 관리

### Develop

- 다음 출시 버전 개발 브랜치
- 모든 기능과 버그가 수정되어 배포 가능한 상태가 된 경우 Release 브랜치에 병합

### Feature

- 기능 개발이나 버그 수정 브랜치

### Release

- 배포 브랜치
- 배포를 위한 버그 수정과 문서 추가의 작업 진행
- 배포 후에 Master와 Develop브랜치에 병합

### Hotfix

- 배포한 버전의 긴급 수정 브랜치
- Master 브랜치에서 분기
- Master와 Develop 브랜치로 병합

<br>

## Repository

### Remote Repository

- 공유하고 관리되는 저장소 전용 서버

### Local Repository

- 원격 저장소에서 가져와서 저장되는 개인 PC 저장소

<br>

## File

### .git

- 버전 제어에 필요한 모든 정보가 포함된 폴더

### .gitignore

- 원격 저장소로 업로드하지 않을 파일들을 명시하는 파일

<br>

## Word

### Origin

- 기본 설정된 원격 주소에 붙는 별명

### Head

- 현재 작업 중인 브랜치를 가리키는 포인터

### Commit

- 파일이나 폴더의 변경사항을 기록하는 동작

### Tag

- 커밋에 달아주는 별명

### Push

- 원격 저장소로 변경된 파일이나 폴더를 업로드하는 동작

### Clone

- 원격 저장소의 내용을 로컬 저장소로 그대로 다운로드하는 동작

### Pull

- 원격 저장소의 내용을 로컬 저장소의 내용에 병합하는 동작

### Fetch

- 원격 저장소의 내용을 로컬 저장소로 가져오지만 병합은 안하는 동작

<br>

## Command

### 생성

- git init

### 원격 저장소 연결

- git remote add origin 'address'

### 파일 추적 추가

- git add 'directories'

### 커밋

- git commit -m "message"

### 커밋 이력

- git log -p

### 커밋 선택 이력 보기

- git show 'commit ID'

### 커밋 리셋

- git reset --hard 'commit ID'
- 이전까지의 커밋 이력을 남기지 않고 완전히 되돌림
- 협업의 경우 지양

### 커밋 되돌리기

- git revert 'commit ID'
- 이전까지의 커밋 이력을 남기고 되돌리는 이력도 남기는 되돌림

### 푸시

- git push 'local branch' 'remote branch'

### 클론

- git clone 'address'

### 풀

- git pull 'local branch' 'remote branch'

### 원격 브랜치 목록

- git branch -a

### 원격 브랜치 선택

- git checkout 'remote branch'

### 원격 브랜치 생성 & 선택

- git checkout -b 'remote branch'  
  git push origin 'remote branch'

### 원격 브랜치 삭제

- git push origin --delete 'remote branch'

### 브랜치 병합

- git merge 'branch'

<br>
