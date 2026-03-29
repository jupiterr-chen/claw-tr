# HH / LL Reversal Indicator - 4H / 1D Usage Guide

## 使用目标

适合用来观察中期趋势是否有反转迹象，不适合做超短线 scalp。

## 4H 周期

### 股票（如 NVDA / GOOGL）
建议先试：
- Left / Right Pivot Bars: `6 / 6`
- ATR Length: `14`
- Min Swing Distance (ATR): `0.8 ~ 1.0`

原因：
- 4H 比日线噪音更大
- 需要更严格一点的 pivot 和摆动过滤

### BTC 4H
建议先试：
- Left / Right Pivot Bars: `6 / 6` 或 `7 / 7`
- ATR Length: `14`
- Min Swing Distance (ATR): `1.0 ~ 1.25`

原因：
- BTC 波动更大，假反转和扫损更多
- 需要更高的 swing 过滤门槛

## 1D 周期

### 股票（日线）
建议先试：
- Left / Right Pivot Bars: `5 / 5`
- ATR Length: `14`
- Min Swing Distance (ATR): `0.6 ~ 0.9`

### BTC 日线
建议先试：
- Left / Right Pivot Bars: `5 / 5` 或 `6 / 6`
- ATR Length: `14`
- Min Swing Distance (ATR): `0.8 ~ 1.1`

## 如何判断信号质量

### 更值得重视的 R↑
- 出现在一段明显下跌后
- 同时伴随确认 HH
- 反转后价格没有快速跌破失效位

### 更值得重视的 R↓
- 出现在一段明显上涨后
- 同时伴随确认 LL
- 反转后价格没有快速站回失效位

## 回测建议

先分别测试：
- NVDA 4H
- NVDA 1D
- GOOGL 4H
- GOOGL 1D
- BTCUSD / BTCUSDT 4H
- BTCUSD / BTCUSDT 1D

记录每组的：
- Net Profit
- Max Drawdown
- Profit Factor
- % Profitable
- Avg Trade
- Trade Count
