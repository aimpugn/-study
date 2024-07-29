# Function Complexity

- [Function Complexity](#function-complexity)
    - [사이클로매틱 복잡도(Cyclomatic Complexity)](#사이클로매틱-복잡도cyclomatic-complexity)
        - [정의](#정의)
        - [복잡도를 증가시키는 요소들](#복잡도를-증가시키는-요소들)
        - [예시1](#예시1)
        - [예시2](#예시2)
        - [결론](#결론)
    - [중요성](#중요성)
    - [복잡도 줄이는 전략](#복잡도-줄이는-전략)
    - [도구 및 자원](#도구-및-자원)
    - [사이클로매틱 복잡도 계산 방법](#사이클로매틱-복잡도-계산-방법)
    - [30 이상의 복잡도 의미](#30-이상의-복잡도-의미)
    - [복잡도 줄이는 방법](#복잡도-줄이는-방법)

## 사이클로매틱 복잡도(Cyclomatic Complexity)

사이클로매틱 복잡도는 코드의 복잡성을 수치화하여, 함수나 모듈이 얼마나 복잡한지를 나타내는 지표입니다.
이 지표는 Thomas J. McCabe가 1976년에 소개했으며, 프로그램 내의 선형적으로 독립적인 경로의 수를 측정합니다.

기본적으로, 이 지표는 결정 구조(조건문, 반복문 등)의 수를 통해 계산되며, 높은 값은 코드가 더 복잡하다는 것을 의미합니다.

소프트웨어 테스트의 필요성과 소프트웨어의 구조적 복잡성에 대한 이해를 높이기 위한 목적으로 이 개념을 도입됐습니다.

### 정의

프로그램 내의 결정 포인트(조건문, 반복문 등)의 수를 기반으로 계산되며, 이는 프로그램의 테스트 가능성과 유지 보수성에 직접적인 영향을 미칩니다.
기본적으로 $V(G) = E - N + 2P$ 라는 공식을 사용합니다.
단순화된 방식으로는 결정 포인트의 수에 1을 더한 값으로 볼 수 있다.

$$
V(G) = E - N + 2P
$$

- `E`: 프로그램 흐름 그래프의 에지 수
- `N`: 노드 수
- `P`: 연결 성분의 수

### 복잡도를 증가시키는 요소들

복잡도 계산에 영향을 미치는 다양한 "결정 포인트"에는 `if`, `for`, `while`, `case` 문과 같은 조건문과 반복문이 포함된다.
각각의 이러한 구조는 코드의 실행 경로를 분기하게 만들어 복잡성을 증가시킨다

- **조건문 (`if`, `else if`, `switch`)**: 코드의 실행 경로를 조건에 따라 분기
- **반복문 (`for`, `while`, `do-while`)**: 코드의 특정 부분을 반복 실행
- **논리 연산자 (`&&`, `||`)**: 복잡한 조건을 평가할 때 사용되며, 실행 경로의 분기를 추가할 수 있다.
- **함수 호출**: 다른 함수로의 점프는 복잡도에 직접적으로 영향을 주지 않지만, 호출된 함수 내에서의 복잡도는 전체 소프트웨어의 복잡성에 기여한다

함수 호출 자체는 사이클로매틱 복잡도를 증가시키는 결정 포인트로 간주되지 않는다.
복잡도는 해당 함수 내부의 로직 복잡성에 기반하기 때문에, 호출되는 함수의 복잡도는 호출자 함수의 복잡도에 직접적으로 더해지지 않는다.
그러나, 함수 `a`와 `b`의 복잡도가 높다는 것은 전체 소프트웨어 시스템의 복잡성을 반영할 수 있으며, 이는 유지보수성과 테스트 용이성에 영향을 줄 수 있다.

### 예시1

```go
func exampleFunction(a, b int, flag bool) int {
    result := 0 // 함수 시작 포인트. 즉, 실행 경로의 시작점. 사이클로매틱 복잡도 계산에서는
                // 함수 시작을 하나의 독립적인 경로로 간주하기 때문에, 계산 공식에 항상 기본값으로 `1`이 추가된다
    
    if flag { // 결정 포인트 1
        result += a
    } else { // 결정 포인트 2
        result += b
    }
    
    for i := 0; i < 5; i++ { // 결정 포인트 3 (for 문)
        result += i
    }
    
    switch result { // 결정 포인트 4 (switch 문)
    case 10:
        result += 1
    case 20:
        result += 2
    default:
        result += 3
    }
    
    return result
}
```

이 함수의 사이클로매틱 복잡도를 계산해보면:

- 함수 시작 포인트: `1`
- `if-else` 문: `2` (if와 else 각각의 분기)
- `for` 반복문: `1` (루프의 시작)
- `switch` 문: `3` (case 10, case 20, default 각각의 분기)

따라서, 사이클로매틱 복잡도는 `1 + 2 + 1 + 3 = 7`가 된다

### 예시2

사이클로매틱 복잡도는 코드 내의 결정 포인트(조건문, 반복문 등)에 기반하여 계산되며, 함수 내부에서 호출되는 다른 함수의 복잡도는 직접적으로 호출자 함수의 복잡도에 포함되지 않는다. 따라서, 함수 `A`가 함수 `a`와 `b`를 호출한다고 할 때, `a`와 `b` 각각의 복잡도가 `A` 함수의 복잡도에 직접적으로 더해지지는 않는다.

```go
func A() {
    a() // 함수 a 호출, 복잡도 30
    b() // 함수 b 호출, 복잡도 10
}
```

여기서 함수 `A`의 복잡도를 계산할 때는 `A` 내부의 결정 포인트만 고려된다.
`A` 함수 자체는 단순히 `a`와 `b`를 순차적으로 호출할 뿐이고, 추가적인 조건문이나 반복문이 없다면, `A`의 복잡도는 기본적으로 매우 낮다.
`A` 함수의 복잡도는 결정 포인트가 없으므로 기본값인 1로 볼 수 있으며, 여기서 호출되는 `a`와 `b` 함수의 내부 복잡도는 `A`의 복잡도 계산에 직접적으로 포함되지 않는다.

### 결론

함수 `A`의 복잡도는 `a`와 `b`를 호출하는 것만으로는 2가 아니라, 결정 포인트가 없으므로 기본적으로 1로 간주됩니다. 함수 호출은 복잡도 계산에서 직접적으로 복잡도를 증가시키지 않지만, 전체 시스템의 복잡도 관리 측면에서 호출되는 함수의 복잡도도 고려하는 것이 중요합니다. 따라서, 복잡한 로직을 가진 함수는 가능한 한 잘게 나누어 관리하여 각 함수의 복잡도를 낮추는 것이 좋습니다.

## 중요성

함수 복잡도 측정은 코드의 유지 보수성, 가독성, 그리고 테스트 용이성을 향상시키기 위해 중요합니다. 높은 복잡도는 코드의 오류 가능성을 증가시키며, 테스트와 디버깅을 어렵게 만듭니다. 따라서, 복잡도를 관리하고 적절한 수준으로 유지하는 것은 소프트웨어 개발 과정에서 매우 중요합니다.

## 복잡도 줄이는 전략

코드 복잡도를 줄이기 위한 전략:
1. 조건문 단순화
2. 코드 리팩토링
3. 함수 분리 등

이러한 전략들은 코드의 가독성을 향상시키고, 오류 가능성을 줄이며, 유지 보수를 용이하게 합니다.

## 도구 및 자원

복잡도를 측정하기 위한 다양한 도구들이 있으며, 이들을 사용하여 코드의 복잡도를 정기적으로 검사하고 관리하는 것이 좋습니다. 예를 들어, Go 언어에서는 `gocyclo`와 같은 도구를 사용하여 사이클로매틱 복잡도를 측정할 수 있습니다.

## 사이클로매틱 복잡도 계산 방법

사이클로매틱 복잡도 V(G)는 다음 공식을 사용하여 계산할 수 있습니다:

```text
V(G) = E - N + 2P
```

- `E`는 프로그램 흐름 그래프의 에지(branches) 수
- `N`은 노드(statements) 수
- `P`는 연결 성분(graph components)의 수

단순화된 방식으로, 사이클로매틱 복잡도는 프로그램 내의 결정 포인트(예: if, for, while, case 등)의 수에 1을 더한 값으로 간주할 수 있습니다. 즉, 더 많은 조건문과 루프가 있다는 것은 더 높은 복잡도를 의미합니다.

## 30 이상의 복잡도 의미

- **30 이상의 복잡도**는 함수나 모듈이 매우 복잡하다는 것을 나타냅니다. 이러한 수준의 복잡도는 코드를 이해하고 유지 보수하는 데 상당한 어려움이 있음을 시사합니다.
- 일반적으로, 사이클로매틱 복잡도가 10을 넘으면 함수를 리팩토링하여 복잡도를 줄이는 것이 좋습니다. 20 이상이면 코드의 복잡성이 매우 높은 것으로 간주되며, 30 이상은 유지보수와 디버깅이 매우 어렵다는 것을 의미합니다.

## 복잡도 줄이는 방법

- **함수 분리**: 큰 함수를 더 작은 함수로 분리합니다.
- **조건문 단순화**: 복잡한 조건문을 단순화하거나, 전략 패턴과 같은 디자인 패턴을 사용하여 복잡한 결정 구조를 간소화합니다.
- **루프와 재귀 최적화**: 깊은 중첩 루프나 복잡한 재귀 호출을 개선합니다.

Go 코드에서는 `gocyclo`와 같은 도구를 사용하여 사이클로매틱 복잡도를 측정할 수 있습니다. 이러한 도구는 코드 분석 시 복잡도를 평가하는 데 도움이 되며, 리팩토링이 필요한 영역을 식별하는 데 유용합니다.