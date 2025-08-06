<div align="center">
  <img src="/docs/public/lilbox.svg" height="200"/>
</div>

<h1 align="center" style="margin-top: -10px"> HomeBox </h1>
<p align="center" style="width: 100;">
   <a href="https://homebox.software/en/">Docs</a>
   |
   <a href="https://demo.homebox.software">Demo</a>
   |
   <a href="https://discord.gg/aY4DCkpNA9">Discord</a>
</p>

## What is HomeBox

HomeBox is the inventory and organization system built for the Home User! With a focus on simplicity and ease of use, Homebox is the perfect solution for your home inventory, organization, and management needs. While developing this project, I've tried to keep the following principles in mind:

- _Simple_ - Homebox is designed to be simple and easy to use. No complicated setup or configuration required. Use either a single docker container, or deploy yourself by compiling the binary for your platform of choice.
- _Blazingly Fast_ - Homebox is written in Go, which makes it extremely fast and requires minimal resources to deploy. In general, idle memory usage is less than 50MB for the whole container.
- _Portable_ - Homebox is designed to be portable and run on anywhere. We use SQLite and an embedded Web UI to make it easy to deploy, use, and backup.

# Screenshots
Check out screenshots of the project [here](https://imgur.com/a/5gLWt2j).
You can also try the demo instances of Homebox:
- [Demo](https://demo.homebox.software)
- [Nightly](https://nightly.homebox.software)
- [VNext](https://vnext.homebox.software/)

## Quick Start

[Configuration & Docker Compose](https://homebox.software/en/quick-start.html)

```bash
# If using the rootless image, ensure data 
# folder has correct permissions
mkdir -p /path/to/data/folder
chown 65532:65532 -R /path/to/data/folder
docker run -d \
  --name homebox \
  --restart unless-stopped \
  --publish 3100:7745 \
  --env TZ=Europe/Bucharest \
  --volume /path/to/data/folder/:/data \
  ghcr.io/sysadminsmedia/homebox:latest
# ghcr.io/sysadminsmedia/homebox:latest-rootless
```

<!-- CONTRIBUTING -->
## 它帮你解决了哪些痛点？
     1. 乱：家里东西太多，满屋子找不到想要的。
     2. 漏：有些东西明明买了，却因为丢三落四又重新买一遍，浪费钱。
     3. 管：想知道某件东西什么时候买的、保质期啥时候到？手动记笔记太麻烦。
     4. 备：搬家、装修、保险理赔……都需要一个清晰的物品清单。
HomeBox 的诞生，就是为了解决以上这些问题。你把东西拍照、分门别类录进去，它会帮你生成一份漂亮的清单，还支持到期提醒、搜索和导出，省时又省心。

## 安装与使用超简单
 几步搞定，零基础小白也能上手。
    1. 准备数据文件夹
     mkdir -p /path/to/data/folder
     chown 65532:65532 -R /path/to/data/folder
    2. 运行 Dockerdocker run -d \
          --name homebox \
          --restart unless-stopped \
          --publish 3100:7745 \
          --env TZ=Asia/Shanghai \
          --volume /path/to/data/folder/:/data \
          ghcr.io/sysadminsmedia/homebox:latest
         • 如果想用 rootless 镜像，把镜像名后缀改成 -rootless 就行。
    3. 访问界面
      打开浏览器，输入 http://你的服务器IP:3100，就能看到 HomeBox 的 Web 界面。
    4. 录入物品
      点“新建物品”，上传照片，填写名称、分类、购买日期、到期日期……保存后，多维度搜索随手可得。
      整个过程不需要复杂配置、数据库服务器，全靠 SQLite 嵌入式存储，备份只要复制 /data 文件夹。

### 优缺点全方位盘点
    优点：
    极简              Go语言开发，单容器部署，50MB 以下内存占用，速度快到飞起。
    易用              完全 Web UI 操作，新手上手无压力，配置文件几乎看不到。
    便携              SQLite 存储，导入导出、迁移备份超简单，随时拷贝同学家用都行。
    功能实用          支持分类、搜索、到期提醒、导出清单，基本家用需求全覆盖。
    开源              MIT 协议，想改源码就改，社区贡献活跃。
    缺点：
    高级自定义少      如果你想深度定制字段或做复杂报表，内置功能可能不够用。
    移动端体验一般    虽然是响应式设计，但手机上操作感觉稍显拥挤，建议用平板或电脑。
    社区中文支持有限  官方文档主要英文，中文资料还在发育中，需要耐心摸索。
### 小结：值不值得入手？
   要是你家里是那种“随便乱放”、“常常翻箱找东西”的大乱斗状态，HomeBox 绝对能帮你快速理清头绪，省时省力还省心。它满足了家庭用户对“简单上手＋实用功能＋轻量部署”的全部想象。如果你需要更复杂的定制或更花哨的报表，就要自己动手改代码或者另寻他物，但对于绝大多数家庭场景来说，HomeBox 已经绰绰有余。毕竟，能用 50MB 就搞定的管理系统，还要什么自行车？快来试试，把家里的“黑洞”变成“井然有序”的小宇宙吧！
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you are not a coder, you can still contribute financially. Financial contributions help me prioritize working on this project over others and helps me know that there is a real demand for project development.

## Help us Translate
We want to make sure that Homebox is available in as many languages as possible. If you are interested in helping us translate Homebox, please help us via our [Weblate instance](https://translate.sysadminsmedia.com/projects/homebox/).

[![Translation status](http://translate.sysadminsmedia.com/widget/homebox/multi-auto.svg)](http://translate.sysadminsmedia.com/engage/homebox/)

## Credits

- Original project by [@hay-kot](https://github.com/hay-kot)
- Logo by [@lakotelman](https://github.com/lakotelman)
