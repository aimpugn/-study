# Go 언어 연산자

- [Go 언어 연산자](#go-언어-연산자)
    - [할당 연산자](#할당-연산자)
    - [단축 할당 연산자](#단축-할당-연산자)
    - [산술 연산자](#산술-연산자)
    - [비교 연산자](#비교-연산자)
    - [논리 연산자](#논리-연산자)
    - [비트 연산자](#비트-연산자)
    - [기타 연산자](#기타-연산자)

## 할당 연산자

- `=` 연산자는 이미 선언된 변수에 값을 할당하는데 사용된다.
- 예시: `x = 5`

## 단축 할당 연산자

- Go 언어에서 `:=`는 새로운 변수를 선언하고 초기화하는 단축 할당 연산자.
- 이 연산자를 사용하면, **해당 범위(scope) 내에서만 유효한 새로운 변수**가 생성된다.
- 예시: `y := 10`

## 산술 연산자

- 기본적인 수학 연산에 사용되는 연산자들.
- `+` (덧셈), `-` (뺄셈), `*` (곱셈), `/` (나눗셈), `%` (모듈로 연산).

## 비교 연산자

- 두 값의 비교에 사용되는 연산자들.
- `==` (동등), `!=` (부등), `<` (미만), `>` (초과), `<=` (이하), `>=` (이상).

## 논리 연산자

- 불리언(Boolean) 값의 논리 연산에 사용되는 연산자들.
- `&&` (AND), `||` (OR), `!` (NOT).

## 비트 연산자

- 정수형 데이터의 비트 단위 연산에 사용되는 연산자들.
- `&` (비트 AND), `|` (비트 OR), `^` (비트 XOR), `&^` (비트 클리어), `<<` (왼쪽 시프트), `>>` (오른쪽 시프트).

## 기타 연산자

- `&` (주소 연산자): 변수의 메모리 주소를 반환.
- `*` (역참조 연산자): 포인터가 가리키는 변수의 값을 반환.
- `<-` (채널 연산자): 채널로부터 값을 보내거나 받는 데 사용.