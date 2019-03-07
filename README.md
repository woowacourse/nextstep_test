# nextstep
우아한 코드 메인 서비스 저장소

---
# 로컬 개발환경 세팅

---
## git clone(submodule까지 clone)
```
git clone --recurse-submodules https://github.com/woowacourse/nextstep.git
```

---
## mysql 계정 생성 및 db 추가
```
CREATE USER 'nextstep'@'localhost' IDENTIFIED BY 'password';
GRANT ALL ON *.* TO 'nextstep'@'localhost';

CREATE DATABASE nextstep_wwh DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
```

---
## 로컬 서버 시작시 config location 설정
* IntelliJ -> Run -> Edit Configurations...
* nextstep.NextstepApplicationKt 추가 또는 선택 후 VM Options에 다음 설정 추가

```
-Dspring.config.location=classpath:/config/
```

![spring config](./resources/setting_spring_config.png)

* Test 수행을 위하여 Template -> JUnit 선택 후 VM options에도 추가

![test config](./resources/setting_test_config.png)

---
## submodule 저장소에 변경 내용 반영
```
git submodule foreach git pull

git submodule foreach git add .

git submodule foreach git commit -m "commit message"

git submodule foreach git push origin master
```
