# Chinese Copywriting Linter

一个用于检查和自动修复中文排版与文案风格规范的 Agent Skill。

## 功能特性

1. **中英文混排空格**：自动检测并在中文字符与英文字母/阿拉伯数字之间插入空格。
2. **标点符号规范**：确保中文语境下使用全角标点，避免重复使用叹号/问号，英文句子中正确使用半角标点。
3. **数字与单位**：数字与物理/容量/时间单位之间保留空格（如 `1 Gbps`, `2 TB`, `3 Hz`, `4 ms` 等），度数与百分比（如 `5°`, `6%`）之间不保留空格。
4. **范围连接符**：数值或时间范围连接符波浪号 `~` 前后自动增加半角空格（如 `7 Hz ~ 8 Hz`）。
5. **全半角控制**：数字一律使用半角数字。
6. **专有名词大小写**：自动纠正主流技术名词的大小写（如 `GitHub`, `TypeScript`, `React`, `Next.js` 等）。
7. **智能忽略**：自动忽略 Markdown 中的 Fenced Code Blocks（代码块）、Inline Code（行内代码）以及 URL 地址，防止误改代码和链接。

---

## 安装方法

您可以通过 Skills CLI (`npx skills`) 将此 Skill 安装到您的 Agent 运行环境中：

```bash
npx skills add hankunpeng/chinese-copywriting-linter
```

---

## 包含内容

* **`SKILL.md`**：向 AI 客户端提供关于何时使用、如何触发以及如何解释本 Linter 结果的系统提示词与指令。
* **`scripts/linter.py`**：内置的 Python 格式化与校验引擎，用于执行具体的正则表达式匹配与自动修复。

---

## 本地手动运行

如果您想在本地手动运行此 Linter 脚本：

### 1. 语法检查（不修改文件）
```bash
python3 scripts/linter.py <文件或目录路径>
```

### 2. 自动格式化（修复文件）
```bash
python3 scripts/linter.py --fix <文件或目录路径>
```
