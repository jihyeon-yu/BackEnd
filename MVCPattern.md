## MVC 패턴

MVC(Model-View-Controller) 패턴은 소프트웨어 설계에서 사용자 인터페이스로부터 비즈니스 로직을 분리하기 위해 사용되는 디자인 패턴입니다. 이 패턴은 애플리케이션을 세 가지 주요 구성 요소로 나누어 구성하며, 각 구성 요소는 특정 역할을 수행합니다. MVC 패턴의 동작 흐름은 사용자 인터페이스와 비즈니스 로직 사이의 결합도를 낮추고, 유지보수와 확장성을 높이는 데 도움을 줍니다.

### MVC 구성 요소
- **Model**: 애플리케이션의 데이터와 비즈니스 로직을 관리합니다. 데이터의 조회, 생성, 수정, 삭제 등의 기능을 담당하며, 상태의 변경이 있을 때 View에게 통지하여 자동으로 화면이 갱신되도록 합니다.
- **View**: 사용자에게 정보를 표시하는 역할을 담당합니다. Model로부터 데이터를 받아 사용자가 볼 수 있는 형태로 렌더링합니다.
- **Controller**: 사용자의 입력을 받고 처리하는 역할을 담당합니다. 사용자의 액션에 따라 Model을 업데이트하고, 그 결과를 View에 반영하여 사용자에게 피드백을 제공합니다.

### 동작 흐름
1. **사용자 액션**: 사용자는 View를 통해 애플리케이션과 상호작용합니다. 예를 들어, 웹 애플리케이션에서는 사용자가 버튼을 클릭하거나 링크를 따라가는 것이 이에 해당합니다.
2. **Controller 처리**: 사용자의 액션은 Controller로 전달됩니다. Controller는 사용자의 입력, 데이터의 조회 요청 등을 분석하여 필요한 작업을 결정합니다.
3. **Model 업데이트**: Controller는 Model을 조작하여 데이터를 생성, 조회, 업데이트, 삭제 등의 작업을 수행합니다. 이러한 작업은 비즈니스 로직의 일환으로, 애플리케이션의 상태를 변경합니다.
4. **View 갱신**: Model의 상태 변경을 View에 반영합니다. Model은 상태 변화에 대해 View를 자동으로 업데이트하거나, Controller가 특정 View를 선택하여 상태 변화를 반영하도록 할 수 있습니다. 이 과정에서 View는 Model로부터 최신 데이터를 조회하여 사용자에게 보여줍니다.
5. **사용자에게 피드백 제공**: View가 갱신되면, 사용자는 새로운 정보를 통해 자신의 액션이 시스템에 어떤 영향을 미쳤는지 볼 수 있습니다. 이는 사용자에게 직접적인 피드백을 제공하는 과정입니다.

이러한 흐름을 통해 MVC 패턴은 역할에 따른 구분을 명확히 하여 애플리케이션의 유지보수성, 확장성 및 테스트 용이성을 향상시킵니다. 또한, 개발 과정에서 프론트엔드와 백엔드를 분리하여 작업할 수 있어 팀 작업의 효율성을 높일 수 있습니다.
