# Case Converter
변수, 함수, 클래스 등의 이름이 여러 개의 단어로 표현될 때 이를 표현하기 위한 여러가지의 네이밍 컨벤션이 있습니다.
대표적으로 언더 바(`_`) 기호로 구분하는 snake_case, 대시(`-`) 기호로 구분하는 kebab-case, 첫 단어의 첫 글자는 소문자로, 두 번째 이후 단어의 첫 글자는 대문자로 쓰는 camelCase, camelCase와 비슷하지만 첫 단어의 첫 글자가 대문자인 PascalCase가 있습니다.

위 네 가지의 네이밍 컨벤션들을 서로 변환할 수 있는 프로그램을 작성해 봅시다. 

## Basic
시작 컨벤션을 snake를 기준으로 해서 변환할 컨벤션으로 변환하기 위한 함수를 작성해 봅시다.
- ```
  function snakeToKebab(snake) { }
  ```
- ```
  function snakeToCamel(snake) { }
  ```
- ```
  function snakeToPascal(snake) { }
  ```

위의 함수들을 작성했다면 아래처럼 테스트해볼 수 있습니다.
```javascript
let kebabCase = snakeToKebab('hello_world');
// 정상적으로 'hello_world'를 변환해서 'hello-world'를 반환한다면, 아래 조건문은 false가 되어 예외가 발생하지 않을거예요.
if(kebabCase !== 'hello-world') {
    throw 'kebab case가 아닙니다.'
}
```
다른 두 개의 `snakeToCamel` 함수와 `snakeToPascal` 함수도 동일한 형식으로 테스트를 해보고 모두 기대하는 대로 동작한다면 커밋해 주세요.

## Advanced Requirement 1
모든 시작 컨벤션 to 변환 컨벤션을 함수로 작성하기에는 함수의 수가 너무 많습니다. 아래처럼 호출할 수 있도록 변경해 봅시다.

```javascript
snakeTo('kebab', 'hello_world'); // -> 'hello-world'
snakeTo('camel', 'hello_world'); // -> 'helloWorld'
snakeTo('pascal', 'hello_world'); // -> 'HelloWorld'
```

## Advanced Requirement 2
꼭 시작 컨벤션이 필요할까요? 다음처럼 해볼수 있을까요? (이렇게 동작하려면 먼저 입력된 값이 어떤 네이밍 컨벤션에 해당되는지 판단할 수 있어야겠죠?)
```javascript
// snake -> kebab
toKebab('hello_world'); // -> 'hello-world'

// kebab -> camel
toCamel('hello-world'); // -> 'helloWorld'

// pascal -> snake
toSnake('HelloWorld'); // -> 'hello_world'
```

## Advanced Requirement 3
위에서 구현한 함수를 네이밍 컨벤션별로 자유롭게 객체로 설계해서 작성해 봅시다.