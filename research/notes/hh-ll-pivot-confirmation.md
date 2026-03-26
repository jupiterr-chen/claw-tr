# HH / LL 确认逻辑说明

## 为什么不能直接比较相邻 close

文章里的 Python 示例本质上是在做：

- `HH = close > close[1]`
- `LL = close < close[1]`

这只能说明当前收盘价比前一根高/低，**不能说明市场结构上形成了 Higher High 或 Lower Low**。

比如：
- 连续几根小阳线会让 `close > close[1]` 连续成立
- 但这不代表形成了新的 swing high
- 在结构分析里，HH / LL 应该基于**已确认的摆动高点/低点**来判断

## 这版 Pine 的做法

使用 `ta.pivothigh()` 和 `ta.pivotlow()`：

- 先确认 swing high
- 先确认 swing low
- 再与上一个同类 swing 点比较

### Higher High

当一个新的确认高点出现时：
- 如果它 > 上一个确认高点
- 则标记为 `HH`

### Lower Low

当一个新的确认低点出现时：
- 如果它 < 上一个确认低点
- 则标记为 `LL`

## 为什么这是“确认版”

因为 pivot 需要右侧 `rightBars` 根 K 线来确认。

这意味着：
- 不会在当前还没走完时就提前乱标结构点
- 会有一定延迟
- 但信号更稳，更适合做结构识别

## 当前范围

当前先实现：
- HH
- LL

下一步可以继续补：
- LH
- HL
- BOS / CHoCH
- 内部结构 vs 外部结构
- 趋势状态机
