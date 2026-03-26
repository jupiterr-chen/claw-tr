# Market Structure Full v1

## 包含内容

这个版本把结构识别扩成完整的一套：

- HH: Higher High
- HL: Higher Low
- LH: Lower High
- LL: Lower Low
- BOS: Break of Structure
- CHoCH: Change of Character
- Trend State: bullish / bearish / neutral

## 核心逻辑

### 1. 先确认 pivot

通过 `ta.pivothigh()` 和 `ta.pivotlow()` 得到确认后的 swing 高低点。

### 2. 再判断结构类型

- 新高点 > 上一个高点 => HH
- 新高点 <= 上一个高点 => LH
- 新低点 < 上一个低点 => LL
- 新低点 >= 上一个低点 => HL

### 3. 再判断 BOS / CHoCH

- 收盘价向上突破最近有效结构高点
  - 如果此前趋势为 bearish => CHoCH↑
  - 否则 => BOS↑
- 收盘价向下跌破最近有效结构低点
  - 如果此前趋势为 bullish => CHoCH↓
  - 否则 => BOS↓

## 说明

这是一个**确认版结构指标**，所以会有 pivot 确认延迟，但稳定性比直接比较相邻 close 更强。

## 后续可优化

- 内部结构 / 外部结构分层
- 更严格的 swing 过滤
- 位移阈值（ATR / 百分比）过滤伪结构
- 专门的 BOS / CHoCH 线段绘制
- 多周期结构联动
