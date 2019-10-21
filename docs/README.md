# Nest.js
Nest는 효율적이고 확장 가능한 Node.js 서버 애플리케이션을 구축하기 위한 프레임워크입니다. 프로그레시브 JavaScript를 사용하고 OOP(Object Oriented Programming), FP(Functional Programming) 및 FRP(Functional Reactive Programming)의 요소를 결합하여 TypeScript를 지원합니다. 아직은 순수 JavaScript로 개발할 수 있습니다. 

Nest는 Express(기본값) 및 Fastify와 같은 강력한 HTTP Server 프레임워크를 사용합니다. Nest는 이러한 프레임워크의 추상화를 제공하고 있지만, API에 직접 접근하는 것도 가능합니다. 따라서 각 플랫폼에서 사용할 수 있는 무수히 많은 타사 모듈을 쉽게 사용할 수 있습니다.

## 철학 
최근 몇 년 동안 Node.js 덕분에 자바스크립트는 프론트엔드 및 백엔드 애플리케이션을 위한 웹의 "링구아 프랑카(Lingua franca)"이 되었습니다. 이로 인해 Angular, React 및 Vue 와 같은 멋진 프로젝트가 생겨났습니다. 이 프로젝트는 개발자 생산성을 향상시키고 빠르고 테스트 가능하며 확장 가능한 프론트엔드 애플리케이션을 구축 할 수 있게합니다. 그러나 Node (그리고 서버사이드 JavaScript)에는 뛰어난 라이브러리, 헬퍼 및 도구가 많이 있지만 그 중 아무도 주요 문제인 **아키텍처**를 효과적으로 해결하지 못합니다 .

Nest는 개발자와 팀이 고도로 테스트 가능하고, 확장 가능하며, 느슨하게 결합되고, 유지 관리가 용이한 애플리케이션을 만들 수 있도록 지원하는 기본 제공 애플리케이션 아키텍처를 제공합니다.

## 시작하기
시작하기 위해 Nest CLI를 사용하거나 GitHub에서 프로젝트를 복제할 수 있습니다. 두 프로젝트 모두 동일한 결과가 생성됩니다.

Nest CLI를 사용하여 프로젝트를 조정하려면 다음 명령을 실행합니다. 그러면 초기 코어 Nest 파일 및 지원 모듈이 포함되어 디렉터리가 생성됩니다. 처음 시작하는 사용자라면, Nest CLI를 사용하여 새 프로젝트를 생성하는 것이 좋습니다.

## 설치 방법

```
$ npm i -g @nestjs/cli
$ nest new project-name
```
> TypeScript Starter Project가 필요하다면 아래와 같이 다운로드 할 수 있습니다.
> ```
> $ git clone https://github.com/nestjs/typescript-starter.git project
> $ cd project
> $ npm install
> $ npm run start
> ```

## 수동으로 설치하기
핵심 파일과 지원 파일을 npm이나 yarn으로 설치하여 새 프로젝트를 수동으로 생성 할 수도 있습니다. 물론 이 경우에는 프로젝트 파일을 직접 작성해야합니다.
```
$ npm i --save @nestjs/core @nestjs/common rxjs reflect-metadata
```
