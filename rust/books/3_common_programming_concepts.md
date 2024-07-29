# 3. Common Programming Concepts

## 3.1. Variables and Mutability

## [3.2. Data Types](https://doc.rust-lang.org/book/ch03-02-data-types.html)

### Scalar Types

스칼라 타입은 단일 값을 나타낸다.
Rust에는 integers, floating-point numbers, Booleans, 그리고 characters 네 가지 기본 스칼라 유형이 있다.

#### Integer Types

### Compound Types

#### The Tuple Type

#### The Array Type

##### `Vec<u8>`과 `[u8]`

`Vec<u8>`과 `[u8]`은 Rust에서 서로 다른 타입이지만, 관련이 깊으며 특정 상황에서 상호 변환 가능하다.
이 두 타입을 이해하는 것은 Rust의 메모리 관리와 타입 시스템을 이해하는 데 중요하다.

- `Vec<u8>`

    `Vec<u8>`는 u8 타입의 요소를 가지는 동적 배열(벡터)이다.
    동적 배열이라는 것은 런타임에 크기가 변할 수 있다는 것을 의미한다.
    벡터는 *힙* 메모리에 데이터를 저장하며, 크기 변경이 가능하다.

    `Vec<u8>` 타입은 `Vec` 구조체의 메서드와 특성을 사용할 수 있다.
    요소 추가, 제거, 접근 등 다양한 동적 배열 관련 연산을 수행할 수 있다.

- `[u8]`

    `u8` 타입의 요소를 가지는 슬라이스(slice)다.
    슬라이스는 배열의 연속된 부분을 참조하는 "뷰"로, 슬라이스 자체는 소유권을 갖지 않는다.
    즉, 슬라이스는 데이터의 소유권을 가지는 것이 아니라, 데이터의 일부 또는 전체를 "참조"한다.

    `[u8]`는 고정된 크기를 가지지 않으며 컴파일 타임에 크기가 결정되지 않는다.
    그 크기는 런타임에만 알 수 있다.

`Vec<u8>`에서 `[u8]` 슬라이스로의 변환은 자주 사용되는 연산이다.
이는 `Vec<u8>`가 소유한 데이터에 대한 *불변 참조*를 생성하여 수행된다.
예를 들어, `&vec[..]` 또는 `vec.as_slice()` 메서드를 사용하여 `Vec<u8>` 타입의 변수를 `[u8]` 슬라이스로 변환할 수 있다.

```rust
let vec = vec![1, 2, 3];
let slice: &[u8] = &vec[..]; // Vec<u8>에서 &[u8]로 변환
```

함수가 `[u8]` 타입의 슬라이스를 매개변수로 받는 경우, `Vec<u8>` 타입의 변수를 직접 전달할 수 있다.
Rust 컴파일러는 자동으로 `Vec<u8>` 타입을 `[u8]` 슬라이스로 변환해 준다.
이 변환은 `Vec<u8>` 변수에 대한 *불변 참조*를 생성함으로써 이루어진다.

```rust
fn process(data: &[u8]) {
    // 데이터 처리 로직
}

let data = vec![1, 2, 3];
process(&data); // Vec<u8> 타입의 변수를 &[u8] 타입의 매개변수에 전달
```

이러한 변환은 Rust의 *타입 추론*과 *자동 참조* 및 *역참조 기능* 덕분에 가능하다.
따라서 `Vec<u8>`과 `[u8]`은 서로 다른 타입이지만, Rust에서는 이들 간의 상호 작용이 매우 자연스럽게 이루어진다.