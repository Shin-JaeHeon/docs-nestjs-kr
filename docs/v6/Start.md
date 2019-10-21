# 첫 걸음부터 시작하는 Nest.js
이 기사에서는 Nest의 **핵심 기본 사항**을 학습합니다. Nest 애플리케이션의 필수 구성 요소에 익숙해 지도록 입문 레벨에서 많은 기초를 다루는 기능을 갖춘 기본 CRUD 애플리케이션을 빌드합니다.
## 언어
우리는 **TypeScript**를 좋아하지만 무엇보다도 **Node.js**를 좋아합니다. 그렇기 때문에 Nest는 TypeScript 및 **순수 JavaScript**와 호환됩니다. Nest는 최신 언어 기능을 활용하므로 바닐라 JavaScript와 함께 사용하려면 Babel 컴파일러가 필요합니다.

?> 한국어 문서에서는 **TypeScript** 코드만을 표시하고 있습니다. JavaScript로 표시된 코드를 보시려면 영문 문서를 참조하시기 바랍니다. 
## 조건
`8.9.0` 이상의 Node.js가 설치되어 있어야 합니다.
## 설치
Nest CLI를 사용하여 새 프로젝트를 설정하는 것은 매우 간단합니다. npm을 설치하면 OS 터미널에서 다음 명령을 사용하여 새 Nest 프로젝트를 만들 수 있습니다.
```shell script
$ npm i -g @nestjs/cli
$ nest new project-name
```

프로젝트 디렉토리가 생성되면, 노드 모듈과 상용구 파일이 설치되며, `src/` 디렉토리가 생성되어 여러 코어 파일로 채워집니다.
```
src
 ├── app.controller.ts
 ├── app.module.ts
 └── main.ts
```

### 파일 살펴보기
핵심 파일에 대한 간략한 개요는 다음과 같습니다.

| `app.controller.ts` | 단일 경로의 기본 컨트롤러 샘플                                                                          |
| `app.module.ts`     | 응용 프로그램의 루트 모듈입니다.                                                                        |
| `main.ts`           | 핵심 함수 NestFactory를 사용하여 Nest 애플리케이션 인스턴스를 작성하는 애플리케이션의 엔트리 파일입니다 |

`main.ts`에는 비동기 함수가 포함되어있어 응용 프로그램을 **부트 스트랩**합니다.
```typescript

import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();
```

Nest 애플리케이션 인스턴스를 작성하기 위해 핵심 `NestFactory` 클래스를 사용합니다. `NestFactory`는 애플리케이션 인스턴스를 생성 할 수있는 몇 가지 정적 메서드를 제공합니다. `create()` 메소드는 `INestApplication` 인터페이스를 수행하는 애플리케이션 오브젝트를 반환합니다. 이 객체는 다음 장에서 설명하는 메소드를 제공합니다. 위의 `main.ts` 예제에서 HTTP 리스너를 시작하면 응용 프로그램이 인바운드 HTTP 요청을 기다릴 수 있습니다.

Nest CLI로 생성된 프로젝트는 권장하는 디렉토리 구조를 갖는 초기 프로젝트 구조를 만듭니다.

## 플랫폼
Nest는 플랫폼에 구애받지 않는 프레임 워크가되는 것을 목표로합니다. 플랫폼 독립성을 통해 개발자는 여러 유형의 응용 프로그램에서 활용할 수있는 재사용 가능한 논리적 부분을 만들 수 있습니다. 기술적으로 Nest는 어댑터가 생성되면 모든 Node HTTP 프레임 워크와 작동 할 수 있습니다. 기본적으로 지원되는 HTTP 플랫폼인 [**express**](https://expressjs.com/)와 [**fastify**](https://www.fastify.io/)가 있습니다. 필요에 따라 적절한 플랫폼을 선택하세요.
| `platform-express` | Express는 노드에 대한 잘 알려진 미니멀한 웹 프레임워크입니다. 커뮤니티에서 구현한 많은 리소스를 갖추고 있고, 매우 많이 테스트 된 프로덕션용 라이브러리입니다. `@nestjs/platform-express` 패키지가 기본적으로 사용됩니다. 많은 사용자가 Express를 사용하고 있으므로이를 활성화하기 위해 별 다른 조치를 취할 필요가 없습니다. |
| `platform-fastify`     | Fastify는 최대 효율과 속도를 제공하는 것에 중점을 둔 고성능이며 오버헤드가 낮은 프레임워크입니다. 사용 방법은 [여기](https://docs.nestjs.com/techniques/performance)에 있습니다. |

어떤 플랫폼을 사용하든 자체 애플리케이션 인터페이스를 제공합니다. 각각 `NestExpressApplication` 및 `NestFastifyApplication`으로 표시됩니다.

아래 예제와 같이 `NestFactory.create()` 메서드에 형식을 전달하면 `app` 객체에 특정 플랫폼에서만 사용할 수 있는 메서드가 있습니다. 그러나 기본 플랫폼 API에 실제로 액세스하지 않는 한 **유형을 지정할 필요가 없습니다.**

```typescript
const app = await NestFactory.create<NestExpressApplication>(AppModule);
```

## 애플리케이션 시작
설치 프로세스가 완료되면 OS 명령 프롬프트에서 다음 명령을 실행하여 인바운드 HTTP 요청을 수신하는 애플리케이션을 시작할 수 있습니다.
```shell script
$ npm run start
```
이 명령은 `src/main.ts` 파일에 정의 된 포트로 수신하는 HTTP 서버를 시작합니다. 응용 프로그램이 실행되면 브라우저를 열고 `http:// localhost:3000/`로 이동하세요. `Hello World` 메시지가 보일 것입니다!

## 도움 주기
Nest는 MIT 라이센스인 오픈소스 프로젝트입니다. 이 멋진 사람들의 지원 덕분에 성장할 수 있습니다. 가입하려면 [여기](https://docs.nestjs.com/support)를 참조하십시오.
