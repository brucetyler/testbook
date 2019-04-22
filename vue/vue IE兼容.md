`IE不兼容es6`

`所以npm install babel-polyfill`

`在main.js中引入 import 'babel-polyfill'`

`在webpack.base.conf.js配置文件中将 app:"./src/main.js" 改为app:['babel-polyfill','./src/main.js']`

```

```

`关于新请求fetch的IE兼容：`

`npm install isomorphic-fetch`

`并在main.js中引入 import 'isomorphic-fetch';`

