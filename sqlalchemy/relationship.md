relationship에서 `lazy` 옵션의 기본 값은 `select`이다. 이 옵션의 경우 해당 relationship 변수에 접근하자마자 `limit` clause 없이 select 해오는 query를 실행한다. `lazy` 옵션을 `dynamic`으로 둘 경우 `Query` 객체에 index를 붙여서 접근할 때 `limit` clause가 추가된 select query를 실행한다. 

특정 조건을 만족하는 relationship만을 로드하고 싶을 때는 primaryjoin에 조건을 넣으면 된다. 공식 문서에서는 string literal로 조건을 명시해줬는데, lambda를 사용하면 직접 클래스와 변수를 참조하여 조건을 작성할 수 있다. 나중에 변수명이 변경된다거나 할 때 IDE의 힘을 빌리고자 할 경우, 이렇게 하는 것이 더 좋을 것으로 생각된다. 사용 방법은 다음과 같다.

```
actions_like = db.relationship(
    'DocumentActivityModel',
    lazy='joined',
    primaryjoin=lambda: and_(DocumentModel.id == DocumentActivityModel.document_id,
                             DocumentActivityModel.activity == 'like'))
```

foreign key에 해당하는 부분의 조건은 제외할 수 있으면 좋지 않을까 싶은데, 일단은 불가능해보인다. 직접 추가적으로 함수를 구현해주면 가능할 것 같긴 하다. 근데 그렇게 하는게 더 좋을지는 모르겠다.
