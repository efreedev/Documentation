# ZeroNet 是什么?

ZeroNet 使用 Bitcoin (比特币)加密系统和 BitTorrent 技术构建了一个**去中心的抵制审查的网络**。

用户可以公布静态或动态的网站到 ZeroNet 中，而访问者可以选择也提供这个网站。即使只有一个伙伴提供服务，网站也可以保持在线。

当一个网站由其所有者更新时，所有为站点提供服务的节点(先前的访问者)将只会收到对站点内容进行的增量更新。

ZeroNet 附带了一个内建的 SQL 数据库。这个使得内容密集站点的开发变得容易。 该数据库也会用增量更新和托管的节点同步。


# 原因?

* 我们相信开放、自由和无审查的交流。
* 无审查: 在内容发布后，就没有办法移除它。
* 无单点故障: 即使只有一个伙伴提供它，内容仍可保持在线。
* 不可能关闭: It's nowhere because it's everywhere. 内容由任何愿意提供的用户提供。
* 快速: ZeroNet 使用 BitTorrent 技术，比中心化的服务器更快的传递内容。
* 离线工作: 即使你的互联网不可用，你也可以访问站点。
* 安全: 内容所有权是使用和保密你的比特币钱包一样的技术来确保安全的。

[comment]: <> (I'm unsure about the following bit. Thoughts?)
[comment]: <> (# What problem is ZeroNet solving?)

[comment]: <> (When Tim Berners-Lee created the internet, he meant for it to be free. Not surveilled nor censored. And [he is still fighting for that](http://edition.cnn.com/2014/03/12/tech/web/tim-berners-lee-web-freedom/).)

[comment]: <> (The internet is centralized mainly in two places: Content and Domain Names (URLs) are hosted and controlled by central servers. If you control the central servers (and if you are powerful enough you do) you control the network.)

[comment]: <> (**Decentralized content storage**)

[comment]: <> (ZeroNet tackles the content storage problem by giving everyone the ability to store content. Site visitors can choose to store a website on their computers, and when they do this they also help to serve the site to other users. The site is online even if only one user is hosting it.)

[comment]: <> (**Shared DNS cache**)

[comment]: <> (Site addresses on ZeroNet are cached by all network members. When you type a ZeroNet site URL on your browser this will query other peers connected to you about the site. If one of these peers happen to have the site they will send it to you, if not, they will forward your query along.)

[comment]: <> (This architecture means that when a site URL is created, as long as one peer is serving it, there is no way to take the URL down.)


# 特性
 * 简单、零配置的架设。
 * 基于无密码 [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki)
   的身份验证: 你的账户是使用和你的比特币钱包一样的密码系统来保护的。
 * 实时更新网站。
 * Namecoin .bit 域名支持。
 * SQL 数据库支持: 可以更容易的进行站点开发和更快的网页加载时间。
 * 匿名: 完整的 Tor 网络支持带来 .onion 隐藏服务来代替 ipv4 地址
 * TLS 加密的连接。
 * 自动化， uPnP 端口开启。
 * 多用户(openproxy)支持的插件。
 * 配合任何浏览器/操作系统工作。


# 它是如何运作的?

* 在你安装和运行 ZeroNet 后，你可以通过访问以下地址打开站点:
  `http://127.0.0.1:43110/{zeronet_site_address}`
  (如  `http://127.0.0.1:43110/1HeLLo4uzjaLetFx6NH3PMwFP3qbRbTf3D`).
* 然后 ZeroNet 将会使用 BitTorrent 网络来查找为站点供种的伙伴，而且将会从这些伙伴那里下载站点的内容(HTML, CSS, JS...)。
* 每个访问过的站点也变成由你提供服务。
* 每个站点包含了在该站点中使用的所有文件的一个列表，列表使用一个 SHA512 哈希和一个使用站点所有者的私钥生成的签名。
* 如果站点的所有者修改站点，那么他/她会签署一个新的列表并把它公布给伙伴们。
  在伙伴验证了文件列表的完整性之后(使用签名)，它们就会下载修改的内容并公布新的内容给其它伙伴。

##### [有关 ZeroNet 加密系统、内容更新和多用户站点的幻灯片 &raquo;](https://docs.google.com/presentation/d/1_2qK1IuOKJ51pgBvllZ9Yu7Au2l551t3XBgyTSvilew/pub?start=false&loop=false&delayms=3000)


# 截图

![Screenshot](./img/zerohello.png)

![ZeroTalk](./img/zerotalk.png)

##### [更多截图 &raquo;](/using_zeronet/sample_sites/)

# 当前限制

* 没有类似 Torrent 的，对于大文件的文件分割的支持
* 文件事务没有压缩~~或者还未加密~~ (已添加了 TLS 加密)
* 无私人站点

# 帮助保持本项目的活跃

Bitcoin: 1QDhxQ6PraUZa21ET5fYUCPgdrwBomnFgX


### 谢谢你!

* 更多信息、帮助、更新日志、零网站点: [http://www.reddit.com/r/zeronet/](http://www.reddit.com/r/zeronet/)
* 评论，和我们聊天: [#zeronet @ FreeNode](https://kiwiirc.com/client/irc.freenode.net/zeronet) 或者上 [gitter] (https://gitter.im/HelloZeroNet/ZeroNet)
