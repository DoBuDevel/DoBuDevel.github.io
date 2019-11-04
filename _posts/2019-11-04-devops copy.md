---
layout: splash
title: CI/CD
mathjax: true
category : theory
tag : CI/CD
comments : true
---

# 2.소스 배포

## CI/CD
- CI (Continuous Integration) - 지속적 통합
- CD (Continuous Delivery) or (Continuous Deployment)  - 지속적 서비스 배포  or 지속적 배포
두 가지 의미 모두 파이프라인의 추가 단계에 대한 자동화를 뜻하지만 때로는 얼마나 많은 자동화가 이루어지고 있는지를 설명하기 위해 별도로 사용되기도 합니다.

## 대표적 CI 툴 몇가지만 (많이 접하는..)
- [GitHub - ligurio/awesome-ci: List of Continuous Integration services](https://github.com/ligurio/awesome-ci)
- 개인적으로 쉘로 짜서 배포하는 것이 젤 편함..

### hudson (허드슨) (옛날엔 많이썻는데 요즘은 아예 안쓰는 추세)
- [Hudson Continuous Integration](http://hudson-ci.org/)
- CI 의 조상격 jenkins의 아버지

### jenkins (젠킨스)
- 회사에서 씀.
- 우리나라에서 젤 많이 쓰는듯..
- 모듈도 많고 많이 해봐서 편함..
- 도커도 지원되고 안되는 것이 없음.
- 사람들이 UI 구려서 잘안씀..

### gitlab ci (소개할 것)
- piccoma 프로젝트에 썼다.
- 간단한 배포 로직일 때 굉장히 좋은 것 같다. -하지만 픽코마는 배포가 복잡햇찌.-
- 회사에서 gitlab 서버를 사용하면 정말 좋은 CI 
- 여러가지 배포를 한부서가 담당하면 쓰지말아야할 CI (배포이력이 프로젝트마다 보임. 다 볼려면 젠킨스가 나음)

# 3. 서버 배포
## 무중단 배포.
- 무중단 배포 대표적으로 두가지

### 설명 잘된 이미지


### Blue Green Deployment
![RtQRg.png](https://i.stack.imgur.com/RtQRg.png)


- 기존 환경 Green
- Green 운영 Blue 만듬
- Blue 검증, 테스트
- Router 에서 Blue 환경으로 변경
- Blue 환경 전환 후 모니터링 후 문제가 없으면 삭제
- 이전 버전으로 변경이 필요할 경우 Green 으로 라우터 변경

### Canary Deployment
![bA9Xi.png](https://i.stack.imgur.com/bA9Xi.png)
- 일부 리소스에만 신규 버전의 app을 배포, 트래픽 중 일부를 분배,
- 검증 결과가 만족스러우면 조금씩 신규를 늘림,
- 최종적으로 모든 리소스  배포를 완료하면 종료.
- 기존 리소스를 그대로 활용하면서 수행할 수 있고, 새로운 버전 App을 새로운 리소스에 배포 하면서도 수행 할 수있다.

## 참고
[CI/CD란 무엇일까요?](https://www.redhat.com/ko/topics/devops/what-is-ci-cd)


