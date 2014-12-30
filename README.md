GitBook Table Of Content Plugin
==============

为GitBook生成目录结构，效果如下：

![gtoc效果图](https://lh6.googleusercontent.com/-jsqrsB5Pu1o/VJLHr7s0J2I/AAAAAAAACNw/f3jcM5F4aVc/s800/gtoc%25E6%2588%25AA%25E5%259B%25BE.png)



### 使用方式
在`book.json`中添加如下配置：
{
    "plugins": ["gtoc"]
}

然后运行`gitbook install`即可。

### 功能
 - 抽取页面标题组成目录列表
 - 自动添加序号
 - 可隐藏GTOC
 - 回到顶部功能，可配置是否有“电梯”效果
 - 适配Gitbook的“Sepia”、“Night”主题
 - 抽离出配置项，提供

### 快捷键
【t】:收缩/展现目录

【h】:显示/隐藏目录

### 说明
 - 默认只抽取h2,h3标题
 - 默认进入页面就显示（后期会修改默认隐藏）


### TODO
 - 需要有本地存储功能，记忆上次用户阅读的位置，可配置此功能【2014.12.23】
 - 需要抽取出配置项【2014.12.23】
 - 适应不同主题下的样式（比如夜间模式等等）【20141219】
 - 添加滚动高显功能，电梯功能【20141219】
 - 功能的模块化【20141219】
 - 绑定快捷键't'，用于toggle显示/隐藏【20141218】
 - 手柄hover状态时，需显示提示文字【20141218】
 - 添加“回到顶部”【20141218】
 - 配置：【20141218】
     + 抽取层级
     + 放在左边还是右边
     + 跟随还是放在开头（跟随的时候可以折叠，包含“回到顶部”按钮）


### 修改记录

**2014.12.24**
 - 完成电梯功能
 - 解决ScrollTop的奇怪问题，“只有在Chrome打开控制台情况下'回到顶部'按钮才有有效”，这是因为当宽度大于1240时body-inner是固定高度的，而当宽度小于1240时，body-inner是变高度，book-body是固定高度的；原始代码只对book-body设置scrollTop动画，所以打开Chrome窗口的时候（意外地使得浏览器窗口小于1240）才有动画；已经修复。

**2014.12.22**
 - 主题模式的匹配
 - "回到顶部"功能

**2014.12.19**
 - 重构，模块化，抽离出content模块，专注目录dom字符串
 - 调整目录结构，使得能够出现垂直滚动条
 - 添加state-scroll，只有当窗口高度小于目录高度时候才显示滚动条

**2014.12.18**
 - 使用$.guid给不同的标题赋Id
 - 使用tagName给不同层级标题赋值类名
 - 添加动画效果