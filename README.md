## 那些年遇到的Bug
- IE11问题：
  - Vue组件的循环渲染`v-for`调用appendToChild方法的时候会导致svg丢失的问题。解决办法：remove掉这段dom然后手动插入。
  - IE11虚拟机调试问题：如果静态资源cdn是假的https证书（调试的时候会将cdn换成本地的静态资源，所以是假的证书），需要再同一个标签页下先打开静态资源，同于安全策略之后,再在同一个标签页下打开网址即可正常加载静态资源。
  - Vue2的组件渲染问题：当一个页面有多个组件的时候，尽量使得Vue绑定的el的范围尽量小，避免使得其他组件无法渲染出来。
  - SVG Element 在IE环境下没有`innerHTML`和`outerHTML`属性
- Firefox问题：
  - Firefox会将html内的多个空格去除，chrome会将多个空格保留成一个，所以在需要空格调整的样式的时候请使用&nbsp;
  - Firefox上button内部的元素无法产生hover状态（button内部有一个icon,hover这个icon会出现说明，firefox会失效）。解决办法：不使用button标签
