## Interceptor, ArgumentResolver 분리

`Interceptor`와 `ArgumentResolver`는 각각 다른 목적과 역할을 가지고 있으며, 분리해서 사용해야 한다.

### 1. 역할과 책임의 분리

ArgumentResolver는 요청 파라미터나 경로 변수와 같은 입력 데이터를 바인딩하고, 메서드의 파라미터로 전달하는 역할을 수행한다. 반면에 Interceptor는 요청
전후에 수행되는 전처리와 후처리 로직을 담당한다. 두 가지 역할을 서로 다른 책임을 가지고 있으므로, 분리해서 사용하면 코드의 가독성과 유지보수성을 향상할 수 있다.

### 2. 재사용성과 확장성

각각 독립적으로 개발 및 확장될 수 있다. 분리해서 사용하면, 다양한 Interceptor와 ArgumentResolver를 개별적으로 작성하여 재사용할 수 있다. 또한, 필요한
경우 Interceptor나 ArgumentResolver를 추가하거나 제거하여 애플리케이션의 특정 기능을 유연하게 조정할 수 있다.

### 3. 실행 순서 제어

Interceptor는 핸들러 전후에 호출되고 ArgumentResolver는 컨트롤러 메서드 실행 전에 호출된다. 분리해서 사용하면 각각의 실행 순서를 조절하여 필요한 처리를
수행할 수 있다.
