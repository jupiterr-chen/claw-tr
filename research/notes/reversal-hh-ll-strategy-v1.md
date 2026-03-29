# Reversal HH LL Strategy v1

## 策略逻辑

基于 `indicator_reversal_hh_ll_assist_v2` 的结构信号做回测：

- `R↑` 出现时尝试做多
- `R↓` 出现时尝试做空
- 止损放在最近结构失效位
- 止盈使用固定 `R Multiple`
- 可选：遇到反向 reversal 直接平仓

## 默认参数

- `Left/Right Pivot Bars = 5/5`
- `ATR Length = 14`
- `Min Swing Distance (ATR) = 0.75`
- `Take Profit R Multiple = 2.0`

## 回测时重点看

- Profit Factor
- Win Rate
- Avg Trade
- Max Drawdown
- Long / Short 分开表现
- 不同品种 / 周期表现是否一致
- 参数轻微调整后结果是否稳定

## 特别注意

如果某个参数只在单一品种、单一周期特别好，通常说明过拟合风险高。
