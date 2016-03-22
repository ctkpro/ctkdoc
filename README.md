# ctkdoc
This is the documentation for CTKPro

## table of contents
- [DesignPattern](#DesignPattern)
- [Git](#Git)
- [Javascript](#Javascript)
- [ReactJs](#ReactJs)
- [AWS](#AWS)
- [UserCenteredDesign](#UserCenteredDesign)


<a name="DesignPattern"/> 
## Design Pattern
- [CTKPro Design Patterns](https://github.com/ctkpro/ctkdoc/blob/master/designPattern/README.md)

<a name="Git"/> 
## Git
- [CTKPro git 使用流程](https://github.com/ctkpro/ctkdoc/blob/master/git/git.md)

<a name="Javascript"/> 
## Javascript

### NodeJS 經驗談
- 機器的memory一定要夠大(4 GB), install或執行時才不會有問題，如果遇到很不一定發生的問題，可以檢查memory的使用率

### NodeJS coding style
- [npm-coding-style](https://docs.npmjs.com/misc/coding-style)
- [Felix's Node.js Style Guide](http://nodeguide.com/style.html)

<a name="ctkproJsCodingStyle"/>
綜合上面2個建議使用如下：

##### 程式一行長度
一行不要超過80個字

##### code indent (程式縮排)
2個space
  
##### 大括弧 **{**
正確：放在後面，不要放新的一行

```
function () {
```

錯誤：

```
function ()
{
```

##### Quotes (單引號)
使用單引號，除了JSON以外
正確

```
var foo = 'bar';
```

錯誤

```
var foo = "bar";
```

##### 命名規則
- 使用 **lowerCamelCase** 在 objects, functions, methods, properties, 還有以下沒有被敘述到的東西
- 使用 **UpperCamelCase** 在 class names (things that you'd pass to "new").
- 使用 **all-lower-hyphen-css-case** 在 filenames and config keys.
- 使用 **CAPS_SNAKE_CASE** 在 constants, things that should never change and are rarely used.

### ES6
- [ES6語法 update (udemy課程分享)](https://docs.google.com/document/d/19ZutRGjnaNQRyRhmkwNnowRTKbpKjYx9h4xtGdxNVhA/edit)

<a name="ReactJs"/> 
### ReactJs
- [谷阿莫 ReactJs 心得分享](https://docs.google.com/presentation/d/1POeCgM8PEGUTV88zq0xAF93FMIVABiI3J1MfvWJsn3I/edit?usp=sharing)  

>  包含udemy(React+Flux)的課程，youtube的GraphQL, Relay  

- [必看!!非常好的redux的introduction (由redux神人錄製)](https://egghead.io/lessons/javascript-redux-the-single-immutable-state-tree)
- [必看!!Redux搭配React運用](http://chentsulin.github.io/redux/docs/basics/UsageWithReact.html)：這篇有講到Container 和 Presentational Components的觀念
- [Redux gitbook的中文化版本](http://chentsulin.github.io/redux/docs/advanced/index.html)
- [Dan Abramov - Live React: Hot Reloading with Time Travel at react-europe 2015 (redux神人demo)](https://www.youtube.com/watch?v=xsSnOQynTHs)
- [Relay and GraphQL Introduction Materials](https://quip.com/oLxzA1gTsJsE)
- [Redux簡介 (中文)](http://huli.logdown.com/posts/294037-javascript-redux-basic-tutorial)
- [Redux使用範例](http://chentsulin.github.io/redux/docs/introduction/Examples.html#real-world): 這裡有很多實用的範例可以直接從source code看實作

<a name="AWS"/> 
## AWS
- [CodeDeploy](https://github.com/ctkpro/ctkdoc/tree/master/AWS/CodeDeploy)
- [API Gateway](https://github.com/ctkpro/ctkdoc/tree/master/AWS/API%20Gateway)

<a name="UserCenteredDesign"/> 
## User Centered Design
- [20160322 User Data Analyze](https://slack-files.com/T02ULH856-F0U5L5DQ8-151d13ae57)