# System Errors

- [System Errors](#system-errors)
    - [시스템 오류(System Errors)](#시스템-오류system-errors)
    - [`ENOENT`](#enoent)
    - [`EACCES`](#eacces)
    - [`EEXIST`](#eexist)
    - [`ENOMEM`](#enomem)
    - [`EINVAL`](#einval)
    - [`EBUSY`](#ebusy)
    - [`EIO`](#eio)

## 시스템 오류(System Errors)

`ENOENT`와 같은 용어들은 주로 운영 체제의 시스템 호출이나 프로그래밍 인터페이스에서 발생하는 오류 코드를 나타낸다.
이러한 오류 코드들은 프로그램 실행 중 발생할 수 있는 다양한 종류의 예외 상황을 식별하기 위해 사용된다.

## `ENOENT`

`ENOENT`는 "Error NO ENTry"의 약자로, 파일이나 디렉토리가 존재하지 않을 때 발생하는 오류를 나타낸다.
예를 들어, 존재하지 않는 파일을 열려고 시도하거나, 존재하지 않는 디렉토리에 접근하려고 할 때 이 오류 코드가 반환된다.

## `EACCES`

"Error ACCESS"의 약자로, 요청된 작업에 대한 권한이 없을 때 발생한다.
예를 들어, 읽기 전용 파일에 쓰려고 시도할 때 이 오류가 발생할 수 있다.

## `EEXIST`

"Error EXIST"의 약자로, 파일이 이미 존재하고 있을 때 발생하는 오류다.
예를 들어, 이미 존재하는 파일을 새로 생성하려고 시도할 때 이 오류가 반환된다.

## `ENOMEM`

"Error NO MEMory"의 약자로, 충분한 메모리가 없을 때 발생한다.
시스템에서 더 이상 프로세스에 메모리를 할당할 수 없을 때 이 오류가 발생할 수 있다.

## `EINVAL`

"Error INVALid"의 약자로, 잘못된 인자가 함수에 전달되었을 때 발생하는 오류다.
예를 들어, 시스템 호출에 유효하지 않은 인자를 전달했을 때 이 오류가 반환될 수 있다.

## `EBUSY`

"Error BUSY"의 약자로, 리소스가 현재 사용 중이고 사용할 수 없을 때 발생하는 오류다.
예를 들어, 언마운트하려는 파일 시스템이 현재 사용 중일 때 이 오류가 발생할 수 있다.

## `EIO`

"Error Input/Output"의 약자로, 입출력 오류가 발생했을 때 반환된다.
하드웨어 오류 또는 데이터 전송 오류 등이 원인일 수 있다.