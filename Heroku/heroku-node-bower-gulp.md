# Heroku에 Node.js 배포하면서 bower 설치하고 gulp 빌드하기

1. gulp를 보통 devDependencies에 추가하므로 Heroku에서 config variable로 `NPM_CONFIG_PRODUCTION = false`를 추가해준다.

2. `package.json`에서 다음과 같이 빌드 스크립트를 추가해준다

```
"scripts": {
  "postinstall": "./node_modules/bower/bin/bower install && npm run build",
  "build": "gulp build",
  "start": "node ./server.js"
},
```
