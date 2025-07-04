# 📦 common-response

Spring Boot에서 공통 응답 포맷을 재사용하기 위한 모듈입니다.  
성공/실패 응답을 일관된 형태로 전달할 수 있도록 설계되었습니다.

---

## ✅ 제공 클래스

- `CommonResponse<T>`: 성공/실패 응답 포맷
- `ErrorResponse`: 실패 시 에러 정보 구조
- `ErrorCode`: 에러 코드 명세용 인터페이스

---

## 📦 예시: 성공 응답

```java
return CommonResponse.success(data);
```

## 📦 예시: 실패 응답

``` java
return CommonResponse.fail(
    ErrorResponse.of("잘못된 요청입니다", 400)
);
```

## 🛠️ Gradle 의존성 추가
``` groovy
repositories {
    maven {
        url = uri("https://maven.pkg.github.com/terayukee/common-response")
        credentials {
            username = project.findProperty("gpr.user") ?: System.getenv("USERNAME")
            password = project.findProperty("gpr.key") ?: System.getenv("GITHUB_TOKEN")
        }
    }
}

dependencies {
    implementation 'com.terayukee:common-response:0.0.1-SNAPSHOT'
}
```

## 🎯 목적
- 여러 프로젝트에서 반복되는 응답 객체 중복 제거
- 통일된 API 응답 구조로 프론트/백 간 협업 효율 향상
- 단일 책임, 재사용성 높은 설계 추구

## ℹ️ 해당 라이브러리는 GitHub Packages를 통해 배포됩니다.
>
> 패키지를 사용하려면:
> - GitHub 계정에서 PAT를 발급하고 (`read:packages` 권한 필요)
> - 이 repository에 read 권한이 있어야 합니다.
>
> 권한이 없을 경우, 작성자에게 요청해 주세요.
