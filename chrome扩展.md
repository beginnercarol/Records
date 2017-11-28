# chrome.devtools.network

最近写 chrome 扩展插件的时候,调用 network API ,出现了很多问题,记录一下,以免之后忘记.
参考资料:[Chrome Devpanel Extension Communicating with Background Page](https://stackoverflow.com/questions/11661613/chrome-devpanel-extension-communicating-with-background-page/11677744#11677744)

***

1. 在 `manifest.json` 中 增加一项: `"devtools_page" : "devtools.html”`
注意接下来要新建这个`devtools.html`文件,这个文件只有一个用处,就是在`<script>`标签中引入`devtools.js`(相应的也要新建 `devtools.js`) ;         
2. 在 `devtools.js` 中创建 panel
+ 在开发者工具中添加一个工具:
`chrome.devtools.panels.create("MyPanel","icon.png","Panel.html",function(panel){});`
+ `Panel.html`就是这个工具面板了,  在`<script>`标签中引入`Panel.js`,在这个 js 文件中定义的函数可以通过3中的方式在`devtools.js`中进行调用
3. `panel.onShown.addListener(callback(panelWindow))`
+ 当打开我们自定义的这个工具面板时 , onShown 触发,获取`Panel.html`页面的 `window`,并传入 callback 中;
+ 接下来可以在 callback 中对 panel 页面进行修改,显示数据,等等等操作       


***

[一个栗子](https://github.com/beginnercarol/Study-Record/tree/master/chrome-extension)










    