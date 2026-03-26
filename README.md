# claw-tr

`claw-tr` 是一个围绕 TradingView / Pine Script 的指标与策略开发仓库。

目标：
- 统一管理 Pine 指标、策略和公共函数库
- 让研究、回测、发布、版本管理更清晰
- 为后续扩展告警脚本、参数实验、策略说明文档预留结构

## 推荐目录结构

```text
claw-tr/
├─ README.md
├─ .gitignore
├─ docs/
│  ├─ project-structure.md
│  └─ development-guide.md
├─ pine/
│  ├─ indicators/
│  │  ├─ trend/
│  │  ├─ momentum/
│  │  ├─ volatility/
│  │  └─ volume/
│  ├─ strategies/
│  │  ├─ trend-following/
│  │  ├─ mean-reversion/
│  │  └─ breakout/
│  ├─ libraries/
│  └─ templates/
├─ research/
│  ├─ ideas/
│  └─ notes/
├─ tests/
│  └─ cases/
└─ examples/
```

## 目录说明

- `docs/`：项目文档、开发约定、命名规范
- `pine/indicators/`：TradingView 指标脚本，按研究方向细分
- `pine/strategies/`：TradingView 策略脚本，按策略类型细分
- `pine/libraries/`：公共函数、复用逻辑、工具模块
- `pine/templates/`：新建指标/策略时的模板
- `research/`：思路草稿、参数记录、实验结论
- `tests/`：手工测试用例、回测检查项、验收清单
- `examples/`：示例脚本、最小可运行案例

## 命名建议

### 指标

建议文件名格式：

```text
indicator_<category>_<name>_v1.pine
```

例子：
- `indicator_trend_ema_ribbon_v1.pine`
- `indicator_momentum_rsi_divergence_v1.pine`

### 策略

建议文件名格式：

```text
strategy_<category>_<name>_v1.pine
```

例子：
- `strategy_breakout_opening_range_v1.pine`
- `strategy_mean_reversion_bbands_v1.pine`

### 库

建议文件名格式：

```text
lib_<domain>_<name>_v1.pine
```

## 初始开发建议

第一阶段建议优先做这几类内容：
1. 通用模板：指标模板、策略模板
2. 公共函数库：均线、波动率、信号过滤、风控辅助函数
3. 基础指标：EMA / VWAP / RSI / ATR / Supertrend 等
4. 基础策略：趋势跟随、均值回归、突破
5. 市场结构类指标：HH / LL / LH / HL、BOS、CHoCH
6. 研究文档：每个策略或结构指标单独记录逻辑、参数、适用品种、已知问题

## 工作流建议

1. 在 `research/ideas/` 记录想法
2. 先从 `pine/templates/` 复制脚本模板
3. 在 `pine/indicators/` 或 `pine/strategies/` 中实现
4. 在 `research/notes/` 记录参数与回测观察
5. 在 `tests/cases/` 补充验证清单
6. 稳定后再整理发布说明

## 下一步

可以继续在这个骨架上补：
- Pine v5/v6 统一模板
- 策略开发 checklist
- 常用技术指标库
- 回测结果记录规范
