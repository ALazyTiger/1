## 前端文档及其使用说明

pigx-ui 前端基于 element、avue 混开完成，同时兼容 element、avue 的功能.

推荐复杂表单直接使用 element 开发, avue 在复杂界面配置较为复杂且渲染速度较慢

vue 文档： https://cn.vuejs.org/

avue 文档： https://avuejs.com/

element-ui 文档： https://element.eleme.cn/#/

avue 文档： https://avuejs.com/

## 前端目录结构说明

pigx-ui  -- UI工程  
├── public -- 静态资源  
├    └── cdn -- 伪CDN  
├    └── img -- 图片资源  
├    └── svg -- SVG资源  
├    └── util -- 网上下载的工具  
├    └── favicon.ico -- 网站图标  
├    └── index.html -- 网站首页，也是唯一的一张页面   
├── src -- 源码目录  
├    └── api -- 和后端交互的API相关  
├    ├── components -- 自己封装的组件  
├    ├── config -- 工程配置  
├    ├── const -- 常量  
├    ├── docker -- docker部署相关  
├    ├── filters -- 全局过滤器  
├    └── mixins -- VUE组件混入  
├    └── page -- 页面组件  
├    └── route -- VUE-Router相关  
├         └── page -- 页面路由  
├         └── views -- 业务路由  
├         └── avue-router.js --自定义路由处理，包括路由拦截，动态路由等  
├         └── axios.js --axios增强  
├         └── route.js --路由配置入口  
├    └── store -- VUEX相关  
├    └── styles -- 样式管理  
├    └── util -- 工具包  
├    └── views -- 业务代码  
├    └── App.vue -- 根组件  
├    └── error.js -- 自定义错误日志处理  
├    └── main.js -- 入口js  
├    └── permission.js -- 权限判断，导航守卫  
├── .browserslistrc -- barbel兼容配置  
├── .editorconfig -- 开发组统一环境配置  
├── .editorconfig -- ESLint配置  
├── .gitignore -- git忽略列表  
├── .postcssrc.js -- CSS预处理配置  
├── babel.config.js -- barbel配置入口  
├── package.json -- 依赖管理  
├── vue.config.js -- vue cli3的webpack配置  

## 部署说明

vue.config.js中开启了gzip压缩，且deleteOriginalAssets 为 true ，删除了原文件，所以部署时，nginx.conf 需要加如下配置:

gzip on;
gzip_static on; 

nginx 会优先匹配你的 gzip 文件来返回，如果没有就寻找相应资源进行 gzip 压缩再返回。
