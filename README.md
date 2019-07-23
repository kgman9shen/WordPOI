# WordPOI

[![Download](https://img.shields.io/badge/download-jar-blue.svg)](https://raw.githubusercontent.com/jenly1314/WordPOI/master/libs/word-poi-1.0.0.jar)
[![Jitpack](https://jitpack.io/v/jenly1314/WordPOI.svg)](https://jitpack.io/#jenly1314/WordPOI)
[![License](https://img.shields.io/badge/license-Apche%202.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)
[![Blog](https://img.shields.io/badge/blog-Jenly-9933CC.svg)](https://jenly1314.github.io)
[![QQGroup](https://img.shields.io/badge/QQGroup-20867961-blue.svg)](http://shang.qq.com/wpa/qunwpa?idkey=8fcc6a2f88552ea44b1411582c94fd124f7bb3ec227e2a400dbbfaad3dc2f5ad)

WordPOI是一个将Word接口文档转换成JavaBean的工具库，主要目的是减少部分无脑的开发工作。

> 核心功能：将文档中表格定义的实体转换成Java实体对象
 
## WordPOI特性说明  
 1. 支持解析doc格式和docx格式的Word文档
 2. 支持批量解析Word文档并转换成实体
 3. 解析配置支持自定义，详情请查看{@link ParseConfig}相关配置
 4. 虽然解析可配置，但因文档内容的不可控，解析转换也具有一定的局限性

> 只要在文档上定义实体对象时，尽量满足示例文档的规则，就可以规避解析转换时的局限性。

## ParseConfig属性说明
| 属性 | 值类型 | 默认值 | 说明 |
| :------| :------ | :------ | :------ |
| startTable | int |0| 开始表格 |
| startRow | int |1| 开始行 |
| startColumn | int |0| 开始列 |
| fieldNameColumn | int | 0 | 字段名称所在列 |
| fieldTypeColumn | int | 1 | 字段类型所在列 |
| fieldDescColumn | int | 2 | 字段注释说明所在列 |
| charsetName | String | UTF-8 | 字符集编码 |
| genGetterAndSetter | boolean | true | 是否生成get和set方法 |
| genToString | boolean | true | 是否生成toString方法 |
| useLombok | boolean |false| 是否使用Lombok |
| serializable | boolean | false | 是否实现Serializable序列化 |
| showHeader | boolean | true | 是否显示头注释 |
| header | String | Created by WordPOI | 头注释内容 |


## 引入

### Maven：
```maven
<dependency>
  <groupId>com.king.poi</groupId>
  <artifactId>word-poi</artifactId>
  <version>1.0.0</version>
  <type>pom</type>
</dependency>
```
### Gradle:
```gradle
compile 'com.king.poi:word-poi:1.0.0'
```

### Lvy:
```lvy
<dependency org='com.king.poi' name='word-poi' rev='1.0.0'>
  <artifact name='$AID' ext='pom'></artifact>
</dependency>
```

###### 如果Gradle出现compile失败的情况，可以在Project的build.gradle里面添加如下：（也可以使用上面的GitPack来complie）
```gradle
allprojects {
    repositories {
        maven { url 'https://dl.bintray.com/jenly/maven' }
    }
}
```

## 引入的库：
```gradle
compile 'org.apache.poi:poi:4.1.0'
compile 'org.apache.poi:poi-ooxml:4.1.0'
compile 'org.apache.poi:poi-scratchpad:4.1.0'
```

如想直接引入jar包可直接点击左上角的Download下载最新的jar，然后引入到你的工程即可。

## 示例

代码示例 (直接在main方法中调用即可)
```Java
    //Word转实体对象,根据'.doc'或'.docx'自动判断文档格式
    WordPOI.wordToEntity("C:/Api1.docx","C:/bean/","com.king.poi.bean",config,"Result","PageInfo");
    //docx格式的Word文档转实体对象
    WordPOI.wordToEntity(Test.class.getResourceAsStream("Api1.docx"),false,"C:/bean/","com.king.poi.bean","Result","PageInfo");
    //doc格式的Word文档转实体对象
    WordPOI.wordToEntity(Test.class.getResourceAsStream("Api2.doc"),true,"C:/bean/","com.king.poi.bean","TestBean");

```

更多使用详情，请查看[Test](src/test/java/Test.java)中的源码使用示例或直接查看[API帮助文档](https://jenly1314.github.io/projects/WordPOI/doc/)

## 版本记录

#### v1.0.0：2019-6-12
*  WordPOI初始版本

## 赞赏
如果您喜欢WordPOI，或感觉WordPOI帮助到了您，可以点右上角“Star”支持一下，您的支持就是我的动力，谢谢 :smiley:<p>
您也可以扫描下面的二维码，请作者喝杯咖啡 :coffee:
    <div>
        <img src="https://jenly1314.github.io/image/pay/wxpay.png" width="280" heght="350">
        <img src="https://jenly1314.github.io/image/pay/alipay.png" width="280" heght="350">
        <img src="https://jenly1314.github.io/image/pay/qqpay.png" width="280" heght="350">
        <img src="https://jenly1314.github.io/image/alipay_red_envelopes.jpg" width="233" heght="350">
    </div>

## 关于我
   Name: <a title="关于作者" href="https://about.me/jenly1314" target="_blank">Jenly</a>

   Email: <a title="欢迎邮件与我交流" href="mailto:jenly1314@gmail.com" target="_blank">jenly1314#gmail.com</a> / <a title="给我发邮件" href="mailto:jenly1314@vip.qq.com" target="_blank">jenly1314#vip.qq.com</a>

   CSDN: <a title="CSDN博客" href="http://blog.csdn.net/jenly121" target="_blank">jenly121</a>

   博客园: <a title="博客园" href="https://www.cnblogs.com/jenly" target="_blank">jenly</a>

   Github: <a title="Github开源项目" href="https://github.com/jenly1314" target="_blank">jenly1314</a>

   加入QQ群: <a title="点击加入QQ群" href="http://shang.qq.com/wpa/qunwpa?idkey=8fcc6a2f88552ea44b1411582c94fd124f7bb3ec227e2a400dbbfaad3dc2f5ad" target="_blank">20867961</a>
   <div>
       <img src="https://jenly1314.github.io/image/jenly666.png">
       <img src="https://jenly1314.github.io/image/qqgourp.png">
   </div>

