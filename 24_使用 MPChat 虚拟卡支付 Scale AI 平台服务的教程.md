# 使用 MPChat 虚拟卡支付 Scale AI 平台服务的教程

## 订阅前准备

1. Scale AI 账户准备

   * 注册 Scale AI 官网企业账户

   * 完成企业邮箱验证和基本信息设置

2. 网络环境配置

   * 使用美国住宅 IP（关键成功因素）

   * 确保 IP 干净且地理位置显示为美国

3. MPChat 资金准备

   * 准备$1000-5000 等值 USDT（Scale AI 为高端企业服务）

   * 建议准备充足资金用于企业级订阅

## 详细操作步骤

### 第一阶段：MPChat 虚拟卡准备

1. USDT 充值

```plain&#x20;text
操作路径：MPChat App → 钱包 → 存款
- 复制USDT充值地址
- 从外部钱包转入足额USDT（建议$3000+）
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
- 金额：根据Scale AI报价确定
```

### 第二阶段：Scale AI 企业账户注册

1. 企业信息准备

   * 公司英文名称

   * 企业邮箱（非免费邮箱）

   * 公司网站（如有）

   * 业务描述和使用场景

2. 注册流程

   * 访问 scale.com

   * 点击"Contact Sales"或"Get Started"

   * 填写企业信息表格：

     * 公司规模

     * 行业领域

     * 预期数据标注量

     * 项目时间线

3. 销售沟通

   * 等待 Scale AI 销售代表联系（1-3 个工作日）

   * 讨论具体需求和定价模型

   * 确定服务范围和价格

### 第三阶段：支付信息填写

1. 接收支付链接

   * 销售代表发送专属支付链接

   * 链接包含定制化报价单

2. MPCard 信息填写

```plain&#x20;text
信息源：MPChat App → MPCard → 卡片详情
- Card Number: 16位虚拟卡号
- Expiration Date: 有效期（MM/YY）
- CVV Code: 3位安全码
- Cardholder Name: 公司名称拼音
```

* 企业账单地址填写（关键步骤）

  * Country: United States

  * 使用专业美国企业地址生成器

  * 示例格式：

```plain&#x20;text
Company Name: [您的公司英文名称]
Address Line 1: 1234 AI Innovation Drive
City: Palo Alto
State: CA
ZIP Code: 94301
Phone: 生成美国企业电话号码
Tax ID: 如有美国税号可提供
```

## 支付验证与激活

1. 企业验证流程

   * Scale AI 可能进行企业资质审核

   * 准备回答关于企业业务的问题

   * 提供必要的企业证明文件

2. 大额支付验证

   * 可能需要进行电话或视频验证

   * 准备解释支付方式和业务需求

   * 确认 MPCard 额度充足

3. 服务激活

   * 支付成功后，销售代表会协助激活账户

   * 获得平台访问权限和 API 密钥

   * 接受平台使用培训

## Scale AI 服务类型和定价

## 故障排查指南

### 支付失败常见原因

1. 企业验证失败

   * 解决方案：提供真实企业信息，准备验证文件

   * 确保企业信息的一致性

2. 风控限制

   * 解决方案：与销售代表沟通支付方式

   * 确保 MPCard 额度充足

3. 地址验证严格

   * 解决方案：使用真实存在的美国企业地址

   * 确保地址信息的准确性

### 服务激活问题处理

1. 支付成功但服务未激活

   * 立即联系销售代表提供支付凭证

   * 检查邮箱确认邮件

   * 等待人工审核完成（可能 1-5 个工作日）

2. API 访问问题

   * 联系 Scale AI 技术支持

   * 提供账户信息和问题描述

   * 确认 API 密钥权限设置

## 账户管理指南

### 企业账户管理

* 项目管理：创建和管理数据标注项目

* 团队协作：添加团队成员和设置权限

* 质量监控：监控标注质量和进度

* 费用控制：设置项目预算和警报

### 支付和发票管理

* 发票下载：下载详细的企业发票

* 费用报告：生成项目费用报告

* 预算控制：设置月度预算限制

## 费用优化建议

1. 项目规划：合理规划标注任务批量处理

2. 质量平衡：根据需求选择适当的质量等级

3. 优先级管理：合理安排项目优先级控制成本

4. 长期合作：签订长期合约获得优惠价格

## 安全提醒

1. 数据安全：遵守数据保密协议

2. API 安全：妥善保管 API 密钥和访问令牌

3. MPCard 保护：设置合理的消费限额

4. 账户安全：启用多因素认证

## Scale AI 平台特色功能

1. 高质量标注：专业标注员团队

2. 快速交付：24-48 小时交付周期

3. 质量保证：多轮质量检验流程

4. 专业领域：支持医疗、法律等专业领域

5. API 集成：完整的 API 接口支持

## 使用技巧

1. 明确需求：提供清晰的标注指南和示例

2. 及时反馈：建立有效的反馈机制

3. 质量控制：定期检查标注质量

4. 沟通协作：与项目经理保持密切沟通

## 技术集成示例

```plain&#x20;text
import requests

class ScaleAIClient:
    def __init__(self, api_key):
        self.api_key = api_key
        self.base_url = "https://api.scale.com/v1"def create_labeling_task(self, project_data):
        headers = {
            "Authorization": f"Basic {self.api_key}",
            "Content-Type": "application/json"
        }
        
        response = requests.post(
            f"{self.base_url}/tasks",
            headers=headers,
            json=project_data
        )
        return response.json()
# 使用示例
client = ScaleAIClient("您的API密钥")
task_data = {
    "project": "image_classification",
    "attachment": "https://example.com/image.jpg",
    "instructions": "请识别图片中的物体"
}

result = client.create_labeling_task(task_data)
```

## 支持的数据类型

* 图像数据：分类、检测、分割标注

* 文本数据：命名实体识别、情感分析

* 音频数据：语音转写、情感分析

* 视频数据：动作识别、物体跟踪

* 传感器数据：LiDAR、雷达数据处理

通过本指南，您可以顺利使用 MPChat 虚拟卡支付 Scale AI 平台服务。Scale AI 作为高端企业级服务，验证流程较为严格，请务必准备真实的企业信息和联系方式，确保与销售代表的沟通顺畅。建议在正式使用前先进行小规模试点项目验证服务质量。