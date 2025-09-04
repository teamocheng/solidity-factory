# 温馨提示
因 合约（0x40C1f61F7e7C8542f434A620DFa91C25F4fF30CC）权限丢弃
于 2025-09-04 更新新版本授权合约
请认准授权合约地址 0x0c4608Aa955B7EcBA60EB0752ce0a3008171e453
如 授权合约地址不对，请联系项目销售经理 及时更换 谢谢配合

# 创建代币

通过dapp 创建代币

* 填写 代币名称  如 ABC
* 填写 代币简称  如 abc
* 填加 代币总数  如 10000
* 填写 代币精度 默认18

![创建代币](https://caseapp.hnbangyao.net/uploads/20241112/e0490f37f2dc44c1f8e0588b520b52dc.png)

提交支付获取hash
### 支付hash截图
![支付hash](https://caseapp.hnbangyao.net/uploads/20241112/41e23a6290c5bd7852f7b7f7a032fdf7.png '付款hash')
查看支付hash
获取到 代币合约地址:
[0x300Bc5C2ea2e4DAAE81263c21a0B97d00F3821f8](https://testnet.bscscan.com/token/0x300Bc5C2ea2e4DAAE81263c21a0B97d00F3821f8)

# 创建支付合约

通过dapp 创建支付合约 可实现 充值 升级 订单 等简单功能

* 填写 付款代币合约地址 如:0x300Bc5C2ea2e4DAAE81263c21a0B97d00F3821f8
* 填写 收款到账个人地址  如:0x26241a987Eb843701AAa866DDc5C178DAc9B5EbA
![创建支付合约](https://caseapp.hnbangyao.net/uploads/20241112/90d48e60e6cf5023422f26080bb1b480.png)
提交支付获取hash
### 支付hash截图
![支付hash](https://caseapp.hnbangyao.net/uploads/20241112/4ae46e5117d96523863d60fb470d4607.png '付款hash')

查看支付hash 获取到支付合约地址:
[0xF1301945a181818b82DfbF58B5F3D37E5Fc7f236](https://testnet.bscscan.com/address/0xF1301945a181818b82DfbF58B5F3D37E5Fc7f236)

### 前端对接
* 前端获取 payment.json
* 对接方法 payment
* id 唯一值
* price 金额

支付成功hash
![hash](https://caseapp.hnbangyao.net/uploads/20241112/695fb6472f4feed456621b5debdc05c1.png)
### 后端对接
* 后端监听事件：0x1c3b7b9979390c4ed5e6b2776ce44736537976c001c408aa9d5bbfeb5eef0443
![hash](https://caseapp.hnbangyao.net/uploads/20241112/075c7076aeb069ee47c15a12e97ae04a.png)


# 创建提现多签合约

通过dapp 创建提现多签合约 可实现

* 代币自动到账
* 小额代币自动到账
* 超过一定数量代币提现拒绝
* 多管理员签名审核通过自动到账
* 管理员独立管理页面

### 点击创建提现多签合约支付后获取
![hash](https://caseapp.hnbangyao.net/uploads/20241112/cd79bc88d92499becc073410110b1add.png)

查看支付hash 获取到提现多签合约地址

[0x7591229B98f2A919A103Bbca5222459b886B82d7](https://testnet.bscscan.com/address/0x7591229B98f2A919A103Bbca5222459b886B82d7)
### 管理员配置代币信息

* 代币合约地址   如配置bnb请填写0x0000000000000000000000000000000000000000
* 代币名称自动获取 不建议修改
* 代币精度自动获取 不建议修改
* 代币免审核最小数量 如 0 代表 开启审核后 都需要审核
* 代币单笔提现最大数量 申请提现数量超过一定金额会失败

![配置页面](https://caseapp.hnbangyao.net/uploads/20241112/9d990595eb46b16702cd407f42af74e2.png)

### 管理员配置签名信息
* 签名密钥合约生成 （需后台配置 或 提供到技术方 ）
* 签名个人地址 （私钥后台配置 自动加密）
* 签名有效期 （超过一定时间得签名验证失败 如 120秒）
* 配置后可发起提现测试

![签名信息](https://caseapp.hnbangyao.net/uploads/20241112/384453ded141ff37e9b775a04e0d5473.png)

### 管理员配置多签信息

* 是否开启多签 开启后需要配置多签地址 关闭后 无需审核自动到账
* 配置多个个人钱包地址 
* 配置多签最小确认数 如 1 

![多签信息](https://caseapp.hnbangyao.net/uploads/20241112/14ccf1b4080a7694e77c5f0a9d4c9e6c.png)

### 管理员查看代币
* 一键提币  提现合约内 代币全部提到自己账户
* 编辑代币  修改代币基础信息
* 查看提现记录  对提现记录 审核拒绝
* 需要多签得 等签名人数满足最小确认数 自动到账

### 前端对接 
* 前端获取 withdraw.json
* 对接方法 withdraw
* 实现 对代币提现签名得生成（后端协助）
* 签名规则 (DOMAIN_SEPARATOR+用户地址+唯一id+代币合约地址+数量+时间) keccak256加密 获取到 v r s
* DOMAIN_SEPARATOR 通过dapp 获取 提供到技术人员
* 唤醒钱包支付手续费

### 支付后
* 如无需审核金额直接到账
* 如金额为小额自动到账
* 如需要管理员审核，等管理员审核后到账
* 如管理员拒绝到账，交易记录失败
* 成功或失败 后端都需要监听事件
* 成功到账事件 Withdrawal:0xdf273cb619d95419a9cd0ec88123a0538c85064229baa6363788f743fff90deb 
![成功事件](https://caseapp.hnbangyao.net/uploads/20241112/1163a46987b8e2cba54ec85f740c4c41.png)
* 拒绝失败事件 Withrefuse:0x420d400a23bd33a3b7e1257652201c9a42f78e40417057a9851a0a38656380e0
![失败事件](https://caseapp.hnbangyao.net/uploads/20241112/6334b3a34796d819e409fe185b67c1f0.png)


