# 优质企业估值小程序

微信小程序，使用唐朝估值法计算企业合理买点、三年后合理估值、卖点等核心指标。

## 功能

- 输入净利润增速、当前市盈率，输出买点/合理估值/卖点
- 支持 Lifetime / Monthly 会员制（微信支付）
- 支持分享奖励领取

## 目录结构

```
weapp-calculator/
├── app.js / app.json           # 小程序入口
├── pages/
│   ├── index/                  # 估值计算主页
│   ├── result/                # 估值结果页
│   ├── price/                 # 价格说明页
│   ├── membership/           # 会员中心
│   └── free-use/             # 免费使用
├── cloudfunctions/           # 云开发云函数
│   ├── createOrder/          # 创建支付订单
│   ├── confirmOrder/         # 确认支付
│   ├── getMembership/       # 获取会员状态
│   └── claimShareBonus/     # 领取分享奖励
├── utils/
│   ├── valuation.js         # 估值核心算法
│   ├── industry.js          # 行业数据
│   └── access.js            # 权限控制
├── tests/                   # 单元测试
└── assets/                  # 资源文件
```

## 估值算法

核心公式来自唐朝的价值投资体系：

- 三年后合理估值 = 当年净利润 × (1+增速)^3 × 合理市盈率
- 买点 = 三年后合理估值 ÷ 2
- 卖点 = 当年净利润 × 50（或三年后合理估值 × 150%，取低值）

---
Made with ❤️
