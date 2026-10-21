# 数字后端设计专家（Digital Back-End Design Expert）

数字 IC 后端物理实现全流程专家：从 netlist 交接一路做到 GDSII 交付，覆盖布局规划、电源网络、布局拥塞、时钟树、布线、时序与功耗签核、物理验证与 Tapeout。

## 类型

Agent 型（单个 AI 专家）

## 功能

- **布局规划与宏单元摆放**：die/core 尺寸与利用率预算、IO 与 pin assignment、macro 通道与朝向、dataflow 驱动的摆放、拥塞与时钟可行性预判。
- **电源网络与 IR/EM**：ring/stripe/mesh 取舍、follow-pin 与 via array、静态与动态 IR drop、EM 与自热余量、decap 与 power switch 布置。
- **布局优化与拥塞治理**：congestion map 归因、density 与 padding、high-fanout 缓冲、size cell / Vt swap 的收益与漏电代价。
- **时钟树综合（CTS）**：skew 与 insertion delay 目标、clock gating 树形、H-tree 与 mesh、useful skew 的边界、clock DRC 与 NDR。
- **布线、RC 抽取与 SI**：拥塞与 DRC 收敛顺序、NDR 取舍、antenna 修复、crosstalk 抑制、extraction 与签核一致性。
- **时序与功耗签核**：signoff corner 选取、OCV/AOCV/POCV 与 derate、MMMC、SI 流程、ECO 路径选择、功耗分解与瓶颈定位。
- **低功耗物理实现**：UPF 与实现一致性核查、isolation / level shifter / retention 落位、power gating 的供电与开关序列。
- **物理验证与 Tapeout**：DRC/LVS/ERC/ANT/DFM 收敛顺序、metal fill、sealring、chip finishing、GDSII 输出与交付清单。
- **工具链与自动化**：Fusion Compiler / ICC2 / Innovus、PrimeTime / Tempus、StarRC、Calibre、Voltus / Redhawk，Tcl/Python/Make flow 封装与回归。

## 使用示例

- 我的模块在 place 之后 WNS 是 -0.42ns，违例集中在 800MHz 时钟域，帮我判断是布局、时钟树还是约束问题，给收敛顺序。
- 帮我评审这个 SoC 的 floorplan：3 个 SRAM 硬核、2 个模拟 IP、目标利用率 65%，给 macro 摆放和电源网络建议。
- 7nm 项目下周 tapeout，给我一份 signoff 前检查清单，按 DRC/LVS、时序、功耗、DFM 分类。

## 头像

头像已自动生成在 `avatars/` 目录下。如需替换为自定义头像，要求：
- 格式：PNG（推荐）或 JPG
- 尺寸：512×512 px
- 大小：单张不超过 500KB

## 安装

将专家包目录放到专家目录下：

```
/Users/dzp/.workbuddy/plugins/marketplaces/my-experts/plugins/digital-ic-backend-expert/
```

然后运行注册命令使其可见：

```bash
python3 scripts/register_expert.py <expert-dir>
```

## 打包分享

```bash
python3 scripts/package_expert.py <expert-dir>
```
