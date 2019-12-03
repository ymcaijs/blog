# blog

>我的个人博客

## 配置

添加变量 `hour` 和 `minute`，用于支持在永久链接里使用发布时间的小时和分钟。

``` js
// hexo/lib/plugins/filter/post_permalink.js
function postPermalinkFilter(data) {
  // 为固定链接新增变量
  const meta = {
    /* ... */
    hour: data.date.format('HH'),
    minute: data.date.format('mm')
  };
}
```

添加默认的开放图谱缩略图，用于在 Facebook 和 Twitter 等海外平台上分享时显示，非必要。

``` js
// hexo/lib/plugins/helper/open_graph.js
if (!images.length) result += og('og:image', urlFn.resolve(url || config.url, '/images/logo.jpg'), false);
```

## 运行

启动本地服务器：

```
hexo server
```

## 部署

由于境内访问 GitHub Pages 速度不稳定，目前部署于腾讯云。

仍使用 `hexo` 部署命令推送内容到 GitHub Pages，但实际已不提供访问。

```
hexo deploy
```

在云主机的站点目录下拉取 `gh-pages` 分支内容。

原 `.blog` 域名不再续费，使用 CloudFlare 永久重定向到新域名。

## 更换主题

以 NexT 主题为例，迁移自定义代码。

```
/source/_data/ # 自定义文件所在目录
```

需要关注的主题配置项：

- Favicon
- 菜单
- 边栏头像
- 搜索
- 统计
- 自定义文件（custom_file_path）
