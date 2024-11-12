# 创建代币

通过dapp 创建代币

* 填写 代币名称  如 ABD
* 填写 代币简称  如 abc
* 填加 代币总数  如 10000
* 填写 代币精度 默认18

提交支付获取hash
## 支付hash截图
![支付hash](https://caseapp.hnbangyao.net/uploads/20241112/41e23a6290c5bd7852f7b7f7a032fdf7.png '付款hash')
查看支付hash
获取到 
[代币合约地址:0x300Bc5C2ea2e4DAAE81263c21a0B97d00F3821f8](https://testnet.bscscan.com/token/0x300Bc5C2ea2e4DAAE81263c21a0B97d00F3821f8)

# 创建支付合约

通过dapp 创建支付合约 可实现 充值 升级 订单 等简单功能

* 填写 付款代币合约地址 如:0x300Bc5C2ea2e4DAAE81263c21a0B97d00F3821f8
* 填写 收款到账个人地址  如:0x26241a987Eb843701AAa866DDc5C178DAc9B5EbA

提交支付获取hash
## 支付hasn截图
![支付hash](https://caseapp.hnbangyao.net/uploads/20241112/4ae46e5117d96523863d60fb470d4607.png '付款hash')
查看支付hash 获取到

[支付合约地址:0xF1301945a181818b82DfbF58B5F3D37E5Fc7f236](https://testnet.bscscan.com/address/0xF1301945a181818b82DfbF58B5F3D37E5Fc7f236)

前端获取 payment.json
对接方法 payment  
id 唯一值
price 金额
支付成功hash
![hash](https://caseapp.hnbangyao.net/uploads/20241112/695fb6472f4feed456621b5debdc05c1.png)

后端监听事件：0x1c3b7b9979390c4ed5e6b2776ce44736537976c001c408aa9d5bbfeb5eef0443
![hash](https://caseapp.hnbangyao.net/uploads/20241112/075c7076aeb069ee47c15a12e97ae04a.png)


# 创建提现多签合约
