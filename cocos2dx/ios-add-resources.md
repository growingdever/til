# iOS 프로젝트에 리소스 추가

ios에 들어갈 리소스들은 xcodeproj 세팅에서 원하는 target을 선택한 뒤 `Build Phases - Copy Bundle Resources`에 항목을 추가해줘야 한다. 이렇게 하면 빌드를 하면서 함께 패키징이 된다. 경로는 `Copy Bundle Resources`에 있는 디렉토리 구조 그대로 들어간다. 현재 작업 중인 프로젝트의 경우 `hello.js`에서 `jsb.js`라는 js-bindings를 통해 생성된 소스를 로드하게 되어 있다. 이런 경우에는 자동 생성되는 소스의 디렉토리를 reference로 추가해놓으면 알아서 같이 패키징 되므로 cocos2d-x 프로젝트의 Resources 디렉토리에 굳이 자동 생성되는 소스의 디렉토리를 복사해두지 않아도 된다. 
