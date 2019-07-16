## Init

#### Vue 프로젝트 생성

Vue Cli 3 를 이용해서 프로젝트를 생성한다.

(기본적으로 npm 을 이용한 기본적인 플러그인은 설치했음)

```shell
vue create frontend
```

사용자 정의 템플릿은 기본으로 셋팅한다.



#### Vue 프로젝트의 생성위치

형상관리 및 FrontEnd 배포에 조금 편의성을 두기위해 Spring Boot 프로젝트를 최상의 Root 로 정의하여 

하위 경로에 Vue 프로젝트를 이동하도록 한다.

```
vueboot/
		frontend/
		src/
		gralde/
		...
```



#### 최초 실행

```shell
npm run serve
```



#### Spring Boot 에서 실행

Webpack 모듈러를 이용하여 build 하여 나온 정적 파일들을 Spring Boot 에서 실행하여 결과물을 확인.

build output 경로를 Spring Boot Templeate ( tymeleaf 기분 ) 가 인식할 수 있는 경로로 지정해줘야 한다.

```js
// vue.config.js
module.export = {
    assetsDir: 'assets',
    outputDir: '../src/main/resources/static/',
    indexPath: '../templates/index.html',
}
```



이후 빌드

```bash
# build 
npm run build
```

