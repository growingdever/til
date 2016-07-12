# 맥에서 여러 버전의 node 쓰기

`brew`를 이용해서 node 패키지를 관리하면 편리하다. `brew install node`를 하면 최신 버전의 node가 설치되고, `brew install node010`으로 설치하면 0.10.x 버전이, `brew install node012`로 설치하면 0.12.x 버전이 설치된다. 
새로운 버전의 node를 설치할 때는 기존의 node를 unlink 해줘야 한다. `brew unlink node` 한 뒤, `brew link --overwrite node010`을 실행하면 되는 식이다.
