

# 接入流程

1.申请接入权限 ------>  2.获取上链凭证 ------> 3.上链数据签名  ------> 4.发起数据上链  ------> 5.受理上链 


# 申请接入权限
<a href="http://portal.hunan.com.cn/index">在中芯区块链（长沙）公共服务平台</a>，进行企业注册后联系平台获得区块链的接入权限。在后续的业务对接中将会对用户的接入权限进行验证；请妥善保管。同时获得接入权限后将获得详细的对接文档。平台注册地址：http://portal.hunan.com.cn/index

# 获取上链凭证
针对每次的上链行为，平台会发放允许请求的凭证；凭证只允许使用一次，时效5分钟；过时需重新获取。

api:
  queryCertificate

input:
   appid
   appsecret

output:
   certificateCode

# 上链数据签名
上链数据需要严格按照格式要求进行签名。

api:
   signData
   
input:
   certificateCode
   jsonData

output:
   hexSignData

# 发起数据上链
只有签名后的数据可发起上链请求，未经签名的数据视为无效请求。

api:
   sendCochain
   
input:
   appid
   appsecret
   hexSignData

output:
   resultHexString

# 受理上链
平台进行身份、签名校验后受理上链请求。

