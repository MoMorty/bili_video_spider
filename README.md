# 哔哩哔哩全站视频信息爬虫(可能会漏爬)

*B 站感觉最近几年发展得太快了,不由得想知道有多少视频,翻阅了一大半网络找了很多爬虫感觉都不是特别的复合自己的胃口(挑食~),于是自己写一个(才学习爬虫没多久写得垃圾代码大佬别喷我啊....)*



**开发环境: Windows10 + Python3**

**工具: VSCode**

准备工作

## 安装

#### Python3

安装`Python`这些就麻烦自己百度吧..

#### 依赖

```
pip3 install -r requirements.txt
```

#### 运行

```
python3 bili_video_get.py
```

### 代码部分

![](img/5.png)



### 运行结果截图(出现各种403,或访问权限不足请不要在意)

![](img/4.png)

#### 保存本地结果

![](img/1.png)



## 思路

通过浏览器打开网页url,打开`开发者工具`(F12),点击`Network`,点击`JS`,刷新(F5),找到 `api`地址

![](img/2.png)

复制下来，去除没必要的内容，得到 <https://api.bilibili.com/x/web-interface/archive/stat?aid=15906633> ，用浏览器打开，会得到如下的 json 数据

 ```
{
	"code":0,
	"message":"0",
	"ttl":1,
	"data":{
		"aid":15666899,
		"view":4422,
		"danmaku":2,
		"reply":12,
		"favorite":28,
		"coin":4,
		"share":48,
		"like":1,
		"now_rank":0,
		"his_rank":0,
		"no_reprint":0,
		"copyright":2
		}
}
 ```

所以通过 访问 `api`,得到数据,解析,然后保存到数据库或者保存到本地......我差不多爬了半天左右,出去吃个饭回来看了看,逛了一个某乎,然后电脑就蓝屏了.....数据就没爬完,打算放Linux下爬,由于这个脚本只在`Windows10`上测试过,在其他环境测试请自己动手改一下保存`本地地址`......

![](img/3.png)

# 免责申明

## 本爬虫只用于个人学习,切勿用于其他用途,否则出现一切问题作者概不负责.
