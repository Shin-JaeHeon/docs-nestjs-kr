# 시작하기
시작하기 위해 Nest CLI를 사용하거나 GitHub에서 프로젝트를 복제할 수 있습니다. 두 프로젝트 모두 동일한 결과가 생성됩니다.

Nest CLI를 사용하여 프로젝트를 조정하려면 다음 명령을 실행합니다. 그러면 초기 코어 Nest 파일 및 지원 모듈이 포함되어 디렉터리가 생성됩니다. 처음 시작하는 사용자라면, Nest CLI를 사용하여 새 프로젝트를 생성하는 것이 좋습니다.

## 설치 방법

```
$ npm i -g @nestjs/cli
$ nest new project-name
```

## TypeScript 스타터 프로젝트
TypeScript Starter Project가 필요하다면 아래와 같이 다운로드 할 수 있습니다.
```
$ git clone https://github.com/nestjs/typescript-starter.git project
$ cd project
$ npm install
$ npm run start
```
## 수동으로 설치하기
핵심 파일과 지원 파일을 npm이나 yarn으로 설치하여 새 프로젝트를 수동으로 생성 할 수도 있습니다. 물론 이 경우에는 프로젝트 파일을 직접 작성해야합니다.
```
$ npm i --save @nestjs/core @nestjs/common rxjs reflect-metadata
```
