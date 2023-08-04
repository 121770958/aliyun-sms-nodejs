# AliyunSms
阿里云邮件发送SDK

### Usage
```bash
npm i aliyun-sms-nodejs
```

```javascript
const AliyunSms = require('index')

const aliyunSms = new AliyunSms(AccessKeyId, AccessKeySecret)

本sdk所有参数可以看官方api进行设置，设置opt属性即可
```

单个短信推送
```javascript
aliyunSms.sendSms(opt)          =>  此函数为返回值为 Promise

opt = {
      PhoneNumbers: '',
      SignName: '',
      TemplateCode: '',
      TemplateParam: `{"code": ${12345}}`
}    其他参数 都是默认值，如果想自己设置，可以传入opt对象属性中

```


查看发送详情

```javascript
aliyunSms.querySendDetails(opt)       =>  此函数为返回值为 Promise
opt= {
         PhoneNumber: '130XXXXXXXX',
         SendDate: 'SendDate',
         PageSize: 10,
         CurrentPage: 0,
         BizId: '5131212'
     }      其他参数 都是默认值，如果想自己设置，可以传入opt对象属性中
```

批量发送短信

```javascript
aliyunSms.sendBatchSms()                =>  此函数为返回值为 Promise

opt = {
          PhoneNumberJson: ['15000000000', '15000000001'],
          SignNameJson: ['云通信', '云通信'],
          TemplateCode: 'SMS_001',
          TemplateParamJson: [{'code':'1234','product':'ytx1'},{'code':'5678','product':'ytx2'}],
      }

```
### new AliyunSms(AccessKeyId,AccessKeySecret)

  - `AccessKeyId` \<string\> 必填，阿里云颁发给用户的访问服务所用的密钥ID。
  - `AccessKeySecret` \<string\> 必填，AccessKeySecret

构造方法，传入配置对象。

```javascript
const AliyunSms = require('aliyun-sms-nodejs')

const aliyunSms = new AliyunSms(AccessKeyId, AccessKeySecret)
```



