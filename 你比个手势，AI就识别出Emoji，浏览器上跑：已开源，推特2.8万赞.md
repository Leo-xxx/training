## 你比个手势，AI就识别出Emoji，浏览器上跑：已开源，推特2.8万赞

原创： 关注前沿科技 [量子位](javascript:void(0);) *今天*

##### 圆栗子 发自 凹非寺  量子位 报道 | 公众号 QbitAI

一只**手势识别AI**，怎样才算得上 (优) 秀啊？

不停地变换姿势，都能**实时输出Emoji**，大约是很秀了：

![img](https://mmbiz.qpic.cn/mmbiz_gif/jV7UBxIyfBMtZJFdNu6Zs76LibdBFNHvCZwkVjibfzKJABXQr2RyjrmQSaOoHkS1x46MB21LkibTMj4ia4vRwxXaYA/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

🖖是守卫 (误) ，是来自《星际旅行》瓦肯的举手礼。不大常用，做起来甚至有难度。

🤞是好运，一般会两只手一起比。不过，也不是人类通用的手势。

即便这样，AI依然机智地识别出来。并且，**它是在浏览器上跑，也几乎没有延时**。

AI的爸爸，名字叫Nick Bourdakos (简称“尼克”) ，是来自IBM的程序猿。

尼克把自己的调教成果发了推特，揽下**2.8万赞**：

![img](https://mmbiz.qpic.cn/mmbiz_png/jV7UBxIyfBMtZJFdNu6Zs76LibdBFNHvCEpMTn5oiaRtloJksYxbSZicmtYg9yVzrqTGLu0GzvuE4zW0Uib8lONoyQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

###### **△** 666

尼克用的是**TensorFlow.js**，实时识别毫无压力。

他把算法**开源**了，说大家都可以试一试。

## 半小时就好

尼克说这个模型很简单，就是**SSD-MobileNet**。

MobileNet是分类，SSD是目标检测，搭配食用也是常规方法。

![img](https://mmbiz.qpic.cn/mmbiz_gif/jV7UBxIyfBMtZJFdNu6Zs76LibdBFNHvC35JfwzcGSakT3MicqQMCkj7iaL4ZY2yXf5nTLAQlYHlTnjMCGZR1YEAw/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

他是用IBM云上的GPU训练的，**免费的k80**，半小时就训练好了。

在训练开始之前，要先准备数据：AI吃的是**标注过的手势图**。

准备就绪，就来安装模型吧：

```
1$ npm install -g cloud-annotations
```

然后，可以开始训练了：

```
 1$ cacli
 2┌─────────────────────────────┐
 3│ (C)loud (A)nnotations (CLI) │
 4│ version 1.0.12              │
 5└─────────────────────────────┘
 6
 7Usage: cacli <command>
 8
 9where <command> is one of:
10  init         Interactively create a config.yaml file
11  train        Start a training run
12  logs         Monitor the logs of a training run
13  progress     Monitor the progress of a training run
14  list         List all training runs
15  download     Download a trained model
16
17cacli <cmd> -h     quick help on <cmd>
```

当然，也不是非要用IBM云，也不是非要用GPU。拿**CPU**也能调教AI，大概要几小时吧。

训练完成，该在浏览器上跑了。GitHub项目里，自带了转换为TensorFlow.js模型的脚本。

把模型添加到**React App**里面。

![img](https://mmbiz.qpic.cn/mmbiz_png/jV7UBxIyfBMtZJFdNu6Zs76LibdBFNHvCiajmPXvNtdIicLgc5icY6G9GSFuXuPwQ28FgpXY0sAdohU5D03g0GGj0g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

最后，写一句nmp start，用浏览器打开http://localhost:3000。

耶，这样就可以对着屏幕随意舞动手指了，你的AI会明白的：

![img](https://mmbiz.qpic.cn/mmbiz_gif/jV7UBxIyfBMtZJFdNu6Zs76LibdBFNHvCn041n87k8qPfgn1lQVyibSLAticVYBwLog5tvuRp1wQZr5JABp2wye3g/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

当然，这只机智的AI，才不是只能识别手指。

## 喝点什么

只看你用什么样的数据去投喂AI了。

曾经，尼克就帮AI修炼了分辨汽水的眼力。

**第一题**：一瓶雪碧，一瓶Canada Dry，都是绿色。

![img](https://mmbiz.qpic.cn/mmbiz_gif/jV7UBxIyfBMtZJFdNu6Zs76LibdBFNHvCPOiadPMVEuEp27icdZ8M46YEoWj71vWDujRZ8WqJhnFsoN0CUQ4fOYNg/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

不管调换位置、还是侧过瓶身，AI都不会被迷惑。定格一看：

![img](https://mmbiz.qpic.cn/mmbiz_png/jV7UBxIyfBMtZJFdNu6Zs76LibdBFNHvCckvQtnub9giaTw0tCkZU1jmwdbW20cSPiaqCAu6ZUyqIibNEY3kNjPUSA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**第二题**：加大难度，两瓶都是Mountain Dew，一瓶普通一瓶低糖。

AI依然分得清楚，毫不犹豫。

![img](https://mmbiz.qpic.cn/mmbiz_gif/jV7UBxIyfBMtZJFdNu6Zs76LibdBFNHvC6icPzgI49aVtx6em81F6sGp6u5ibO6ZPiaQnK0Y8ZG68MUHe9ta3WhI1Q/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

分辨手势，分辨汽水，都不失水准。

那么问题来了，**你想让AI识别什么呢？**

想好了就开始调教吧，代码在这里：

https://github.com/cloud-annotations/training/

P.S. 推特评论区，已经有小伙伴亲测成功，并表示Easy。

![img](https://mmbiz.qpic.cn/mmbiz_gif/jV7UBxIyfBMtZJFdNu6Zs76LibdBFNHvCjDnEeZr7icMJ9jmTJJib9PKEBHtWdL2gxmc0LqaD6KIKb5DP9j6IY8CQ/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

###### **△** 再把识别结果，显示成Emoji就完美了

— **完** —

**小程序|get更多AI学习干货**

[![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtDpADEKp9rvicB48XgA8ueVdwNbXM1wibYx0ic2pYicwu3UCU5BM6fpDvbH8c4e9JV3uGvYaWAhvGiaTVQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)](https://mp.weixin.qq.com/s?__biz=MzIzNjc1NzUzMw==&mid=2247520898&idx=4&sn=25f400faafb55fb32f85ccde8e850ef2&chksm=e8d025f0dfa7ace61021547f5eb5090f6e1f2ab0fe12944218f56a92e6e48dce8c14ae044250&mpshare=1&scene=1&srcid=&key=90581f21d61583cc172f1a54031ccba5056ef3d9b7ae3fa6c75938913ac9f6d4df2b5cacd176d8b1c89513d768357811c697bff73ac271190c8da6fb85d3c4674dda60930d475f157defdabc235f927e&ascene=1&uin=MjMzNDA2ODYyNQ%3D%3D&devicetype=Windows+10&version=62060739&lang=zh_CN&pass_ticket=ZcEDNskDGNPvX7oVWyn5i2vjhb9%2BBrSBrsQB1%2BEKcMDuxlsuwOud%2BcXWDPOd1XyS)

**加入社群**

量子位AI社群开始招募啦，量子位社群分：AI讨论群、AI+行业群、AI技术群；



欢迎对AI感兴趣的同学，在量子位公众号（QbitAI）对话界面回复关键字“微信群”，获取入群方式。（技术群与AI+行业群需经过审核，审核较严，敬请谅解）



![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtCQYLj62wpY5xicKlLfDCpKV2aTXlvJODSNPV9Q3zHNEu7UibkwluIwr0TN705vZawerScqBhC67HDQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



**量子位** QbitAI · 头条号签约作者





վ'ᴗ' ի 追踪AI技术和产品新动态



喜欢就点「在看」吧 !











微信扫一扫
关注该公众号