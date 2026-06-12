## changelog

> wiki 有一些截图，方便查看

see `CHANGELOG.v2.md` or [wiki](https://github.com/gozeon/yapii/wiki)

## 使用

### 方式一

1. `git clone https://github.com/gozeon/yapii.git --depth 1` or 下载项目
2. `npm install --production`  [报错点这里](https://github.com/gozeon/yapii/wiki/npm-install-%E2%80%90%E2%80%90production-%E6%8A%A5%E9%94%99)
3. 修改 `config.json` 配置文件
4. `pm2 start server/app.js --name yapii`

> 这是部署方式，如果你在本地启动，直接运行`npm start` or `node server/app.js`

> 日志管理建议使用 `pm2-logrotate`

### 方式二

> 适合从旧的`yapi`迁移到

1. 修改 `config.json` 配置文件
2. `docker build . -t yapii`
3. docker run --rm -it -d -p 4000:4000 yapii

### 方式三（推荐）

> 一键部署，需要注意数据库的备份

1. 修改 `config.json` 配置文件
2. `docker compose up -d`
3. 设置系统管理员 `docker compose run yapii node server/install.js`

> 具体可参考[frankcou](https://github.com/frankcou) 给的[详细步骤](https://github.com/gozeon/yapii/issues/19)

## 设置系统管理员

```bash
npm run install-server
```

## 自定义开发

> 主要问题是前端编译

[常见问题](https://github.com/gozeon/yapii/wiki)

```bash
docker build . -t yapii.dev -f Dockerfile.dev
docker run --rm -it -p 4000:4000 -v $PWD:/app -w /app yapii.dev /bin/sh
```
> 开发需要安装全部依赖`npm install`，参考: https://github.com/gozeon/yapii/issues/15

使用`npm start`启动`node server`，如果前端有改动，使用`npm run build-client`即可

## note

知道你们忙，所以我来了。


- yapi不维护了
- 我还挺喜欢用
- 万恶的`node_modules`，弄得js开发者跟`诈骗犯`一样 

## 线上服务相关

> 主要是我抢到了腾讯云38元一年的服务器，如果有别的服务需要搭建，请联系我

Q: 为什么要做一个线上的?  
A: 大多就是临时用一下或者项目周期短，没必要本地搭建了。
Q: 为什么没用域名?  
A: 接口就是开发的参考或格式定义，没必要。  
Q: 可以用在AI或者vibecoding种么?  
A: 可以，但别造成并发压力。

## 资金支援

> 如果你用到了或者有能力的话，不要搞情怀、凑热闹！

<img src="IMG_8705.PNG.JPG" alt="Editor" width="300">  
