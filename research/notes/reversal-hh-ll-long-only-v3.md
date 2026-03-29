# Reversal HH LL Long Only v3

## 这版目标

把策略做成更像“可读、可回测、可迭代”的版本。

## 核心规则

- 只做 Long
- 只在真正可交易的 bullish reversal 时开仓
- 不加仓（`pyramiding=0`）
- 出场方式：
  - 结构止损
  - 固定 R 倍数止盈
  - 可选 bearish reversal exit
  - 可选结构 trailing stop

## 关于“exit 后和继续加仓信号怎么做”

这版先采用更稳的规则：

- 持仓中：不加仓
- 出现 exit：先退出
- 退出后：如果后面再次出现新的有效 entry signal，再重新开仓

原因：
- 这样回测更容易理解
- 更容易判断问题出在 entry 还是 exit
- 避免一开始就把 pyramiding 逻辑搅进来

## 下一步可能的优化

如果 v3 结果接近可用，后面再考虑：
- pullback re-entry
- pyramiding add-on
- 部分止盈
- break-even stop
