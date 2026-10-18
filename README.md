# adg-rules

自用 [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) 规则集，持续维护。

## 🚀 订阅方式

在 AdGuard Home 的 **过滤器 → DNS 拦截清单** 中添加以下地址（任选所需）：

```
https://raw.githubusercontent.com/comew574/adg-rules/main/rules-data.txt
https://raw.githubusercontent.com/comew574/adg-rules/main/dns.txt
https://raw.githubusercontent.com/comew574/adg-rules/main/Day.txt
```

**白名单**添加到 **DNS 允许清单**：

```
https://raw.githubusercontent.com/comew574/adg-rules/main/white-rules.txt
```

> ⚠️ 如果 `raw.githubusercontent.com` 访问不稳定，可换用以下镜像：
> ```
> https://ghfast.top/https://raw.githubusercontent.com/comew574/adg-rules/main/rules-data.txt
> https://cdn.jsdelivr.net/gh/comew574/adg-rules@main/rules-data.txt
> ```

## 🧩 规则格式

**拦截规则**（AdGuard 语法）

```
||example.com^              # 拦截域名及其子域
||example.com^$third-party  # 仅拦截第三方请求
/ads?[0-9]+\.example\.com/  # 正则拦截
```

**白名单**（`@@` 前缀）

```
@@||example.com^            # 放行
@@/^api\.example\.com$/     # 正则放行
```

## 🔄 更新策略

规则按需更新，主要通过青龙定时任务自动提交。查看历史：

```bash
git log --oneline
```

AdGuard Home 端可在「过滤器」页面点「检查更新」，或设置自动更新间隔。

## 📌 说明

- 本规则集为**个人自用**，按实际使用场景裁剪，不追求大而全
- 拦截规则基于 `ad`、`sdk`、`log`、`stat` 等关键词与已知 SDK 域名整理
- 遇到误杀请在 `white-rules.txt` 中补充放行，优先用精确域名而非宽泛正则
- 规则如有冲突，**白名单优先级高于拦截**

## 📜 许可

个人使用，无特定许可。
