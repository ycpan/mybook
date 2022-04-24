使用方法:
```
gitbook install ./
```
book.json ： 配置文件
```json
{
    "title": "opencv",
    "output.name": "site",
    "language": "zh-hans",
    "gitbook": "2.6.9", // gitbook版本
    "root": ".",
    "plugins": [
        "code",
        "splitter",
        "chapter-fold",
        "-summary"
    ],
    "pluginsConfig": {
        "code": {
            "copyButtons": true
        }
    }
}
```
也可以是这种
```json
{
    "title": "Blankj's Glory",
    "author": "Blankj",
    "description": "select * from learn",
    "language": "zh-hans",
    "gitbook": "3.2.3", // gitbook版本可以修改
    "styles": {
        "website": "./styles/website.css"
    },
    "structure": {
        "readme": "README.md"
    },
    "links": {
        "sidebar": {
            "我的狗窝": "https://blankj.com"
        }
    },
    "plugins": [
        "-sharing",
        "splitter",
        "expandable-chapters-small",
        "anchors",
        "summary",
        "github",
        "github-buttons",
        "donate",
        "sharing-plus",
        "anchor-navigation-ex",
        "favicon"
    ],
    "pluginsConfig": {
        "github": {
            "url": "https://github.com/ycpan"
        },
        "github-buttons": {
            "buttons": [{
                "user": "panyc",
                "repo": "mybook",
                "type": "star",
                "size": "small",
                "count": true
                }
            ]
        },
        "donate": {
            "alipay": "./source/images/donate.png",
            "title": "",
            "button": "赞赏",
            "alipayText": " "
        },
        "sharing": {
            "douban": false,
            "facebook": false,
            "google": false,
            "hatenaBookmark": false,
            "instapaper": false,
            "line": false,
            "linkedin": false,
            "messenger": false,
            "pocket": false,
            "qq": false,
            "qzone": false,
            "stumbleupon": false,
            "twitter": false,
            "viber": false,
            "vk": false,
            "weibo": false,
            "whatsapp": false,
            "all": [
                "google", "facebook", "weibo", "twitter",
                "qq", "qzone", "linkedin", "pocket"
            ]
        },
        "anchor-navigation-ex": {
            "showLevel": false
        },
        "favicon":{
            "shortcut": "./source/images/favicon.jpg",
            "bookmark": "./source/images/favicon.jpg",
            "appleTouch": "./source/images/apple-touch-icon.jpg",
            "appleTouchMore": {
                "120x120": "./source/images/apple-touch-icon.jpg",
                "180x180": "./source/images/apple-touch-icon.jpg"
            }
        }
    }
}
```
关于summary插件的配置，主要是可以根据markdown的目录，自动生成summary。但是，markdown目录前面要有标号，否则，可能是乱序。
如下：
```
.
├── 0-知识体系
│   ├── 0-README.md
│   ├── 1-gitbook安装与初步使用.md
│   ├── 2-gitbook配置文件.md
│   ├── 3-npm常用命名.md
│   └── 4-writing.md
├── 1-mac
│   └── 终端配置.md
```
另外```gitbook init```是生成summary目录的文件，本身目录知识路径，决定显示的是Summary。所以，summary的位次可以和路径不一致。但summary的位次和显示的层次一致。因此，当使用summary时，```gitbook serve```已经会生成summary了，就可以得到想要的层次显示了，就不要```gitbook init```了，否则，gitbook会根据summary再次生成目录，目录就会重复（区别是带编号(为summary适配的路径名字)和不带编号（summary中的名字））。

