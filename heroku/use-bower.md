# heroku python 프로젝트에서 bower 사용하기

기본적으로  python 프로젝트의 buildpack에는 `npm`이 포함되어 있지 않기 때문에 `bower`를 사용할 수가 없다. 이를 해결하기 위해서는 `buildpack`을 추가해주면 된다. `buildpack` 추가는 각 애플리케이션 페이지의 `settings` 탭에서 추가할 수 있다. 아래의 두 `buildpack`을 추가해주자.

```
https://github.com/heroku/heroku-buildpack-nodejs
https://github.com/ejholmes/heroku-buildpack-bower
```

`nodejs buildpack`을 설치하면 당연히 `npm`이 설치가 되고, 아래의 `bower buildpack`에 의해 `bower`를 쓸 수 있다. 단, `bower.json`은 잘 구성해줘야 한다. `.bowerrc` 파일을 이용해서 경로 설정도 잘 해주자.
