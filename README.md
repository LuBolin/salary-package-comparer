# Compensation Package Comparer / 薪酬方案比较器

A bilingual, browser-only calculator for comparing Singapore and Shanghai compensation packages. It separates recurring monthly cash from the year-end bonus and estimates income tax, CPF, Shanghai social insurance, 住房公积金, living costs, allowances, employer contributions, and total employer cost.

用于比较新加坡与上海薪酬方案的中英双语浏览器工具。它将每月固定工资与税后年终奖分开显示，并估算个人所得税、CPF、上海社保、住房公积金、生活成本、公司补贴与公司缴纳。

## Use it / 使用方法

Open [`index.html`](./index.html) directly in a modern browser. There is no build step and no server requirement.

直接使用现代浏览器打开 [`index.html`](./index.html)，无需安装依赖或运行构建命令。

- Add, duplicate, remove, and reorder offers.
- Compare results in SGD or CNY with a configurable exchange rate and percentage baseline.
- Switch between cash take-home, cash after costs, and cash plus CPF/住房公积金 personal-account value.
- Data is saved only in browser `localStorage`; JSON export/import makes it portable.
- Use the EN/中文 switch to change the complete interface and assumptions.

## Default model / 默认模型

The included fictional examples demonstrate the calculator without representing a real person or offer:

- Singapore: citizen CPF and resident income tax, using the published 2026 CPF ceilings.
- Shanghai: China-local employment, resident IIT, Shanghai social-insurance bases, and an editable standard housing-fund rate.

内置方案仅为虚构示例，并不代表任何真实个人或offer。新加坡方案采用公民CPF与居民个人所得税；上海方案采用中国境内劳动合同、居民个税、上海社保基数和可调整的标准住房公积金比例。

All rates, ceilings, bonus eligibility, deductions, costs, and allowances can be changed per offer. Official sources and important limitations are linked inside the dashboard.

## Privacy / 隐私

The app has no analytics, backend, cookies, or network requests. Offer data stays in the browser unless the user explicitly exports a JSON file.

本工具没有统计分析、后端服务或网络请求。除非用户主动导出JSON文件，否则薪酬数据只保存在本地浏览器中。

## Accuracy

This is an offer-comparison estimate, not tax, legal, or financial advice. Payroll withholding, tax residence, foreign-worker participation, bonus qualification, relief eligibility, and employer policy can change the real result. Confirm material assumptions with the employer or relevant authority.

本工具仅供比较offer，并非税务、法律或理财建议。实际结果可能受工资代扣、税务居民身份、外籍员工参保、年终奖资格、扣除资格和公司政策影响。

## Contributing

Keep changes dependency-free where practical, cite primary official sources for policy updates, and preserve the runnable checks in `selfTest()`.

## License

[MIT](./LICENSE)
