
1.  **빌드란?** 소스코드를 컴퓨터가 실행할 수 있도록 변환하는 작업 전체를 의미 코드를 실행 가능한 프로그램으로 변환하는 과정
    
2.  **빌드 과정에 포함되는 것들**
    

*   컴파일(Compile)
*   의존성 관리 (Dependency Management) : 프로젝트에 필요한 외부 라이브러리를 자동으로 다운로드하고 포함 시킴
*   리소스 처리 : 이미지, XML 레이아웃, 문자열 등 앱에 필요한 자원을 함께 패키징
*   패키징(Packaging) : 모든 파일을 하나의 실행 파일로 묶음
*   사인(Signing) : 앱에 디지털 서명을 해서 보안과 인증을 보장
*   최적화(옵션) : 코드 암호화, 불필요한 코드 제거 등

1.  **빌드 도구** Make, Ant Build, Gradle, Maven등
    
2.  **Gradle** 빌드는 여러 단계(Task)로 구성되어 있고, Gradle이 순서대로 실행함
    

    순서| Task 이름         | 설명 
     1| `clean`             | 이전 빌드 결과 삭제 (`build` 폴더 삭제)
     2| `compileJava`      | Java 소스코드 컴파일
     3| `processResources` | `resources` 폴더 내 리소스 처리 (예: `application.properties`)
     4| `classes`          | `compileJava` + `processResources` 결과를 묶음
     5| `jar`                | `.jar` 파일 생성
     6| `test`              | JUnit 등의 테스트 실행
     7| `build`            | 전체 빌드 수행 (test 포함)
    

* * *

1.  **build.gradle파일** 프로젝트의 빌드, 의존성 관리, 태스크 수행 등을 정의하는 스크립트이다. 이 파일을 통해 Gradle은 프로젝트를 어떻게 빌드할지, 어떤 라이브러리나 의존성을 사용할지, 어떤 태스크들을 실행할지 등을 알게된다
    
2.  **buld.gradle파일의 구성요소**
    

*   plugins : 어떤 프로젝트 유형인지 (예: Spring Boot, Java Library, Android 등) plugins { id 'java' }
*   repositories : 외부 라이브러리를 받을 저장소 설정 repositories { mavenCentral() }
*   dependencies : 어떤 외부 라이브러리를 사용하는지 (예: Spring Web, JPA, Lombok 등) \[configuration\] '\[group\]:\[name\]:\[version\]’ | configuration종류 | 설명 | -------------------- | ----------------------------------------------- | `implementation` | 코드에서 사용하는 라이브러리 | `api` | 라이브러리를 외부 모듈도 함께 사용해야 할 때 (library module에서 사용) | `compileOnly` | 컴파일할 때만 필요, 런타임에는 필요 없음 (예: Lombok) | `runtimeOnly` | 실행할 때만 필요 (예: H2 DB) | `testImplementation` | 테스트 코드에서만 사용하는 라이브러리 (JUnit, Mockito 등)

dependencies { implementation 'com.mysql:mysql-connector-j:8.4.0’ testImplementation platform('org.junit:junit-bom:5.10.0') testImplementation 'org.junit.jupiter:junit-jupiter’ }

*   test : 테스트 도구를 설정 test { useJUnitPlatform() }

7.  **Gradle 명령어** `gradle명령어`는 시스템에 설치된 버전만 사용한다 `gradlew`명령어는 Gradle Wrapper 실행 스크립트이다. 프로젝트에 정의된 Gradle 버전으로 빌드 작업을 실행할 수 있게 해주는 도구로서 플랫폼에 따라

*   **Unix/macOS**: `./gradlew`
*   **Windows**: `gradlew.bat`

을 실행하게 되어 있다.

| 명령어 | 설명 |
| --- | --- |
| `gradlew tasks` | 사용 가능한 태스크 목록 보기 |
| `gradlew build` | 프로젝트 전체 빌드 (compile + test + package 등 포함) |
| `gradlew clean` | 이전 빌드 결과물 삭제 (`build/` 디렉토리 삭제) |
| `gradlew test` | 테스트 코드 실행 (JUnit 등) |
| `gradlew assemble` | JAR/WAR 생성 등 아카이브만 생성 (컴파일 + 패키징) |
| `gradlew check` | 테스트 및 코드 검사 수행 (`test` 포함) |
| `gradlew run` | `application` 플러그인을 사용한 앱 실행 (`main()` 실행) |
| `gradlew jar` | 일반 JAR 파일 생성 |
| `gradlew bootJar` | 실행 가능한 Spring Boot JAR 파일 생성 |
| `gradlew bootRun` | Spring Boot 앱 실행 (내장 톰캣 포함) |

1.  **Gradle명령어 실행 옵션**

| 옵션 | 설명 |
| --- | --- |
| \--info | 상세 정보 출력 (태스크별 로그 등) |
| \--debug | 디버그 모드 (매우 상세한 로그 출력) |
| \--stacktrace | 에러 발생 시 스택 트레이스 출력 |
| \--refresh-dependencies | 캐시된 라이브러리 무시하고 의존성 강제 다시 다운로드 |
| \--offline | 인터넷 없이 로컬 캐시만 사용해 빌드 |
| \--dry-run | 실제로 실행하지 않고 어떤 태스크가 실행될지만 보여줌 |
| \--continue | 빌드 중 실패가 발생해도 가능한 다른 태스크 계속 실행 |
| \-x <task> | 특정 태스크 제외 (예: `x test`) |

build 태스크 실행 (전체 프로젝트 빌드) : ./gradlew build 테스트 테스크는 제외하고 빌드 : ./gradlew build -x test 디버그 로그와 함께 build태스크 실행 : ./gradlew build --debug