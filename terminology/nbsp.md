# nbsp

## nbsp?

U+00A0 (Non-Breaking Space, NBSP)는 일반적인 공백(U+0020)과는 다른 특수한 공백 문자입니다.

- **U+00A0**

    Non-Breaking Space는 줄 바꿈이 일어나지 않도록 하는 특수한 공백 문자입니다.
    웹 페이지에서 단어가 분리되지 않도록 할 때 주로 사용됩니다.

- **일반적인 공백(U+0020)**

    일반적인 공백은 텍스트에서 단어와 단어 사이를 구분하는 데 사용됩니다.

## IntelliJ IDEA에서 커밋 메시지를 복사할 때 NBSP가 포함되는 문제

IntelliJ IDEA에서 커밋 메시지를 작성하거나 복사할 때, 에디터가 NBSP를 포함한 특수 문자를 삽입할 수 있습니다.
이는 특정 설정이나 플러그인, 또는 에디터의 자동 포맷팅 기능에 의해 발생할 수 있습니다.

해결 방법:

1. **NBSP를 일반 공백으로 변환**:
   - 커밋 메시지를 복사한 후, 텍스트 에디터에서 NBSP를 일반 공백으로 수동으로 변환할 수 있습니다.
   - 예를 들어, Vim에서는 `:set list` 명령어를 사용하여 특수 문자를 확인하고, `:%s/\%u00A0/ /g` 명령어로 NBSP를 일반 공백으로 변환할 수 있습니다.

2. **IntelliJ IDEA 설정 확인**:
   - IntelliJ IDEA의 설정에서 자동 포맷팅이나 특수 문자를 삽입하는 기능을 비활성화할 수 있습니다.
   - `Settings` > `Editor` > `Code Style` > `General`에서 관련 설정을 확인하고 조정할 수 있습니다.

3. **플러그인 확인**:
   - 특정 플러그인이 NBSP를 삽입할 수 있으므로, 사용 중인 플러그인을 확인하고 필요 시 비활성화합니다.

다음은 Vim에서 NBSP를 일반 공백으로 변환하는 예시입니다:

```vim
:set list
:%s/\%u00A0/ /g
```