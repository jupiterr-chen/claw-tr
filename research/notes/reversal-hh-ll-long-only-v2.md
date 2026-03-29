# Reversal HH LL Long Only v2

## 这版改动

- 只做 Long
- 加入 Backtest Start / End 时间输入
- 止损使用最近结构失效位
- 止盈使用固定 R 倍数
- 可选：遇到 Bearish Reversal 直接平仓

## 怎么选择周期

TradingView 策略默认跟随当前图表周期：
- 图表是 4H，就回测 4H
- 图表是 1D，就回测 1D

## 怎么选择回测时间段

在策略输入里设置：
- `Backtest Start`
- `Backtest End`

## 回测重点

- Profit Factor
- Max Drawdown
- Avg Trade
- Trade Count
- Bearish Reversal Exit 开/关后的差异
