# 南殷居士 · 电商KV视觉系统

**`nanyin-ecommerce-kv`** 将商品资料与参考图转为系列电商海报方案、两套独立语言提示词，并在具备工具的智能体中连续生图。

由 [南殷居士](AUTHOR.md) 设计、编排和维护。关注公众号 **南殷用AI**；[个人站：南殷用AI](https://nanyinai.vip/) · [作者介绍](https://nanyinai.vip/about.html) · [GitHub](https://github.com/nicolasyxw999)。

## 教程与案例

- [AI 视觉系统实战手册（初阶版）](https://nanyinai.vip/articles/ai-visual-system-practical-manual-beginner.html)：了解商品资料、提示词与视觉方案的基本用法。
- [五种配色与美术方向实战](https://nanyinai.vip/articles/ecommerce-color-workshop.html)：对照系列海报的配色与美术方向案例。

## 能做什么

- 从产品图或文字整理品牌、真实卖点、配色与外观信息。
- 锁定商品形状、LOGO位置、材质表现，规划构图有变化的系列海报。
- 分别输出纯中文、纯英文提示词，每张完整、可独立粘贴。
- 有生图能力时按授权连续生成；无生图能力时交付提示词，不伪报成图。
- 信息不足就省略相关参数，规格不足改功能概览；不把“待确认”“样例数字”等制作备注印在图上，也不编造数值。
- 交付静态电商图，外层不放网页式按钮、跳转箭头或伪链接。

这是一套可迁移的技能说明与提示词模板，不内置模型、API密钥或付费账号。自动化程度取决于所在智能体实际具备的工具。画面文字语言与提示词语言可以分别指定。

## 快速开始

### 在 Codex 中安装

下载 [Release](https://github.com/nicolasyxw999/nanyin-ecommerce-kv/releases) 中的 ZIP，解压后将 `nanyin-ecommerce-kv` 文件夹放到用户技能目录 `~/.codex/skills/`。保留目录中的 `SKILL.md`、`references`、`agents` 和文档；已有同名技能时先备份，不直接覆盖本地定制内容。

也可以在目标目录不存在时克隆：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/nicolasyxw999/nanyin-ecommerce-kv.git ~/.codex/skills/nanyin-ecommerce-kv
```

安装后开启能重新发现技能的新会话，再输入：

```text
$nanyin-ecommerce-kv
为我的商品生成一套电商海报方案和两套独立提示词：纯中文一套、纯英文一套。
先整理资料和规划构图，暂时不要生成图片。
```

### 在 Claude 或 Lavart 中使用

使用完整的[使用指南](docs/usage-guide.md)。可将对应语言的[单张提示词模板](references/paste-templates.md)复制到对话，附上商品资料与参考图；批量任务使用独立的智能体执行入口。填好模板中的资料槽位后再交给生图工具。

如果工具支持导入技能文件，可导入完整技能文件夹或其支持的包格式；如果不支持，则直接粘贴。不要假设 Claude、Lavart 和 Codex 的工具、命令或包导入能力相同。

## 准备哪些资料

```text
品牌名称：
产品名称及已知规格：
真实卖点：
目标人群：
产品参考图：正面、背面、细节图，有哪些提供哪些。
没有实物时是否允许概念款：
偏好风格：可填自动推荐。
使用场景或模特：可填自动推荐。
海报数量与比例：
画面文字语言：中文／英文／双语。
主宣传语及其他要求：
```

不必填满。缺失参数不会变成虚构数据，也不会以内部备注进入成图。

## 常用指令

**只生成提示词：**

```text
根据上传的商品图做10张9:16电商海报规划。
产品外观和品牌配色保持一致，各张构图有变化。
输出纯中文与纯英文两套独立文件，不生成图片。
```

**连续生图：**

```text
沿用已经批准的产品参考和方案，连续完成全部编号海报，不用逐张确认。
先检查已有输出，只补未完成项。每张独立出图，保存原图并报告实际检查结果。
只生成与保存，不上传店铺、不对外发布。
```

**局部修改：**

```text
只删除海报外层的拟点击按钮和跳转箭头，保留杯身、人物、配色与其他文案。
以新文件保存，不覆盖原图。
```

## 文件与使用边界

- [SKILL.md](SKILL.md)：智能体执行规则。
- [docs/usage-guide.md](docs/usage-guide.md)：安装、资料输入、语言设置、跨工具使用、批量执行与验收。
- [AUTHOR.md](AUTHOR.md)：作者属性和公开链接。
- [references/paste-templates.md](references/paste-templates.md)：四个语言独立的模板入口。
- `references/poster-zh.txt`、`poster-en.txt`：独立的单张模板。
- `references/agent-zh.txt`、`agent-en.txt`：独立的批量执行模板。

作者属性只属于技能介绍，不会自动加到客户商品图上。本仓库没有附带真实客户资料、会话日志或商品实测报告。跨平台实际生图效果取决于模型、账号权限和输入素材，不能将提示词可粘贴等同于已在所有平台实测。

## 许可

本仓库技能说明、模板与文档采用 [MIT License](LICENSE)，版权署名为南殷居士。该许可不授予第三方商标、用户素材或模型输出的额外权利，也不替代所用模型及平台的服务条款。
