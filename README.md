# notes
1，代码

使用严格模式：
在函数中添加 “use strict”; 声明，严格模式的说明见 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions_and_function_scope/Strict_mode

模块化：
每个模块来封装自己的方法实现，避免全局变量泄露，并且可以更好地组织代码接口，可以方便地按模块进行单元测试。
常用的模块加载器有：requires（requirejs.org），seajs（seajs.org)，browserify(browserify.org)等。

统一的编码规范：
如：Google Javascript Style Guide http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml

使用版本控制系统：
使用版本控制，方便多人合作。除了一些老的系统，基本上都是用 git，代码可以直接托管到github（http://jshint.com/)


2，文档
要把文档提高到和源码同样的重视程度。
写好函数的块级注释，然后可以使用 YUIDoc(http://yui.github.io/yuidoc/) 或者 JSDoc（http://usejsdoc.org/） 来生成API文档。
用 Markdown （http://daringfireball.net/projects/markdown/）来生成更详细更长的说明文档。


3，语法检查
使用 jsHint(http://jshint.com/), 或者 jsLint(http://jslint.com/)来检查代码。
这样可以非常有效的避免语法层面的错误，比如没有使用严格模式、忘记声明变量、括号不匹配等。

4，单元测试
前面提到了模块化，模块化好的代码可以非常容易按模块编写单元测试。
详尽的单元测试可以极大提升代码的健壮性。
可以用 jasmine（http://jasmine.github.io/）或者 Qunit(http://qunitjs.com/)等测试框架来编写单元测试。
有了单元测试之后，还可以使用BrowserStack（http://browserstack.com/）或者SauceLabs（http://saucelabs.com/）等工具在不同的浏览器下跑测试，JS的浏览器兼容性问题再也不用担心了。

5，Measure
不知道应该怎么翻译，“测量”？
可以使用代码覆盖工具检查单元测试的覆盖率，保证100%的单元测试覆盖率。
使用函数复杂性测试工具 http://netm.ag/halstead-249， 他可以通过检查函数体中包含的循环、分支、函数调用等来判断函数的复杂程度。复杂度越底的函数越容易理解和维护。命令行工具plato（http://github.com/es-analysis/plato）可以用来生成代码的复杂性报告，可以帮助判断哪些函数过于复杂需要优化。

6，自动化
基于Grunt的自动化构建。强大的Grunt可以实现几乎所有的构建操作，包括：生成文档、语法检查、合并编译压缩、单元测试、复杂性测试，甚至可以自动帮你刷新页面。有了grunt，在修改源码之外的操作全部可以自动化进行。
Grunt 官网：gruntjs.com

7，处理异常
使用 try catch来处理异常，确保非致命的错误发生时不会影响整个程序的运行。
