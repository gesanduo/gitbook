
### 引用

```javascript
先下载aiplatwechat-js-sdk.js
然后import Client from 'aiplatwechat-js-sdk.js'
```
### 使用

```javascript
先初始化实例：
let client = Client.create({
  accessKey: 'your accessKey',// 必须
  secretKey: 'your secretKey',// 必须
  host:'your host'，// 非必须
})

//快速翻拍识别接口：
client.fastFakePhoto({
  account:"your account",
  imgUrl:"", //与imgBase64Data 二选一
  imgBase64Data:"",//与imgUrl 二选一
  options:{}    //额外参数，以对象形式放在options
}).then((res)=>{
  //调用成功
  console.log(res);
},(err)=>{
  //调用失败或超时
  console.log(err)
})

```
### 通用的参数
单个图片的都是用imgUrl或者imgBase64
数组的图片都是用imgUrls

### 接口参数如下
1. syncDetect：获取货架，冰柜，水堆识别结果

参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrl| String | - | 跟imgBase64二选一 | 识别的图片
imgBase64| String | - | 跟imgUrl二选一 | 识别的图片
type| String | shelf | true | 识别的类型可选值是（shelf 货架,freezer 冰柜,box 水堆）
options| Object|{}|false|额外参数

2. invoiceAuthenticityDetect:发票验真

参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrl| String | - | 跟imgBase64二选一 | 识别的图片
imgBase64| String | - | 跟imgUrl二选一 | 识别的图片
options| Object|{}|false|额外参数

3. invoicePlaceDetect：发票场景检测

参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrl| String | - | 跟imgBase64二选一 | 识别的图片
imgBase64| String | - | 跟imgUrl二选一 | 识别的图片
options| Object|{}|false|额外参数

4. firstFace：初次新增人脸数据

参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrl| String | - | 跟imgBase64二选一 | 识别的图片
imgBase64| String | - | 跟imgUrl二选一 | 识别的图片
idcardName| String|-|true|用户名   
idcardNumber| String|-|true|身份证号  

5. faceVerify：人脸对比

参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrl| String | - | 跟imgBase64二选一 | 识别的图片
imgBase64| String | - | 跟imgUrl二选一 | 识别的图片
personId| String|-|true|新增人脸数据时返回的对比id

6. imageQualityDetect：图片质量检测（是否倾斜清晰）
  
参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrl| String | - | 跟imgBase64二选一 | 识别的图片
imgBase64| String | - | 跟imgUrl二选一 | 识别的图片
options| Object|{}|false|额外参数

7. pictureCheck：图片查重

参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrls| Array | - | true | 图片数组
threshold|Number| - | false| 阈值

8. mergeImage：图片拼接
  
参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrls| Array | - | true | 图片数组

9. mergeImageInfo：获取图片拼接结果
  
参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
mergeId| String | - | true | mergeImage返回的mergeId

10. imageCompare:重复图片筛选

参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrls| Array | - | true | 图片数组

11. storeHead：店头识别
 
参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrl| String | - | 跟imgBase64二选一 | 识别的图片
imgBase64| String | - | 跟imgUrl二选一 | 识别的图片
options| Object|{}|false|额外参数    
options.storeName| String|-|true|门店名称    
options.storeShortName| String|-|true|门店简称    

12. businessLicense:营业执照检测

参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrl| String | - | 跟imgBase64二选一 | 识别的图片
imgBase64| String | - | 跟imgUrl二选一 | 识别的图片
options| Object|{}|false|额外参数       

13. fastFakePhoto:快速翻拍检测
 
参数名 | 类型 | 默认值 | 是否必须 | 描述
---|---|---|---|---|
account| String | - | true | 租户
imgUrl| String | - | 跟imgBase64二选一 | 识别的图片
imgBase64| String | - | 跟imgUrl二选一 | 识别的图片
options| Object|{}|false|额外参数