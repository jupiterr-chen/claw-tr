# Reversal HH LL Minimal v1

## 设计目标

这版不是做完整市场结构展示，而是专门为“通过 HH / LL 捕捉趋势反转”服务。

## 只保留的内容

- HH 确认后，如果此前偏空 => 给出多头反转信号
- LL 确认后，如果此前偏多 => 给出空头反转信号
- 可选 HH / LL 标签
- 很轻的趋势背景

## 刻意去掉的内容

- HL / LH 标签
- BOS / CHoCH 标签
- 结构连接线
- 过多的辅助线

## 核心逻辑

### Bullish Reversal

- 形成确认 `HH`
- 且此前 `trendBias = -1`
- 触发 `REV↑`

### Bearish Reversal

- 形成确认 `LL`
- 且此前 `trendBias = 1`
- 触发 `REV↓`

## 适合用途

- 作为 TradingView 图表上的简洁反转提示器
- 给后续策略开发做基础信号层
- 避免完整结构指标太吵
