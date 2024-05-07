# amazon-sp-api
## 一：什么是SP-API
Selling Partner API简称SP-API，是2020年10月亚马逊正式推出的一套全新的卖家服务API。SP-API的前身是MWS API，即Marketplace Web Service接口。在SP-API发布之前，MWS已经使用有超过10年的历史。今后将由SP-API接力成为亚马逊卖家服务的支柱，MWS则将退出历史舞台。


## 二：SP-API作用
SP-API提供了程序化的方式帮助亚马逊卖家优化业务流程，提高运营效率。目前主要以软件服务商(ISV)通过SP-API为亚马逊卖家提供服务为主; 同时为一些具备软件开发能力的大卖家通过SP-API对接自己内部系统以提高运行效率。


## 三：SP-API开通流程和部分使用参考
如何对接亚马逊电商Selling Partner API：https://aws.amazon.com/cn/blogs/china/how-to-connect-with-amazon-e-commerce-selling-partner-api/

创建SP-API第三方登录应用并完成API Call: https://aws.amazon.com/cn/blogs/china/create-sp-api-third-party-login-application-and-complete-api-call/

SP-API 中 Notifications API 结合 Amazon SQS 使用的详细教程：https://aws.amazon.com/cn/blogs/china/detailed-tutorial-on-the-use-of-notifications-api-in-sp-api-with-amazon-sqs/

SP-API 中 Notifications API 结合 Amazon EventBridge 使用的详细教程：https://aws.amazon.com/cn/blogs/china/detailed-tutorial-on-the-use-of-notifications-api-with-amazon-eventbridge-in-sp-api/

## 四：SP-API SDK接口文档
python: https://python-amazon-sp-api.readthedocs.io/en/latest/index.html

## 五：SP-API Section的功能基本介绍
### A+ content API
为品牌化，精细化运营店铺商品的Listing而设计。卖家可以通过A+ content API向其所属的亚马逊商品Listing页面（产品详细页面）添加丰富的营销内容。A+ 内容帮助销售合作伙伴分享品牌和产品故事，帮助买家做出明智的购买决定。 可以从内容模块中选择添加图像和文本以组合内容形式进行上传。

### Authorization API
通过Authorization接口可以把已经完成MWS授权的卖家MWS token换为SP-API的身份认证，从而调用SP-API的其他各个接口，避免卖家进行二次授权。需要注意的是SP模式或混动模式App需要已完成发布才能调用。

### Catalog Items API
可用来查看各个Catalog下面ASIN商品信息。V1接口支持对于商品进行亚马逊目录中信息的访问查询搜索。

### Feeds API
用来上传各种数据信息，例如：上传商品Listing信息，修改库存数量，修改商品价格，上传商品图片，批量上传各种音视频流媒体文件，取消订单，请求退款等。目前已支持通过json格式进行Listing商品的feed请求。

### Uploads API
Uploads API 允许您上传数据为其他SP-API所使用(Messaging API, A+ Content API)。由于当我们上传相对较大的数据时，基于HTTP的最大传输数据大小的限制，可以通过Uploads API先把数据传输到S3中，借助S3的扩展能力，从而实现上传无限大的数据(<5TB)。

### Finance API
Finance API可帮助您获取与业务相关的财务数据。 您可根据指定订单、或指定财务事件组或日期范围的方式来获取财务事件数据。

### Messaging API
可通过Messaging API给买家发送消息。

### Notification API
可通过Notification API进行消息订阅，可以减少请求的频次，待任务完成，即会接受到消息通知提醒。这种做法可以避免传统的通过轮询方式拉取数据：占用网络请求资源，造成资源浪费，影响thottling效率。

### Orders API
通过Orders API可以拉取一定时间内的所有订单，根据订单ID可以拉取该订单的详细数据。

### Product Fees API
可根据SKU或ASIN获取出售该商品的预计手续费。

### Product Pricing API
可以获取卖家当前在售商品的价格信息，及其他卖家出价信息等。

### Reports API
可以生成并获取数据报告。例如：订单报告，库存报告，退货报告，财务报告等。

### Sales API
可以获取以指定期间范围内，销售业绩为基准的销售表现数据。

### Sellers API
可以获取卖家在当前Region(Endpoint)各个站点下的卖家身份信息及其活跃状态。

### Service API
可根据Service API来获取和修改Service提供商的Service订单(这种情况下，服务本身就是亚马逊商品，即非实体商品)。

### Shipping API
Ship with Amazon功能相关的API服务。

### Shipping Invoicing API
仅限Brazil站点，可用来检索亚马逊物流 (FBA) 订单的货件发票信息。

### Solicitations API
Solicitations API用来向买家发送不敏感的邀请，例如请求买家在商品购买后进行评价等。

### FBA Inventory API
返回当前FBA库存商品的概要信息一览。

### FBA Inbound Eligibility API
用于事先确认某指定商品在运送FBA仓库之前，该商品是否具备成为FBA商品的资格。

### FBA Small and Light
用于帮助卖家管理FBA小型轻量商品计划中的商品。

### Fulfillment Inbound API
用于将FBA商品发货到亚马逊FBA仓库。

### Fulfillment Outbound API
用于将FBA商品发货给多渠道配送(Multi-Channel Fulfillment)的订单。

### Merchant Fulfillment API
自发货卖家(MFN)通过Merchant Fulfillment API接口可购买发货单，用于自行向买家发货。

### Listing Items API
以SKU为单元(1by1), 可以创建、编辑和删除指定上架商品。

### Product Type Definitions API
用于搜索可用的商品类型，获取指定商品类型的必填字段/schma等。

### Tokens API
利用Tokens API通过卖家凭证可获取RDT(Restricted Data Token)凭证，从而利用RDT凭证获取PII数据。
