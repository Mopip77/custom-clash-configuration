# 自定义ClashX规则配置

> 我使用的机场订阅自带分流规则，因此如果在其配置文件内增加自定义分流规则，在订阅自动更新后，自定义的分流规则会被覆盖。

因此，我抽出了Clash X的配置，使用`proxy-provider`和`rule-provider`对代理节点列表和规则列表分开管理，支持配置自定义的规则。

## 使用

由于`rule-provider`使用了`RULE-SET`引用模式，需要安装支持`clash premium core`的`[ClashX Pro](https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public)`，普通版的`Clash X`不支持。

将`custom.template.yaml`复制到clash配置文件夹`~/.confing/clash/`

将`custom.template.yaml`中的订阅地址配置`<your-proxy-subscription-link>`，改为你自己的订阅地址

在`custom.tmeplate.yaml`的`rules`字段下添加你的自定义分流规则

更新clash配置

## 引用

[clash-rules](https://github.com/Loyalsoldier/clash-rules)