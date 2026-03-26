# Market Structure Full v2

## 这版做了什么

相对 v1，这版重点是**降噪**：

1. 默认 pivot 从 `3/3` 调整为 `5/5`
2. 新 swing 点需要满足最小 ATR 位移过滤
3. BOS / CHoCH 增加突破确认 buffer，减少刚碰线就触发的问题

## 新增参数

- `ATR Length`
- `Min Swing Distance (ATR)`
- `Break Confirmation Buffer (ATR)`

## 适合场景

这版更适合：
- 日线 / 4h 结构观察
- 减少小级别噪音结构
- 作为后续策略化前的发布候选版本

## 默认参数建议

- `Left Pivot Bars = 5`
- `Right Pivot Bars = 5`
- `Min Swing Distance (ATR) = 0.75`
- `Break Confirmation Buffer (ATR) = 0.20`

如果你觉得还是太密，可以继续把：
- pivot 调到 `6/6` 或 `7/7`
- `Min Swing Distance (ATR)` 提到 `1.0`
