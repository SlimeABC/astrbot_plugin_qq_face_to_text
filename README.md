
# 让LLM读懂QQ表情

| 项目 | 当前信息                             |
| --- |----------------------------------|
| 插件名 | `astrbot_plugin_qq_face_to_text` |
| 版本 | `v1.0.1`                         |
| 平台 | `aiocqhttp`、`qq_official`        |
| 分类 | AI 增强                            |

QQ 表情在消息链里是 `Face(id=111)`，LLM 不认识数字。本插件在消息阶段把它替换成 `[表情:可怜]`，让 LLM 真正看懂情绪。

## 安装

插件市场搜索 `astrbot_plugin_qq_face_to_text`，或从 Git 安装：

```
https://github.com/SlimeABC/astrbot_plugin_qq_face_to_text
```

## 使用

装完自动生效，无需配置。内置 293 个表情映射，覆盖常见黄脸和超级表情。

## 排障

| 现象 | 检查 |
| --- | --- |
| LLM 无视表情 | 看日志有没有 "替换 Face(id=...)" |
| 未知表情XX | 该 ID 不在内置表，需改源码里的 `FACE_MAP` 字典 |


## 文件

```
main.py           插件主体（硬编码映射表，无需额外文件）
```
