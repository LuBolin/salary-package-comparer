# Compensation Package Comparer / 薪酬方案比较器

A bilingual, browser-only calculator for comparing Singapore and Shanghai compensation packages. It separates recurring monthly cash from the year-end bonus and estimates income tax, CPF, Shanghai social insurance, 住房公积金, living costs, allowances, and employer contributions.

用于比较新加坡与上海薪酬方案的中英双语浏览器工具。它将每月固定工资与税后年终奖分开显示，并估算个人所得税、CPF、上海社保、住房公积金、生活成本、公司补贴与公司缴纳。

## Use it / 使用方法

Open [`index.html`](./index.html) directly in a modern browser. There is no build step and no server requirement.

直接使用现代浏览器打开 [`index.html`](./index.html)，无需安装依赖或运行构建命令。

- Add, duplicate, remove, and reorder offers.
- Compare results in SGD or CNY with a configurable exchange rate and percentage baseline.
- Start with **Cash left after costs**: annual take-home cash minus housing, weekly food, other monthly costs and annual expenses, plus allowances. Enter realistic costs for each city.
- Choose **Cash after costs + CPF / housing fund** to add annual employee and employer deposits to cash left. In each Singapore offer, select **All CPF accounts**, **Housing only: Ordinary Account**, or a **Custom percentage of total CPF**. China includes employee and employer housing-fund deposits. The included amount is shown in the chart, card and table.
- Choose the current CPF age band to use its 2026 allocation. Changing the band loads its standard employee and employer contribution rates; manual rate overrides remain available. This current-payroll age band is separate from the retirement projection's start age.
- Choose **Estimated retirement income / year** to compare CPF LIFE plus planned excess-OA withdrawals for Singapore, and pension payouts for Shanghai, with no inflation adjustment. Singapore separates lifetime CPF LIFE from savings spent down to the chosen age. Salary and the current cash-and-fund total stay outside the retirement chart.
- Compare annual take-home cash and CPF/住房公积金 contributions separately too. The chart shows the annual difference from your selected baseline; cash views also show that difference divided by 12.
- Social insurance premiums remain separate in the cards and table. Premiums are not added to an individual-account balance or combined compensation total. There is no overall best-offer recommendation.
- 默认比较**扣除生活成本后现金**。可选择**扣除成本后现金＋CPF／住房公积金**，或选择**预估年度退休收入**。退休图表只显示退休后领取的收入，不显示或加上工资、扣除成本后现金及本年的缴纳额。社保缴费不直接计入账户余额。
- The bonus is assumed paid in full. Set total months of pay to 12 to check how each offer looks without a bonus.
- For Singapore offers, turn off **Singapore citizen / PR** for a foreign employee who is not a permanent resident. Both employee and employer CPF become zero, including CPF tax relief. Tax residency is a separate choice. Older saves keep CPF enabled.
- 新加坡方案中，非新加坡永久居民的外籍员工请关闭**新加坡公民／永久居民（PR）**。个人和公司CPF缴纳及相关CPF税务减免均归零；税务居民身份另行选择。旧存档默认保留CPF。
- Under Living costs & allowances, enter One-time expenses / year for travel or other annual spending. Use each offer's currency. The amount is counted once in annual living costs and reduces cash after costs and total value. Older saves and imports default to zero.
- 在生活成本与公司补贴中，填写每年一次性支出，例如旅行费用。使用各方案的原币种；该金额每年只计入生活成本一次，并减少扣除成本后的现金与总价值。旧存档和导入数据默认此项为零。
- Data is saved only in browser `localStorage`; JSON export/import makes it portable.
- Use the EN/中文 switch to change the complete interface and assumptions.

## Default model / 默认模型

**CPF / housing-fund contributions** shows this year's full employee and employer CPF or 住房公积金 deposits. It excludes China's pension and medical individual-account components. The combined cash-and-fund view adds only the selected CPF portion, or China's housing fund, to cash after costs. Choosing a comparison portion does not change actual CPF deductions, tax relief or take-home cash. The standalone contributions chart still shows full CPF; the table lists both full deposits and the amount included in the combined total.

For a housing-to-housing comparison, choose **Housing only: Ordinary Account**. Under the [2026 CPF allocation table](https://www.cpf.gov.sg/content/dam/web/employer/employer-obligations/documents/CPFAllocationRatesfromJanuary2026.pdf), age 35 and below allocates 62.17% of total CPF contributions to OA, 16.21% to SA, and 21.62% to MediSave. Thus S$37,740 of full CPF gives about S$23,463 of OA deposits to include. The share changes with age. OA can be used for housing and other permitted purposes; it is not unrestricted cash. The split shown is the standard split before retirement-sum redirects. If the actual OA allocation differs, use a custom percentage.

**CPF／住房公积金缴纳额**显示本年个人和公司的完整缴纳额，不含中国养老和医保个人账户。合计视图可选全部CPF、仅住房OA或自定义比例；中国仍计入住房公积金。选择范围不改变实际CPF扣款、个税及到手现金。35岁及以下标准分配为OA 62.17%、SA 16.21%、MediSave 21.62%，并非固定一半用于住房；比例随年龄变化。改变当前年龄段会载入对应2026年标准缴纳比例，已有手动覆盖值在保存及导入时保留。OA分配按退休存款限额划转前的标准估算，实际不同可自定义比例。退休收入另列。

Existing offers and exports remain compatible. CPF portion, custom percentage and age band are saved and exported with each offer. Older saves retain all CPF and the original age-35-and-below assumption. `adjustedTotalValue` selects the combined cash-and-fund view; the removed `employerCost` view falls back to cash after costs. Monthly and annual expense fields default to zero in older saves. Retirement assumptions receive fictional defaults, with no existing balance or past China service.

## Retirement illustration / 退休测算

Working years and pension start age are separate. New projections default to working from 25 to 50, with CPF LIFE starting at 65 and Shanghai pension at an assumed 63. Contributions stop at 50. Singapore's excess-OA spending starts when work stops or at 55, whichever is later, and defaults to ending at 80. Before that spending starts, other savings or income are needed. These ages do not establish legal pension eligibility. Pay, wage bases and current rules stay fixed. There is no inflation adjustment. Cash saved from salary, China's housing fund, medical accounts and future policy changes are excluded. Retirement income never includes salary or new annual fund deposits.

- Singapore projects contributions using [2026 standard rates by age](https://www.cpf.gov.sg/content/dam/web/employer/employer-obligations/documents/CPFcontributionratesfrom1Jan2026.pdf) and [account allocations](https://www.cpf.gov.sg/content/dam/web/employer/employer-obligations/documents/CPFAllocationRatesfromJanuary2026.pdf), independently of current payroll rate overrides. SA/RA retirement savings default to **4% annual interest**, with the rate editable. Optional retained OA deposits earn **2.5%** before use. Starting savings are treated as unused SA/RA savings. OA retention defaults to 0%, assuming housing use; MediSave is excluded. The [published base rates](https://www.cpf.gov.sg/service/article/what-are-the-cpf-interest-rates) give a blended 3.06745%, about **3.1%**, on new contributions at age 35 and below. This whole-CPF average is explanatory. Balance projections exclude extra-interest bonuses; CPF LIFE uses the published payout examples.
- From 55, the model voluntarily funds RA with available retirement savings up to the [2026 Enhanced Retirement Sum of S$440,800](https://www.cpf.gov.sg/service/article/what-is-the-current-enhanced-retirement-sum), kept fixed as an editable scenario assumption. It does not invent a cash top-up if savings are insufficient. Later selected retirement deposits fill remaining funding room; excess stays outside RA. [RA interest generally does not consume funding room](https://www.cpf.gov.sg/service/article/what-is-the-maximum-amount-of-top-ups-i-can-receive), so the RA balance can exceed the funding limit. Existing balances when starting at 55 or later are treated as funding, without reconstructing past interest. This is an annual illustration with end-year contributions. The **RA pot is never divided by a chosen lifespan**.
- The two OA choices apply only to excess savings after funding RA. The amount available is shown beside the choices. If no excess remains, both choices give the same income; the note also flags the default 0% OA retention assumption. **Withdraw as cash** divides the excess at spending start by the years to the selected end age, assuming no further return. **Keep in OA and withdraw gradually** calculates a level annual withdrawal at 2.5% interest, so the remaining OA balance reaches zero at the selected end age. Spending begins at the later of age 55 and stopping work. These are annual, end-year withdrawal approximations, not an automatic CPF service. The chart shows CPF LIFE plus OA spending during their overlapping period, beginning at pension payout age. The card separately shows OA spending before CPF LIFE, the remaining cash or OA balance at pension start, and CPF LIFE alone after OA spending ends. The age must exceed pension start age and cannot exceed 120. The default is 80. China is unchanged and does not use this life expectancy.
- **Automatic reference estimate** is the CPF default. It interpolates the [published male Standard Plan age-55 examples](https://www.cpf.gov.sg/service/article/how-much-cpf-payouts-can-i-get-every-month), converting projected RA capital to an age-55 equivalent at the reference 4% base rate, then interpolating payout ages 65–70. Thus S$440,800 funded at 55 with 4% growth reproduces the published S$3,440 monthly reference at 65. This freezes the reference relationship; it is not the actuarial CPF LIFE formula or a personal quote. No extrapolation is made outside the table. Zero capital gives zero CPF LIFE income. OA spending is added separately and does not affect CPF LIFE.
- **Custom monthly estimate** is optional. Selecting it prefills the automatic reference amount and allows editing. The CPF LIFE component is the monthly amount multiplied by 12; selected OA spending is added separately. Use the [official planner](https://www.cpf.gov.sg/member/retirement-income/about-cpf-planner-retirement-income) for a personal quote. Changing relevant salary or retirement inputs returns to automatic mode, avoiding stale custom payouts. Changing only the OA choice or end age keeps the custom CPF LIFE amount.
- Shanghai uses the [basic plus individual-account pension formula](https://rsj.sh.gov.cn/tyljjfbf_17557/20260911/t0035_1443672.html). The basic component is average monthly wage × (1 + average contribution index) ÷ 2 × service years × 1%, multiplied by 12. The individual component is the projected account balance divided by the [age-based monthly divisor](https://rsj.sh.gov.cn/tshbx_17729/20220117/t0035_1405188.html), multiplied by 12. New individual-account deposits use 8% of the social base, capped by the entered employee social rate. Employer premiums are not deposited into that account. Eligible pension payments [continue for life, including the individual-account component after its balance is exhausted](https://rsj.sh.gov.cn/trdhy_17355/20211015/t0035_1403121.html). Personal life expectancy changes the number of years paid, not the annual estimate; the statutory divisor is not a payment deadline. Future pension adjustments remain excluded.
- Shanghai defaults to work ages 25–50, payout age 63, no past service or balance, average monthly wage CNY 12,577 and **1.5% annual personal-account interest**. The editable rate uses the [published 2025 employee pension account rate](https://www.fcgs.gov.cn/ggfw/zxbs/shbz/wyk/cbdj/t26140285.shtml) as a simple future assumption, not a guaranteed rate. Only working years count as new service; interest continues after work stops. The [minimum service requirement](https://rsj.sh.gov.cn/tyljlqtj_17556/20240205/t0035_1421093.html) rises from 15 years through 2029 by half a year annually from 2030, reaching 20 years in 2039. The default 25-year career meets this minimum service requirement. The account balance is still shown, not discarded or treated as zero. Existing service, its average wage index and the account balance can be entered. Shanghai eligibility, benefit location and retirement age require confirmation; transitional pensions and later pension increases are excluded.

默认25至50岁工作并缴费，养老金领取年龄另设，新加坡65岁、上海63岁。新加坡SA／RA默认年利率4%，留存OA按2.5%计息；综合基础利率约3.1%仅作说明。55岁起，可用退休储蓄按2026年ERS上限S$440,800存入RA，不虚构额外现金补足。RA自身利息不占用存入额度。剩余资金可选一次取出并平均分摊，或留在OA按2.5%计息、逐步提取。支出从停止工作或55岁中较晚者开始，默认用至80岁，CPF LIFE仍单独终身发放。图表显示养老金开始后至OA结束年龄的合计年度金额，之前的OA支出及之后的CPF LIFE另注明。中国个人账户默认年利率1.5%，基础养老金另算，不受此寿命输入影响。不调整通胀，默认25年工作满足未来中国20年最低缴费年限，实际领取仍须符合相应资格。

Existing saved projections and imports keep pay, costs, work periods, balances, CPF choices and custom monthly payouts. Old after-inflation growth assumptions are replaced once by the new 4% / 1.5% annual-interest defaults, and the old inflation field is removed. The old default S$220,400 RA target migrates to S$440,800 when no OA choice has yet been saved. Other existing limit overrides are preserved; after migration all explicit limit choices survive saving. OA choice and end age are saved, exported, imported, and duplicated per offer. **Use 25–50 projection defaults** resets retirement assumptions and the OA choice without changing salary, tax, CPF comparison selection or living costs. All financial inputs have defaults; notes remain optional. Older blank CPF payout fields select automatic mode.

CPF applies to citizens and permanent residents, with rates depending on age and PR status. See the [CPF Board's exemption rules](https://www.cpf.gov.sg/service/article/who-is-exempted-from-receiving-cpf-contributions). Adjust the existing rate overrides for a first- or second-year PR.

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
