# 使用 MPChat 虚拟卡开通 Apify 服务的教程

## 开通前准备

1. 网络环境配置

   * 使用美国住宅 IP（重要成功因素）

   * 确保 IP 干净且地理位置显示为美国

2. MPChat 资金准备

   * 准备 50−150 等&#x503C;*&#x20;USDT*（入门计划 49/月起）

   * 建议多预留资金用于验证费用

3. 技术需求分析

   * 确定每月计算用量（计算单元）

   * 评估数据存储需求

   * 考虑代理使用需求

## 详细操作步骤

### 第一阶段：MPChat 虚拟卡准备

1. USDT 充值

```plain&#x20;text
操作路径：MPChat App → 钱包 → 存款
- 复制USDT充值地址
- 从外部钱包转入足额USDT（建议$100+）
- 等待网络确认到账
```

* 申请美国区 MPCard

```plain&#x20;text
操作路径：MPChat App → MPCard → 申请新卡
- 发行国家：必须选择"美国"
- 卡片类型：虚拟卡（即时生成）
- 安全记录卡号、有效期、CVV码
```

* 资金划转

```plain&#x20;text
操作路径：MPChat App → 钱包 → 划转
- 从：MP钱包（USDT）
- 到：MPCard（美元）
- 金额：$60-80（根据订阅计划调整）
```

### 第二阶段：Apify 账户注册

1. 访问官网注册

   * 使用美国 IP 访问 apify.com

   * 点击"Sign Up"或"Start Free Trial"

2. 选择订阅计划

1) 账户验证

   * 使用邮箱注册账户

   * 完成邮箱验证

   * 设置账户信息

### 第三阶段：支付信息填写

1. 支付界面导航

   * 登录后进入"Billing"页面

   * 点击"Upgrade Plan"或"Add Payment Method"

   * 选择订阅周期

2. MPCard 信息填写

```plain&#x20;text
信息源：MPChat App → MPCard → 卡片详情
- Card number: 16位虚拟卡号
- Expiration date: 有效期（MM/YY）
- CVV: 3位安全码
- Name on card: 建议使用拼音
```

* 账单地址填写（关键步骤）

  * Country: United States

  * 使用专业美国地址生成器

  * 示例格式：

```plain&#x20;text
Address Line 1: 1234 Crawler Street
City: San Francisco
State: CA
ZIP Code: 94102
Phone: 生成美国电话号码
```

## 支付验证与激活

1. 即时验证

   * Apify 会进行小额验证扣款（立即退还）

   * 验证卡片有效性和地址匹配度

2. 服务激活

   * 支付成功后，服务立即激活

   * 获得计算单元配额

   * API 令牌自动生成

3. 功能验证

   * 测试 Actor 运行功能

   * 验证数据存储

   * 检查代理设置

## Apify 套餐功能对比

## 故障排查指南

### 支付失败常见原因

1. 地区检测失败

   * 解决方案：使用美国住宅 IP，清除浏览器缓存

2. 地址验证严格

   * 解决方案：使用真实存在的美国地址

3. 账户验证

   * 解决方案：确保账户信息真实有效

### 服务激活问题处理

1. 扣款成功但服务未激活

   * 等待 5-10 分钟系统同步

   * 检查注册邮箱确认邮件

   * 联系 Apify 支持

2. API 访问问题

   * 检查 API 令牌是否正确

   * 确认配额是否充足

   * 验证网络连接

## 订阅管理指南

### 账户管理

* 查看状态：Settings → Billing

* 使用统计：监控计算单元使用情况

* 令牌管理：管理 API 访问令牌

### 资源管理

* 计算单元：监控每月使用量

* 存储空间：管理数据集存储

* 代理使用：配置代理设置

## 费用优化建议

1. 按需付费：初始阶段选择按需付费模式

2. 资源监控：定期检查资源使用情况

3. Actor 优化：优化 Actor 性能减少计算单元消耗

## 安全提醒

1. API 令牌保护：妥善保管 API 令牌

2. MPCard 保护：设置合理的消费限额

3. 数据安全：加密敏感数据

## Apify 核心功能详解

### Actor 开发与运行

1. Actor 创建

   * 基于 Node.js 环境

   * 支持 Puppeteer 和 Playwright

   * 容器化部署

2. 运行管理

   * 实时监控运行状态

   * 日志查看和调试

   * 性能指标分析

### 数据存储与管理

1. 数据集存储

   * 结构化数据存储

   * 支持 JSON、CSV 格式

   * 数据导出功能

2. Key-value 存储

   * 持久化配置存储

   * 状态管理

   * 缓存机制

## 使用示例

### 基础 Actor 示例

```plain&#x20;text
// 基础Apify Actor示例const Apify = require('apify');

Apify.main(async () => {
    // 创建请求队列const requestQueue = await Apify.openRequestQueue();
    
    // 添加起始URLawait requestQueue.addRequest({ url: 'https://example.com' });
    
    // 创建爬虫const crawler = new Apify.CheerioCrawler({
        requestQueue,
        handlePageFunction: async ({ request, $ }) => {
            // 提取数据const title = $('title').text();
            
            // 存储数据await Apify.pushData({
                url: request.url,
                title: title
            });
        },
    });
    
    await crawler.run();
});
```

### API 调用示例

```plain&#x20;text
// 通过API运行Actorconst axios = require('axios');

const runActor = async (actorId, input) => {
    const response = await axios.post(
        `https://api.apify.com/v2/acts/${actorId}/runs`,
        {
            inputs: input
        },
        {
            headers: {
                'Authorization': `Bearer ${process.env.APIFY_TOKEN}`,
                'Content-Type': 'application/json'
            }
        }
    );
    return response.data;
};
```

## 高级功能配置

### 代理配置

```plain&#x20;text
// 配置代理const crawler = new Apify.PuppeteerCrawler({
    proxyConfiguration: await Apify.createProxyConfiguration({
        groups: ['RESIDENTIAL'],
        countryCode: 'US'
    }),
    // ...其他配置
});
```

### 并发控制

```plain&#x20;text
// 优化并发设置const crawler = new Apify.CheerioCrawler({
    maxConcurrency: 10, // 控制并发数maxRequestsPerMinute: 100, // 限制请求频率// ...其他配置
});
```

## 技术规格

* 运行环境：Node.js 16+

* 浏览器自动化：Puppeteer、Playwright

* 数据存储：数据集、Key-value 存储

* 代理支持：数据中心、住宅代理

* API 接口：RESTful API

## 最佳实践建议

### 性能优化

1. 请求优化

   * 合理设置请求延迟

   * 使用请求队列管理

   * 避免重复请求

2. 资源管理

   * 监控内存使用

   * 优化选择器性能

   * 及时清理资源

### 成本控制

1. 计算单元优化

   * 减少不必要的页面加载

   * 使用高效的选择器

   * 优化数据处理逻辑

2. 存储优化

   * 压缩存储数据

   * 定期清理旧数据

   * 使用合适的数据格式

## 支持的功能特性

1. Web 爬取：完整网页内容抓取

2. 数据提取：结构化数据提取

3. 表单提交：自动化表单处理

4. 截图 PDF：页面截图和 PDF 生成

5. API 集成：与其他服务集成

## 合规使用提醒

1. 遵守 robots.txt：尊重网站爬虫协议

2. 速率限制：合理控制请求频率

3. 数据版权：遵守数据使用条款

4. 隐私保护：不抓取个人敏感信息

通过本教程，您可以顺利使用 MPChat 虚拟卡开通 Apify 服务，享受强大的 Web 自动化和数据提取功能。Apify 采用计算单元计费模式，建议先从按需付费开始，根据实际使用量调整订阅计划。合理优化 Actor 性能可以显著降低成本，同时获得更好的运行效果。