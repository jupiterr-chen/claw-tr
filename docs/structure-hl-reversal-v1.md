# Structure HL Reversal v1

## 目标

这是一套重新开始的版本，逻辑回到最初需求：

- 用 `HH / HL / LH / LL` 描述并确认结构趋势
- 在 bearish 结构里，`HL` 作为潜在转多预警
- 预警后，如果价格突破前一个 swing high，再给出 long trigger
- long-only 策略只围绕这套逻辑回测

## 指标文件

- `pine/indicators/trend/indicator_structure_hl_reversal_signal_v1.pine`

### 图上展示

- `HH / HL / LH / LL`：小标签
- `HL?`：下跌结构中出现 HL，提示可能转多
- `L`：在 HL 预警之后，价格突破前一个 swing high，形成 long trigger
- 绿色虚线：这次 long setup 的参考止损位（HL 的低点）

### 显示原则

这版刻意保持前端简洁：
- 不使用大号 REV 标签
- 不使用背景染色
- 不堆 BOS / CHoCH / 多余辅助线

## 策略文件

- `pine/strategies/trend-following/strategy_structure_hl_reversal_long_only_v1.pine`

### 策略逻辑

1. 确认 bearish structure（`LL + LH`）
2. 出现 `HL` -> 记为 `HL?` 预警
3. 若价格突破预警前的 swing high -> 开 long
4. 止损 = 该次 `HL` 的低点
5. 止盈 = 固定 `R Multiple`
6. 可选：出现新的 `LL` 时提前退出 long

## 适合怎么测

先测试：
- NVDA 1D
- GOOGL 1D
- BTC 4H / 1D

优先看：
- Profit Factor
- Max Drawdown
- Avg Trade
- Trade Count
- `Close Long On New LL` 开 / 关后的差异
