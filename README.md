# Pandora Helm Chart

这是一个用于部署 Pandora-cloud 的 Helm chart。

感谢pengzhile大佬的开源项目[pandora](https://github.com/pengzhile/pandora)

## 版本信息

- Chart 版本：0.1.0
- pandora 版本：1.2.3

## values.yaml说明

1. ingress配置项中 `host`请修改为对应的域名。
2. 本项目默认开启 `https`，请在本项目命名空间下创建secret，并在 `secretName`中引用它。
3. 本项目默认使用traefik，如需使用nginx，请自行跟换ingress下内容。
4. 可在auth中添加 `basicauth`认证。认证信息请用 `htpasswd -nb user password | openssl base64`生成。

## 如何使用

1. 克隆此项目
2. 拷贝或通过 `helm show`导出 `values.yaml`或将 文件以满足你的需求
3. 创建新的namespace（可选，强烈推荐）
4. 使用 Helm 安装此 chart

```bash
helm install [RELEASE_NAME] ./pandora-chart -f [YOUR_VALUES].yaml
```

请注意，你需要将 `[RELEASE_NAME]` 替换为你想要的发布名称。将 `[YOUR_VALUES]`替换为你自己的values文件。

## LICENSE

MIT
