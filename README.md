title: 标题
comments: 评论区
toc: 是否生成目录
date: 时间
sticky: 权重 降序
categories: 分类
tags: - 标签
pic: 缩略图（在该文章文件夹下）
only:仅在何处显示(不配置都出现，配- none 隐藏)

- home首页
- category分类
- tag标签页

```
{% alertbox success "成功啦o(*￣▽￣*)ブ" %}
{% alertbox danger "有危险Σ(っ °Д °;)っ" %}
{% alertbox info "有消息(・∀・(・∀・(・∀・*)" %}
{% alertbox warning "当心哦≧ ﹏ ≦" %}


{% collapse 折叠框的标题 %}

被折叠的内容 1
被折叠的内容 2
...

{% endcollapse %}

{% collapse 折叠框的标题 open %}

被折叠的内容 1
被折叠的内容 2
...

{% endcollapse %}

{% colorpanel info 面板框的标题 %}

successs
danger
info
warning
{% endcolorpanel %}

<!-- more -->概要
{% asset_img 文件名 备注 %}插入此文件夹内图片
```





## 安装提示

由于本模板使用了和默认模板landscape一样的ejs引擎，因此当您完成Hexo站点的安装后，您应该能够直接运行本主题。

在运行之前，请您将`_config.yml.example`文件复制一份，并重命名为`_config.yml`；

## 主题配置

**配置文件地址：`./kratos-rebirth/_config.yml`**

### - Global 全局配置

- **site_analytics** : 站点统计代码，这一行代码会被插入到后页脚。
- **hoster** : 网站托管服务提供者，这个是出于感恩性的可选添加内容，这一个链接会被插入到后页脚。
- **site_logo** : 网站的LOGO图片文件，请注意与后面核心JS的设置保持一致。
- **snow** : (*true/false*)站点下雪特效开关，控制是否在载入下雪相关的代码。
- **enable_dark** : (*true/false*)站点是否启用暗色模式适配。请注意，即使启用了暗色模式，在亮色的环境下主题仍然会渲染为亮色模式；同时用户可以手动选择使用的颜色（右下角菜单栏按钮处）。
- **highlight_theme** : 代码高亮主题，五选一（light | night | night-eighties | night-blue | night-bright），控制代码高亮时候使用的配色。会根据用户的选择自动加载对应的高亮主题文件。
- **cdn** (*true/false*)为静态资源开启CDN加速（使用jsDelivr）。请注意，如果您修改了任何静态资源，那么请保持此项为false（同时也是默认状态）
- **check_update** (*true/false*)版本更新检查，无需检查的话就记得关闭哦。

### - Index 首页配置相关

- **post_type** (*true/false*)站点首页是否使用文章主题的显示模式（即一开始可见一部分，点击阅读更多可以加载全文，Hexo许多主题都默认的显示模式（而不是默认的这种卡片式的陈列方式）
- **read_count** (*true/false*)在首页显示每篇文章的阅读量统计（目前仅支持 valine/waline 评论系统的内置统计功能）
- **comment_count** (*true/false*)在首页显示每篇文章的评论量统计（目前仅支持 waline 评论系统的内置统计功能）

### - Top Menu 顶部导航栏相关

- 分为**menu**和**label**两个模块，控制页首的顶部导航栏内容。
  menu模块提供导航到的页面位置，label模块提供导航选项卡的显示内容。
  请注意menu项与label项需要一一对应，否则可能会出现无法正常显示的情况。
  配置样例随主题附带，可以参考使用。
- 现已加入二级菜单支持，配置格式为：

```
menu:
  二级菜单:
    submenu: true
    菜单项1: 地址1
    菜单项2: 地址2
    ...

label:
  二级菜单:
    submenu: 菜单显示内容
    菜单项1: 菜单项1显示内容
    菜单项2: 菜单项2显示内容
    ...
 复制
```

请注意关键词`submenu`不可被改变，其他内容在保证一一对应的情况下可以自定义。
具体可以参照主题自带的样例配置。

**额外提示：**二级菜单功能可能会和旧版本的部分函数发生冲突，如果出现意外报错的话可以考虑**检查一下是否存在更新的Hexo版本**，或者[去Github提一个Issue](https://github.com/Candinya/Kratos-Rebirth/issues)。
目前开发使用的环境(`package.json`文件)可以参见[🎁 使用环境小贴士](https://github.com/Candinya/Kratos-Rebirth#-使用环境小贴士)

### - Footer 页脚显示相关

- **group_link** : 控制是否在页面右下角显示群聊的加入按钮。如果显示的话，这里可以指定加群的链接。无需显示的话请留空（而*不是*删除这个设置项），相关的代码会自行处理结构生成关系。
- **contact** : 联系方式相关，控制是否在页脚(./kratos-rebirth/layout/_partial/footer.ejs)显示各种联系方式的按钮
  如果要启用的话，请输入相关联系方式的代码，直接输入用户名即可（fediverse的实例需要输入实例地址，邮箱请使用[mail@example.com](mailto:mail@example.com)这样的格式）；无需显示的内容请留空。
- **timenotice** : 本站运行时间前的提示文本。
- **icp** : ICP备案号，便于生成快捷链接，如`萌ICP备22010101号`
- **psr** : 公安备案号，便于生成快捷链接，如`371402000001`

### - Post Page 文章页面相关

- **show_cc** : (*true/false*)控制文章页面(./kratos-rebirth/layout/post.ejs)是否显示CreativeCommon知识共享协议相关的提示内容w
- **donate** : (*true/false*)控制文章页面是否显示捐助的二维码按钮，二维码链接可以在站点的 *JavaScript 相关的配置* 里进行修改（详见下文）
- **share** : (*true/false*)控制文章页面是否显示分享链接的按钮
- **comments** : (*disqus/disqusjs/valine/twikoo/waline/false*)会从`layout/_comments`文件夹中加载指定的评论系统，您也可以自定义其他的解决方案。如果不想开启评论的话，那就还是设置为false吧~

### - Disqus 评论相关

- **shortname** : 站点短代号，需与 [Disqus Admin - Settings - General - Shortname](https://disqus.com/admin/settings/general/) 的保持一致

### - DisqusJS 评论相关

这里使用了[DisqusJS](https://github.com/SukkaW/DisqusJS)这个项目，具体的参数配置相关的可以参考[原始文档](https://github.com/SukkaW/DisqusJS#配置-disqusjs-参数)，这里提供的说明仅供参考w

- **shortname** : 站点短代号，需与 [Disqus Admin - Settings - General - Shortname](https://disqus.com/admin/settings/general/) 的保持一致
- **sitename** : 站点名，建议与 [Disqus Admin - Settings - General - Website Name](https://disqus.com/admin/settings/general/) 的保持一致
- **api** : API服务器地址，官方有提供一个反向代理地址`https://disqus.skk.moe/disqus/`，也可以使用其他的API代理服务，或是自建相关的代理，如本站使用自建的代理(https://disqus.candinya.com/api/)
- **apikey** : DisqusJS发起请求时使用的公钥，本主题目前只考虑了一个的情况，如果有多请求需求的话可以考虑直接修改`./kratos-rebirth/layout/_comments/disqusjs.ejs`的代码
- **admin** : 站点评论区管理员的Disqus用户名，可以在 [Disqus - Settings - Account - Username](https://disqus.com/home/settings/account/) 获取或进行修改
- **adminlabel** : 站点管理员的提示标签，可以在 [Disqus Admin - Settings - Community - Moderator Badge Text](https://disqus.com/admin/settings/community/) 获取或进行修改

### - Valine 评论相关

这里使用了[Valine](https://valine.js.org/)这个项目，具体的参数配置相关的可以参考[原始文档](https://valine.js.org/configuration.html)，这里提供的说明仅供参考；如果您有自定义功能的需要，您可以考虑手动修改`layout/_comments/valine.ejs`文件中相关的配置内容。

- **app_id** : 您LeanCloud的APP ID
- **app_key** : 您LeanCloud的APP Key
- **visitor** : (*true/false*)是否开启[Valine的阅读统计功能](https://valine.js.org/visitor.html)
- **enableQQ** : (*true/false*)是否开启[昵称框自动获取QQ昵称和QQ头像](https://valine.js.org/configuration.html#enableQQ)

### - twikoo评论相关

- **env_id** : 您twikoo的Env ID

### - Waline 评论相关

这里使用了[Waline](https://waline.js.org/)这个项目，具体的参数配置相关的可以参考Waline文档的[前端配置](https://waline.js.org/client/basic.html)段，自行调整相关前后端的配置。在该配置段下的内容都会被自动引入至评论模块中。el 和 path 会在页面自动生成，不必加入。

### - APlayer 音乐播放器相关（页面左下角）

- **enabled** : (*true/false*)用音乐来点缀全新的体验吧！这里可以选择是否开启aplayer播放器哦~
- **playlist** : APlayer播放使用的歌单地址，可以使用公开的API服务，或是搭建自己使用的后端。
  我提供了一个后端API的样例，目前本站点使用的就是这个，可以去[Github](https://github.com/Candinya/aplayer-simple-backend)获取。不过这个项目已经过时，我们推荐使用下一种加载方式，即使用[MetingJS](https://github.com/metowolf/MetingJS)（默认使用`api.i-meto.com/meting/api`解析）的方式来加载。
- **meting** : 使用MetingJS时请保留该选项
  - **server** : 使用的音乐服务来源：`netease`, `tencent`, `kugou`, `xiami`, `baidu`
  - **type** : 加载的播放列表类型：`song`, `playlist`, `album`, `search`, `artist`
  - **id** : 请求的ID，如曲目ID、播放列表ID、专辑ID、搜索关键词等
- **order** : (*list/random*)音乐播放的顺序，我个人比较喜欢的是random模式，这样就能避免每次访问博客时，都是从第一首音乐开始播放的尴尬清情况。

### - Widgets 侧边栏与挂件

- **sidebar** : (*left/right/none*)是否启用侧边栏与小工具，若设置为left则会显示在页面左侧，若设置为right则会显示在页面右侧。

- **widgets** : 启用的小部件，默认全部启用，不喜欢的就删掉吧

  请注意`splitter`是分隔符，用于分割活动区域和固定区域（例如默认配置下文章页向下滚动时，About区块会顺势上浮，toc区块会固定在最顶，您可以手动调整各小挂件的位置，删除`splitter`表示禁用该功能（即所有小挂件均固定显示）

- **avataUri** : 头像的图片地址链接，例如我用的是gravatar

### - FancyBox 图片放大显示

- **fancybox** : (*true/false*)启用图片放大显示工具，点击文章内的图片可以进行全屏放大操作

### - Search 搜索

- **enable** : (*true/false*)是否启用站点搜索功能
- **path** : 搜索数据库的文件名，一般保持默认`search.json`即可
- **field** : 搜索的区域，可以是页面，或是文章，或是所有内容。默认情况下是仅搜索文章内容。
- **content** : (*true/false*)搜索内容是否包含文章或是页面的详细内容

### - JavaScript 相关的配置

- main

   

  : 主JavaScript配置

  - **picCDN** (*true/false*)图片是否使用CDN来载入（如果有本地替换过图片的话，请千万不要设置成true）
  - **createTime** 站点建立的时间，请改成您站点建立的时间。该项与页脚的运行时间有直接关联，建议按照样例格式进行书写，以免出现莫名其妙的报错。
  - **donateBtn** 捐助按钮上显示的文字，建议不要太长以免溢出，如果不显示捐助按钮的话就不用去管它啦~
  - **kr.scanNotice** 二维码小窗口上的小标题，如果不显示捐助按钮的话也不用去管它啦~
  - **qr_alipay** 支付宝二维码的文件地址
  - **qr_wechat** 微信支付二维码的文件地址
  - **siteLeaveEvent** (*true/false*)是否启用站点失焦事件（只是为了卖萌，有可能会影响到历史记录，请谨慎开启）
  - **leaveTitle** 离开时候站点标题的追加内容
  - **returnTitle** 返回时候站点标题的追加内容
  - **expire_day** 文章过期提示：距离最后更新时间多少天时，打开文件会给出提示信息
  - **topNavScrollToggle** (*true/false*)顶部导航栏在页面向下滚动时隐藏

### - Site verify related 站点所有权验证相关

- site_verify

   

  :

  - **google** : [Google Search](https://search.google.com/search-console/)，只填写中间那一串随机码即可
  - **baidu** : 百毒搜索，同样只需填写中间的一串随机码
  - **bing** : 必应搜索，同样只需填写中间的一串随机码

### - Friends page related 友链页面相关

工作模式

我们提供两种配置友链的方式：

- 一种是自动生成单独的页面，您只需要指定页面的路径（href配置内容）即可自动生成
- 另一种则是Tag工作模式（href项留空或删除），主题会生成一个方便您使用的小标签，在任何一个页面或是文章内插入`{% friends %}`即可自动生成友链块。

- friends

   

  : 友链页面全局字段，删除此字段以禁止自动生成友链页面

  - **href** : 友链页面的路径，如`friends`表示`yoursite.ltd/friends/`的路径，留空此字段会使用Tag模式
  - **page** : 页面相关的参数，您可以配置任意多您需要的页面参数，提供的样例可供您参考
  - **list** : 友链列表，您可以参照提供的样例进行对应的复制修改，每一项可以提供显示的名字(name)、简介(bio)、头像链接(avatar)和目标站点链接(link)，无用项建议留空（而不是直接删除）
  - **verify** : 是否在每次启动时验证友联的可访问性