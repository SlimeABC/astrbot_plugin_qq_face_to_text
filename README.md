
# 让LLM读懂QQ表情

| 项目 | 当前信息 |
| --- | --- |
| 插件名 | `astrbot_plugin_qq_face_to_text` |
| 版本 | `v1.1.0` |
| 平台 | `aiocqhttp`、`qq_official` |
| 分类 | AI 增强 |

QQ 表情在消息链里是 `Face(id=111)`，LLM 不认识数字。本插件在消息阶段把它替换成 `[表情:可怜]`，让 LLM 真正看懂情绪。

## 安装

插件市场搜索 `astrbot_plugin_qq_face_to_text`，或从 Git 安装：

```
https://github.com/SlimeABC/astrbot_plugin_qq_face_to_text
```

## 使用

安装完成自动生效，无需配置。内置 293 个表情映射，覆盖常见黄脸和超级表情。

遇到缺失的表情（日志显示"未知表情"），两种解决办法：

**1. 编辑 JSON 文件**

插件目录下的 `face_map.json`，直接改，改完发：

```
/重载表情映射
```

**2. 插件配置覆盖**

插件配置里填 `face_map_overrides`，格式 `ID:名称`，如 `111:可怜`。优先级最高，覆盖 JSON 里的同名 ID。同样发 `/重载表情映射` 生效。

## 排障

| 现象 | 检查 |
| --- | --- |
| LLM 无视表情 | 看日志有没有 "替换 Face(id=...)" |
| 未知表情XX | 该 ID 不在内置表，需改源码里的 `FACE_MAP` 字典 |



## 文件

```
main.py           插件主体（硬编码映射表，无需额外文件）
```