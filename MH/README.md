# Mobile-Devepment-Guide

## 门户 | Guide

### 开发基准
**简明，模式 | simple , pattern**
    
    简明：代码简单，清晰明白
    模式：松耦合，积木化


### 开发方案选择：

    00. 项目代码以简单易懂为主，方便他人维护
          避免过分追求技术陷阱，造成学习成本以及维护成本变大
          避免技术架构深度耦合，比如不合时宜的使用前台MV*
          推荐：考虑实际项目和人员情况，制定更佳的方案，not best but better

    01. 触屏页面结构保持简单
          避免过度深度交互和深度嵌套，坏例如2014触屏改版的侧边导航
          推荐：轻UI交互，重内容，高UI交互推荐迁移至app应用

    02. 页面同样保持简单
          避免内容堆砌
          推荐合理的阅读密度，手持设备相对PC识别区域变小

    03. 页面上尽量保持一条css和一条script引用

    04. 页面上不直接放JS code，使用引用的方式，同时注意压缩
          后端使用include后端合并标签压缩
          前端自行uglifyjs压缩
    05. 图片合并，可以雪碧图的必须
    06. css推荐sass和compass，可自动合成雪碧图
    07. 了解seo，爬虫等基本概念
    08. 实现非SEO需求时，尽量使用后端接口
    09. 业务或非业务插件开发
          开发角度：需要给第三方使用，考虑开源，长期维护
    10. 尽量为逻辑思考点等注释
    11. 尽量适时重构或梳理关键方法和项目逻辑
    12. 新技术试点一般以专题为佳，快速小巧


### 开发思路流程举例

    00. 梳理需求和制定实现方案
    01. 代码实现 code implement
    02. 代码检查 code review
    03. 代码测试 code test


### 库：

    zepto 使用中
    地址： http://zeptojs.com/
    jquery 2.0+


### UI组件：

    推荐门户自己的MU组件，自己维护，自己测试，自己更新
    地址：https://github.com/Roeis/MU
    包含轮播，弹窗，页面转场等



### 工具方法：

    underscore
    地址：http://underscorejs.org/
    mu组件中util对象，mu.uitl
    地址：https://github.com/Roeis/MU/tree/master/samples/util



### 事件：

    mu.touch 触屏事件， 兼容PC端
    tap, longTap, swipeLeft, swipeRight, swipeUp, swipeDown
    地址：https://github.com/Roeis/MU/tree/master/samples/touchevent




### 微信交互：

    url : http://common.hjfile.cn/js/hj-weixin-2.0.js
    使用方法：http://st.hujiang.com/topic/162110742385/
    和微信验证: wxshare.config();
    自定义分享: wxshare.reset(wx_data);

    自定义分享应用场景：
    改变用户分享内容，比如贺卡，将信息添加至URL传递，客户端根据url的query做


### cookie：
![Build Status Matrix](https://camo.githubusercontent.com/c070f264c7ffddee9fe85845d1180717059ebfa3/68747470733a2f2f73617563656c6162732e636f6d2f62726f777365722d6d61747269782f6a732d636f6f6b69652e737667)

    cookie操作，统一引用js.cookie.js
    地址：https://github.com/js-cookie/js-cookie

    Cookies.set('name', 'value', { expires: 7, path: '' });
    Cookies.get('name'); // => 'value'
    Cookies.remove('name');


### localstorage：

    使用前判断是否隐身状态
    场景：ios safari等



### 横竖屏判断：



### 模板：

    dot 使用中
    地址：http://olado.github.io/doT/
    _.template
    ejs



### 编写规范：

    符合一般主流规范；
        tab推荐空格；
        单双引号保持单文件统一即可；
        使用JShint保持校验；
        等等；


### 工作流：

    处理自动压缩，打包，合并，雪碧图等
    Grunt  使用中
    webpack



### 业务插件举例：

    //单个业务插件举例
    var core = {
        init: function(){
            //初始化    
        },
        bindEvent: function(){
            //绑定事件
        },
        getData: function(){
            //获取数据
        },
        renderHtml: function(){
            //渲染拼接
        },
        doFunctionA: function(){},
        doFunctionB: function(){},
        doFunctionC: function(){}
    };


