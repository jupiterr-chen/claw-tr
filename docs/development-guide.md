# Development Guide

## Pine Script 开发约定

## 1. 版本

默认统一使用 Pine Script v6；除非有明确兼容性需求，否则不再新增 v5 脚本。

## 2. 文件头建议

每个脚本建议在开头写清楚：
- 脚本名称
- 类型（indicator / strategy / library）
- 版本号
- 作者/维护者
- 功能简介
- 最近更新日期

示例：

```pine
//@version=6
indicator("EMA Ribbon", overlay=true)

// Name: EMA Ribbon
// Type: Indicator
// Version: v1
// Description: Multi-EMA ribbon for trend observation.
```

## 3. 命名规范

### 变量
- 输入参数：`inputLength`, `inputSource`
- 中间变量：`emaFast`, `emaSlow`, `atrValue`
- 布尔信号：`isLongSignal`, `isShortSignal`

### 函数
- 使用动词或明确语义：`calcAtrBand()`、`getTrendState()`

### 常量
- 使用大写或明确前缀：`DEFAULT_LENGTH`

## 4. 注释习惯

不要把每一行都注释，但以下内容必须说明：
- 核心公式来源
- 特殊过滤条件
- 重绘风险
- 进出场逻辑
- 参数敏感项

## 5. 指标与策略分离

同一个研究思路，优先拆成：
- 一个指标文件：专注信号可视化
- 一个策略文件：专注进出场和回测

这样后续维护、排错和展示都会更干净。

## 6. 公共逻辑抽离

当出现以下情况时，应该抽到 `pine/libraries/`：
- 多个脚本重复使用同一段逻辑
- 同一指标被多个策略依赖
- 时间过滤、波动率计算、信号标准化经常复用

## 7. 研究记录要求

每个比较正式的策略，建议在 `research/notes/` 新建一个对应说明文档，至少记录：
- 核心逻辑
- 使用指标
- 交易品种
- 时间周期
- 参数范围
- 回测观察
- 已知缺陷
- 下一步优化方向

## 8. 提交建议

建议 commit message 使用这类格式：
- `init: bootstrap claw-tr project structure`
- `feat: add ema ribbon indicator template`
- `feat: add opening range breakout strategy`
- `docs: add pine development guide`
- `refactor: extract shared volatility helpers`

## 9. 发布前检查

发布前至少检查：
- 是否有 repaint 风险说明
- 参数默认值是否合理
- 是否有无效 plot / label 残留
- 指标与策略标题是否清晰
- 输入项是否对用户友好
- 是否在目标品种和周期上完成过基本验证
