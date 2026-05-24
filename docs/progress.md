# 📋 lidar-promo-website 项目进度管理

> **文档说明**
> - `andrewljf001` = 项目负责人本人操作
> - `Claude (Anthropic)` = 由 AI 助手 Claude 代为更新
> - 每次更新请在底部「文档编辑记录」追加一行

---

## 项目基本信息

| 字段 | 内容 |
|------|------|
| 项目名称 | 激光雷达 B2B 推广网站 |
| 仓库地址 | https://github.com/andrewljf001/lidar-promo-website |
| 负责人 | andrewljf001 |
| 开始日期 | 2026-05-24 |
| 目标 | 面向海外买家（无人机/车载/极客），线下汇款询价 |
| 产品核心 | Sony IMX459 + FPGA 自研激光雷达，售卖开发平台 |

---

## 🌐 域名决策记录

| 项目 | 内容 |
|------|------|
| 首选域名 | `lidarforge.com` |
| 备选域名 | `lidarpulse.com` / `lidarcore.com` / `depthcore.com` |
| 当前状态 | ⏳ 暂缓购买，先用 GitHub Pages 搭建 Demo |
| 正式购买时机 | Demo 验证完成、正式推出前 |
| GitHub Organization | 正式推出时注册 `lidarforge` Organization |
| 注意事项 | 购买前确认 `lidarforge.com` 可用性 |

---

## 🎨 品牌策略

### 网站风格
- 深色科技风（深色背景 + 青色 accent + 等宽字体）
- 符合工程师/极客审美，传递"认真做技术"的信号

### 团队展示策略（重要）
- **不展示团队成员**，团队躲在品牌后面
- 原因：避免竞争对手挖人、不暴露团队规模
- 网站**不设 Team / About 页面**
- 对外只用品牌名 **LidarForge**
- 联系方式用品牌邮箱（如 `hello@lidarforge.com`），不出现个人名字
- 页面上团队描述用一句话带过：
  > *"Built by a team of engineers obsessed with LiDAR precision."*

---

## 🏗️ 基础设施架构

### 服务器信息
| 项目 | 内容 |
|------|------|
| 服务商 | Contabo VPS |
| 规格 | 6核 CPU / 12G RAM / 100G SSD |
| 用途 | 主站 + Discourse 社区论坛 |

### 压力评估（100人同时在线）✅ 完全没问题
| 资源 | 需求 | 可用 | 结论 |
|------|------|------|------|
| CPU | 2-4核 | 6核 | ✅ 充裕 |
| RAM | 3-6G | 12G | ✅ 充裕 |
| 存储 | ~10G（系统+DB）| 100G | ⚠️ 图片附件需对接对象存储 |

> Discourse 官方推荐 2核2G，当前配置是推荐值3倍，支撑500人在线无压力

### 存储解决方案
- 媒体文件走 **Cloudflare R2**，不落本地 VPS
- 免费额度 10G/月，超出 $0.015/G，费用几乎为零

### 开源分工
| 内容 | 平台 |
|------|------|
| ROS 驱动 / SDK / 示例代码 | **GitHub**（开发者主场，免费无限）|
| 技术讨论 / 问答 | **Discourse（自有 VPS）** |

---

## 🏘️ 社区策略

- 自己的网站是社区根据地，外部平台只作引流
- 开源代码托管 GitHub，讨论沉淀 Discourse

### ✅ 开源内容（托管 GitHub）
| 内容 | 说明 |
|------|------|
| ROS 驱动包 | 开源促进硬件销售 |
| 上位机 SDK 接口层 | 降低集成门槛 |
| 点云数据处理示例 | 降低开发门槛 |
| 应用案例代码 | 无人机避障、SLAM 示例等 |

### 🔒 闭源内容（永不开放）
| 内容 | 说明 |
|------|------|
| FPGA 固件 | 核心算法，绝对壁垒 |
| Sony IMX459 驱动调教参数 | 关键性能差异 |
| 硬件原理图 | 除非后续销售 PCB 设计 |

---

## 📌 总体阶段规划

| 阶段 | 内容 | 状态 |
|------|------|------|
| 阶段零 | 需求梳理 & 推进逻辑确认 | ✅ 完成 |
| 阶段一 | Demo 搭建（GitHub Pages）| 🔄 进行中 |
| 阶段二 | 页面内容替换为真实产品信息 | 🔲 待开始 |
| 阶段三 | 产品内容填充 & 3D 展示 | 🔲 待开始 |
| 阶段四 | 正式域名购买 & 上线 | 🔲 待开始 |
| 阶段五 | Discourse 部署 & 对象存储 & 开源发布 | 🔲 待开始 |
| 阶段六 | 外部推广引流 | 🔲 待开始 |
| 阶段七 | SEO & 持续优化 | 🔲 待开始 |

---

## 阶段零：需求梳理 ✅

- [x] 产品定位、目标客群、询价方式确定
- [x] 域名候选确定，首选 `lidarforge.com`
- [x] 建站方式：Claude 生成静态页面
- [x] 社区：Discourse 自有 VPS，外部平台只引流
- [x] 开源代码托管 GitHub，讨论沉淀 Discourse
- [x] 服务器压力评估：6核12G 支撑100人在线完全没问题
- [x] 存储方案：媒体文件接 Cloudflare R2
- [x] 开源/闭源边界确定
- [x] 品牌策略：不展示团队，无 Team/About 页面，只用品牌邮箱

---

## 阶段一：Demo 搭建 🔄

- [x] 完成 index.html 主站页面
- [x] 完成 community.html 社区 Demo 页面
- [x] 推送到 GitHub 仓库根目录
- [ ] 开启 GitHub Pages（Settings → Pages → Branch: main）
- [ ] 确认访问：https://andrewljf001.github.io/lidar-promo-website/
- [ ] 手机端体验反馈 → 修复移动端适配问题
- [ ] 提供产品真实名称与规格参数

---

## 阶段二：页面内容替换 🔲

- [ ] 替换产品名称、型号、规格为真实内容
- [ ] 替换占位图片为真实产品图
- [ ] 询价表单接入邮件（Formspree）
- [ ] 移动端适配优化

---

## 阶段三：产品内容 & 3D 展示 🔲

- [ ] 实物样品多角度拍照（50-100 张）
- [ ] AI 三维重建（NeRF / 高斯泼溅）
- [ ] 网站嵌入 360° 交互预览

---

## 阶段四：正式域名 & 上线 🔲

- [ ] 确认 `lidarforge.com` 可用性
- [ ] 注册 GitHub Organization `lidarforge`
- [ ] 购买域名，SSL 配置，迁移上线

---

## 阶段五：Discourse 部署 & 开源发布 🔲

- [ ] Contabo VPS 安装 Docker，部署 Discourse
- [ ] 配置 Cloudflare R2 对接文件上传
- [ ] 配置社区分类
- [ ] 开源发布：ROS 驱动 / SDK / 点云工具 / 示例代码

---

## 阶段六：外部推广引流 🔲

- [ ] Hackaday.io / Hackster.io / Reddit 发帖引流
- [ ] 所有外部帖子附社区链接

---

## 阶段七：SEO & 持续优化 🔲

- [ ] Meta 标签优化
- [ ] Google Search Console 接入

---

## 📅 进度日志

| 日期 | 完成内容 | 操作人 |
|------|----------|--------|
| 2026-05-24 | 创建 GitHub 仓库 | andrewljf001 |
| 2026-05-24 | 初始化仓库文件结构 | Claude (Anthropic) |
| 2026-05-24 | 完成全套需求梳理与技术方案确定 | andrewljf001 + Claude |
| 2026-05-24 | 服务器压力评估完成 | Claude (Anthropic) |
| 2026-05-24 | 完成 index.html + community.html，推送 GitHub | Claude (Anthropic) |
| 2026-05-24 | 确定品牌策略：不展示团队，无 Team/About 页面 | andrewljf001 |

---

## 🖊️ 文档编辑记录

| 时间 | 修改内容 | 操作人 |
|------|----------|--------|
| 2026-05-24 | 文档初始创建 | Claude (Anthropic) |
| 2026-05-24 | 更新产品定位、域名、阶段规划 | Claude (Anthropic) |
| 2026-05-24 | 新增社区策略、开源/闭源边界 | Claude (Anthropic) |
| 2026-05-24 | 新增基础设施架构、服务器评估、存储方案 | Claude (Anthropic) |
| 2026-05-24 | 新增品牌策略：不展示团队，无 Team/About 页面 | Claude (Anthropic) |

---

## 说明
- ✅ 已完成　🔄 进行中　🔲 待完成　🔴 紧急