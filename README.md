# KT “소동물 펫케어” 개인 프로젝트 기획서

## 👀 개요
---
- 동물을 기르는 사람들을 위한 펫케어 프로젝트(**KT 소동물 팻캐어 관리 플랫폼**)입니다.
- 간단하게 대쉬보드를 통해 반려동물 항목을 추가하고 관리하는 웹 플랫폼으로 구성돼있습니다.
- 일일 급여량을 기록하고 날짜별 반려동물의 체중 변화, 일일 급여량등의 정보를 시각화하여 제공합니다.
- 모든 소동물들이 행복한 삶을 살고, 주인들은 동물관계 관계에서 행복을 느끼는 것을 목표로 합니다.
(* 소동물은 케이지안에서 기를 수 있는 모든 동물들로 정의한다.)

***미션***
사용자가 반려 뱀을 효율적으로 관리할 수 있도록 데이터 기반의 맞춤형 솔루션을 제공하고, 언제 어디서나 반려 뱀의 상태를 확인할 수 있는 플랫폼을 구축하는 것.

***핵심가치***
1. 사용자 중심: 사용자의 요구와 편의를 최우선으로 고려한 기능 설계.
2. 정확성: 정확하고 신뢰할 수 있는 데이터 제공.
3. 접근성: 누구나 쉽게 접근하고 사용할 수 있는 간단하고 직관적인 인터페이스.
4. 지속 가능성: 장기적인 반려 뱀 관리 솔루션을 제공하여 사용자와 반려 동물의 지속적인 관계 유지.
5. 혁신성: 최신 기술을 활용하여 지속적으로 기능을 개선하고 새로운 기능을 도입.
6. 안정성: 핵심 기능인 반려동물 등록, 급여량 기록 기능을 MSA방식으로 설계하여 솔루션 안정성 확보.

## 🗂️ 기능 목록
---
- 새로운 친구 추가하기, 삭제하기, 수정하기
- 개체별 먹이기록 추가하기, 불러오기
- 통계기능 - 먹이기록 데이터 분석
    - 날짜별 몸무게 추이 그래프
    - 달력에 먹이기록 별 표시하기
- 공기계를 통한 CCTV 모니터링 기능
    - socket io를 통해 집에 있는 동물 관찰
 
## 📘 UI/UX
<img width="486" alt="image" src="https://github.com/user-attachments/assets/d1e1b131-9e11-44a4-a8e9-72a45616c331">

<img width="1440" alt="image" src="https://github.com/user-attachments/assets/e676b26d-dac7-4e06-85bf-c98270b6e3da">


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/64aa3a42-8f18-4105-a0a1-bdedec1cfef5/c7399ec6-e0ba-46e1-876a-306cf9c7e3dc/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/64aa3a42-8f18-4105-a0a1-bdedec1cfef5/c416cda3-e39b-4a40-b51b-3a65b3c96990/image.png)

https://github.com/user-attachments/assets/4d2a3907-fad2-4712-a129-606f6862dcbf

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/64aa3a42-8f18-4105-a0a1-bdedec1cfef5/1644ed19-3a3f-4c83-8f5d-ccd9ec2fd46a/image.png)


## 서비스 시나리오

  1. 사용자가 반려동물을 등록한다.
  2. 등록된 반려동물별로 급여량, 체중등을 기록한다.
  3. 데이터를 수합하여 반려동물 별 시각화자료를 제공한다.
  4. 반려동물, 급여량 데이터는 수정/삭제가 가능하다.
  5. 등록한 반려동물 정보는 메인화면에서 조회가 가능하다.
     
## 분석/설계
### AS-IS조직(Horizontally-Aligned)
![image](https://github.com/user-attachments/assets/42987a4f-dd7e-4f69-86e7-71db9ca8513e)
### TO-BE조직(Vertically-Aligned)
![image](https://github.com/user-attachments/assets/03d85da0-9212-42ef-afae-141fe3756b54)

## 이벤트 스토밍
1. 이벤트 도출
   ![image](https://github.com/user-attachments/assets/87a6da6e-3ce7-4ef3-b89c-bf3d5e8bf26e)
2. 부적격 이벤츠 탈락
  - 단순 프론트엔드 작업 제외
  ![image](https://github.com/user-attachments/assets/4f49ba05-f18f-4d86-9c9b-d269abe8a089)
3. 액터, 커맨드 부착
  ![image](https://github.com/user-attachments/assets/7ace939e-c403-4940-ad6e-d58fcca56b51)
4. 어그리게잇으로 묶기
  ![image](https://github.com/user-attachments/assets/12ba3ba0-0ef0-4bbd-9069-4e7187dc4d15)
5. 바운디드 컨텍스트로 묶기
  ![image](https://github.com/user-attachments/assets/4fd2eaff-fd76-4dc6-a487-c1467c404292)
6. 폴리시 부착및 컨텍스트 매핑(점선은 pub/sub방식)
  ![image](https://github.com/user-attachments/assets/92bd2205-924c-4c81-a112-f5d32af8bd62)
- 최종 결과
  ![image](https://github.com/user-attachments/assets/e39a9a9c-09b4-49f6-b4ca-a6b7b7145c54)
  - 링크
  **https://www.msaez.io/#/130229528/storming/ndpro**

  ![image](https://github.com/user-attachments/assets/e39a9a9c-09b4-49f6-b4ca-a6b7b7145c54)

## 구현
각 마이크로 서비스들을 스프링부트로 구현하여 게이트웨이를 활용하여 진입점을 통일하였다.(각자의 포트넘버는 8081 ~ 808n 이다)
###  DDD의 적용
각 Aggregate 객체를 Entity 로 선언하여 활용하였다.
![image](https://github.com/user-attachments/assets/6bff564a-5de3-4326-a73f-c7b6b2acba40)

JPA와 H2데이터베이스를 활용하였고, ORM을 활용하여 CRUD기능을 구현하였다.
![image](https://github.com/user-attachments/assets/a5188299-4214-4f2c-915f-63026c8a7480)

적용 후 REST API 의 테스트
![image](https://github.com/user-attachments/assets/564e7af5-7e6a-49fb-bb4b-377a87dcd5ee)


## 🐙 AKS 배포 현황

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/64aa3a42-8f18-4105-a0a1-bdedec1cfef5/828c1484-590b-49de-adf4-7fdf48457b5b/image.png)

- **참조**

![스크린샷 2024-10-02 오전 9.22.47.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/64aa3a42-8f18-4105-a0a1-bdedec1cfef5/11d17d33-1248-430e-8e6c-4309af8aad25/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-10-02_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_9.22.47.png)

### 🏛️ Gateway 설정
---

```yaml
server:
  port: 8088
---
spring:
  profiles: default
  cloud:
    gateway:
      routes:
        - id: order
          uri: http://localhost:8081
          predicates:
            - Path=/orders/**,
        - id: pet
          uri: http://localhost:8082
          predicates:
            - Path=/pets/**,
        - id: feed
          uri: http://localhost:8083
          predicates:
            - Path=/feeds/**,
        - id: bambam-front
          uri: http://localhost:8080
          predicates:
            - Path=/**
      globalcors:
        corsConfigurations:
          '[/**]':
            allowedOrigins:
              - '*'
            allowedMethods:
              - '*'
            allowedHeaders:
              - '*'
            allowCredentials: true
---
spring:
  profiles: docker
  cloud:
    gateway:
      routes:
        - id: order
          uri: http://order:8080
          predicates:
            - Path=/orders/**,
        - id: pet
          uri: http://pet:8080
          predicates:
            - Path=/pets/**,
        - id: feed
          uri: http://feed:8080
          predicates:
            - Path=/feeds/**,
        - id: bambam-front
          uri: http://bambam-front:8080
          predicates:
            - Path=/**
      globalcors:
        corsConfigurations:
          '[/**]':
            allowedOrigins:
              - '*'
            allowedMethods:
              - '*'
            allowedHeaders:
              - '*'
            allowCredentials: true

server:
  port: 8080

```

## 🔋 부하 테스팅
---

```yaml
kubectl exec -it siege -- /bin/bash

siege -c1 -t60S -v http://order:8080/orders --delay=1S (테스트용)
siege -c1 -t60S -v http://pet:8080/pets --delay=1S
siege -c1 -t60S -v http://feed:8080/feeds --delay=1S
```

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/64aa3a42-8f18-4105-a0a1-bdedec1cfef5/11984e33-d757-4855-8712-5fe154a824f5/image.png)

## 🚫 무정지 재배포
- 모든 프로젝트의 readiness probe 및 liveness probe 설정 완료.

```yaml

readinessProbe:
  httpGet:
    path: /actuator/health
    port: 8080
  initialDelaySeconds: 10
  timeoutSeconds: 2
  periodSeconds: 5
  failureThreshold: 10
livenessProbe:
  httpGet:
     path: /actuator/health
     port: 8080
  initialDelaySeconds: 120
  timeoutSeconds: 2
  periodSeconds: 5
  failureThreshold: 5
```

### **오토 스케일 적용**
- replica 를 동적으로 늘려주도록 HPA 를 설정한다. 설정은 CPU 사용량이 15프로를 넘어서면 replica 를 10개까지 늘려준다.
    
    ```yaml
    kubectl autoscale deploy feed --min=1 --max=10 --cpu-percent=15
    ```
    

## 🚨 트러블 슈팅
---

```yaml
**모든 CI/CD 과정이 정상진행 되지만 재배포가 되지 않는 현상발생**

- 원인: gitpod가 아닌 local m1 air에서 docker image 생성 시, linux와 호환되지 않는 image가 생성됨
- **해결: docker build -t  →** buildx build --platform linux/amd64,linux/arm64 -t 명령어로 호환되게 변경

**재배포 확인됐지만 소스코드 반영 되지 않는 현상발생(kutectl get all로 확인)**

- 원인: 빌드 시, 캐싱 발생(mvn package, npm run build, 브라우저 캐싱)
- 해결: 소스코드 빌드 시, 기존 dist 및 target 참조하지 않고 빌드 진행 및  브라우저 캐시 삭제
```

## ➕ 참고사항
---
- 추후 storage를 이용할 예정이어서 키값 들은 .env에 별도 보관중입니다.
    - 참조 사용한 브랜치 및 커밋 전략
    
    ```yaml
    **[브랜치 전략]**
    <커밋_타입>(<영향_범위>): <수정사항_한줄_요약>
      │       │             │
      │       │             └─⫸ 수정사항 한줄 요약
      │       │
      │       └─⫸ 영향받은 서비스: transfer|my-insurance|business-ledger|...
      │
      └─⫸ 수정 종류: feat|fix|perf|refactor|test|ci|docs|build|chore
    
    브랜치명은 "/"로 구분한다.
    예시) feat/bambam/login
    
    **[커밋 전략]**
    <커밋_타입>(<영향_범위>): <수정사항_한줄_요약>
      │       │             │
      │       │             └─⫸ 수정사항 한줄 요약
      │       │
      │       └─⫸ 영향받은 서비스: transfer|my-insurance|business-ledger|...
      │
      └─⫸ 수정 종류: feat|fix|perf|refactor|test|ci|docs|build|chore
    
    setting: 라이브러리 등 초기 환경설정
    feat: 기능 추가
    fix: 버그 수정
    refact: 리팩토링(기능변경x)
    docs: 주석 및 마크다운
    
    커밋메세지는 " "로 구분한다.
    예시) feat bambam: login validation
    
    ```
