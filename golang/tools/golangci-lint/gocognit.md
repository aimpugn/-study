# gocognit

- [gocognit](#gocognit)
    - [gocognit란?](#gocognit란)
    - [설치 방법](#설치-방법)
    - [gocognit의 작동 방식](#gocognit의-작동-방식)
    - [사용 방법](#사용-방법)
    - [출력 형식](#출력-형식)

## gocognit란?

`gocognit`는 Go 소스 코드 내의 함수와 메서드의 인지 복잡성을 계산하는 도구입니다.
인지 복잡성은 코드를 이해하는 데 필요한 인지적 노력을 수치화한 것으로, 코드의 복잡성을 줄이고 가독성을 높이는 데 도움을 줍니다.

## 설치 방법

`gocognit`를 설치하려면, Go가 설치된 환경에서 다음 명령을 실행합니다:

```bash
go install github.com/uudashr/gocognit/cmd/gocognit@latest
```

## gocognit의 작동 방식

`gocognit`는 소스 코드 내 함수의 인지 복잡도를 측정하기 위해 다음과 같은 기준을 사용합니다:

1. **조건문**: `if`, `else if`, `switch` 등의 조건문은 인지 복잡도를 증가시킵니다. 각 조건 분기는 복잡도를 1씩 증가시킵니다.

2. **루프**: `for`, `while`, `do-while` 등의 반복문은 복잡도를 증가시키는 요소로 간주됩니다. 반복문의 중첩도 복잡도를 추가로 증가시킬 수 있습니다.

3. **중첩된 구조**: 함수 내에서 다중 중첩된 구조(예: 중첩된 `if`문 안에 또 다른 `if`문)는 복잡도를 크게 증가시킬 수 있습니다. 중첩된 각 수준은 추가 복잡도를 부여합니다.

4. **점프 문**: `break`, `continue`, `goto`와 같은 점프 문은 복잡성을 증가시킵니다.

5. **복잡한 표현식**: 복잡한 논리적 또는 비교 표현식도 복잡도를 증가시킬 수 있습니다.

`gocognit`는 이러한 요소들을 고려하여 각 함수의 복잡도 점수를 계산하고, 이 점수를 통해 코드의 특정 부분이 얼마나 복잡한지를 수치적으로 제시합니다. 이 수치는 함수가 얼마나 많은 '인지 부하'를 가지고 있는지를 나타내며, 높은 수치는 리팩토링을 통해 복잡도를 감소시킬 필요가 있음을 암시합니다.

## 사용 방법

`gocognit`는 명령줄 인터페이스를 통해 사용할 수 있으며, 다음과 같은 명령어 옵션을 제공합니다:

- `gocognit .`: 현재 디렉토리의 모든 Go 파일의 인지 복잡성을 계산합니다.
- `gocognit main.go`: 특정 파일의 인지 복잡성을 계산합니다.
- `gocognit -top 10 src/`: 가장 복잡한 상위 10개 함수를 보여줍니다.
- `gocognit -over 25 docker`: 인지 복잡성이 25를 초과하는 함수만 보여줍니다.
- `gocognit -avg .`: 평균 인지 복잡성을 계산합니다.
- `gocognit -ignore "_test|testdata" .`: 특정 패턴을 무시하고 인지 복잡성을 계산합니다.

## 출력 형식

`gocognit`의 기본 출력 형식은 다음과 같습니다:

```bash
<complexity> <package> <function> <file:row:column>
```

이 형식은 각 함수의 인지 복잡성 점수, 패키지 이름, 함수 이름, 그리고 위치(파일명과 행, 열 번호)를 보여줍니다.