# 自定义ClashX规则配置

> 我使用的机场订阅自带分流规则，因此如果在其配置文件内增加自定义分流规则，在订阅自动更新后，自定义的分流规则会被覆盖。

因此，我抽出了Clash X的配置，使用`proxy-provider`和`rule-provider`对代理节点列表和规则列表分开管理，支持配置自定义的规则。

## 使用

### 1 安装clashX Pro

由于`rule-provider`使用了`RULE-SET`引用模式，需要安装支持`clash premium core`的[ClashX Pro](https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public)，普通版的`Clash X`不支持。

### 2 复制配置文件

```bash
curl -LO https://raw.githubusercontent.com/Mopip77/custom-clash-configuration/master/custom.template.yaml ~/.config/clash/custom.yaml
```

### 3 修改订阅地址

将`~/.config/clash/custom.yaml`中的订阅地址配置`<your-proxy-subscription-link>`，改为你自己的订阅地址

### 4 编写自定义分流规则

在`custom.yaml`的`rules`字段下添加你的自定义分流规则

分流规则语法cheatsheet
```
 - DOMAIN-SUFFIX,google.com
 - DOMAIN-KEYWORD,google
 - DOMAIN,ad.com
 - SRC-IP-CIDR,192.168.1.201/32
 - IP-CIDR,127.0.0.0/8
 - GEOIP,CN
 - DST-PORT,80
 - SRC-PORT,7777
```

### 5 更新clash配置

## 引用

clash的订阅规则列表[clash-rules](https://github.com/Loyalsoldier/clash-rules)
