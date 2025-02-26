

# 大模型代码生成

llm_code_genration
- [公众号](https://mp.weixin.qq.com/s/jbbTPy_zkZIfRUH8wjkSGA) 含演示视频
- [知乎](https://zhuanlan.zhihu.com/p/26477848381)

## 模型

参赛模型
- DeepSeek 等多种模型
- 以 AskManyAI 上免费模型为准

![](https://pica.zhimg.com/v2-160f1c31cba75d5aebd283363578ff74_1440w.jpg)

![](https://pic3.zhimg.com/v2-05b9ad48fab585bce59a638b3e9a904c_1440w.jpg)


## 评估

评估维度：
- 功能完整度
- 页面美观度
- 数据准确性
- 自我认知


## 总结


### 玉虚宫列表页

总结（60分及格，低分不计入榜单）
- 功能完成度：OpenAI o3-mini＞GPT-4o-mini=DeepSeek R1满血版＞DeepSeek V3＞Gemini-2 Flash
- 页面美观度：OpenAI o3-min=DeepSeek R1满血版＞DeepSeek R1联网版＞GPT-4o-mini＞Gemini-2 Flash
- 数据准确度：DeepSeek V3＞DeepSeek R1联网版＞OpenAI o3-mini＞＞Gemini-2 Flash＞GPT-4o-mini=DeepSeek R1满血版＞豆包 1.5-Pro
- 自我认知：全部失败，只有DeepSeek能报出模型名（不过是GPT-4）

整体：openai系列模型与DeepSeek靠前，OpenAI o3-mini≈DeepSeek R1

![](https://pic4.zhimg.com/v2-47a801dd0921b9877bc311ff3b8f19cb_1440w.jpg)


### 玉虚宫抽签页

总结（60分及格，低分不计入榜单）
- 功能完成度：DeepSeek V3＞Gemini-2 Flash＞豆包 1.5-Pro＞OpenAI o3-mini
- 页面美观度：DeepSeek V3＞DeepSeek R1满血版=DeepSeek R1联网版=Gemini-2 Flash＞豆包 1.5-Pro
- 数据准确度：DeepSeek R1满血版=豆包 1.5-Pro＞DeepSeek R1联网版=OpenAI o3-mini=Gemini-2 Flash＞GPT-4o-mini
- 自我认知：全部失败，只有DeepSeek能报出模型名（不过是GPT-4）

整体：DeepSeek V3强于DeepSeek R1=openai系列

![](https://pic1.zhimg.com/v2-2185f2f980835b7e02b5b4c27b9ec736_1440w.jpg)

## 效果

页面效果展示


### 单词本

![](https://pic2.zhimg.com/v2-c91fcf9d062749ce2cbeda60d63e1ca9_1440w.jpg)

### 简易抽签系统


![](https://pica.zhimg.com/v2-c759f5bb8d802e77535408b25dba32a0_1440w.jpg)


### 玉虚宫

![](https://pic4.zhimg.com/v2-25d22a39f6ea4e3758ec3e4ba0e02241_1440w.jpg)

#### 玉虚宫列表页

![](https://pic3.zhimg.com/v2-33af0b5f909f7d66818f62fdb33c1ce8_1440w.jpg)

![](https://pic3.zhimg.com/v2-a67535d1414a1fecb51cb8ea6312b37c_1440w.jpg)

#### 玉虚宫抽签页

![](https://pic2.zhimg.com/v2-1bad31a7a7c32c955c73fc5c7317d4d3_1440w.jpg)

![](https://picx.zhimg.com/v2-cca9b598c549fc1dd2896a4f5a333d73_1440w.jpg)

## 提示语集合

### 小红书单词卡

```md
生成一段html,js代码，实现功能：逐项卡片展示数组a里的项目
布局要求：第一行加粗展示“RedNote Slangs for TiktokRefugee”，其次再展示卡片，每行3个卡片，超过后另起一行，每个卡片浅蓝色背景，卡片是云朵颜色，3个字段字体颜色依次是红色、绿色、紫色，点击卡片后自动放大，要求简洁、美观、立体效果、配色好看；
数据：国内常用网络用语，每个短语包含字段：中文短语、英文短语、英文解释；以 javascript list 输出, 示例 [['a', 'a', 'a']]；注意：只输出代码，不要解释
````

### 玉虚宫抽签系统


#### 列表页

提示语

```md
请用 前端代码 写一个信息栏, 代码放在一个html文件里, 可运行.

界面要求
- 天蓝色背景, 几个边缘模糊的云朵，随机分布在页面内, 从左往右匀速飘过, 右上角有太阳,边缘模糊, 光芒四射
- 页面中间显示标题 【玉虚宫抽签系统】, 大号字体, 加粗，下面另起一行, 显示当前调用的模型名称 model;
- 中间依次显示多张卡片,扑克牌风格，大小根据页面自动适配, 立体效果, 小幅晃动
- 卡片从左到右，每行6个，依次铺开，逐个显示 candidate 里的人物: 头像地址来自 url, 图片大小超出范围时，缩放; 
- 人物姓名来自 name, 隶书, 大号字体, 红色, 金色边缘
- 卡片上逐个字段显示人物信息, 字段逐行显示, 雅黑, 中号字体, 绿色, 白边；
- 鼠标点击卡片时，放大，周围金光闪烁
- 页面可以滚动下滑

附加信息：
- 模型名称: model, 存储这个指令 "你是什么模型,直接返回模型名" 返回结果
- 候选人物集合信息：姓名 name, 头像地址 url

```json
candidate =  [
    { "name": "哪吒", "url": "哪吒2/哪吒.jpg",},
    { "name": "敖丙", "url": "哪吒2/敖丙.jpg",},
    {"name": "敖光","url": "哪吒2/敖光.jpg",},
    {"name": "敖闰","url": "哪吒2/敖闰.jpg",},
    { "name": "李靖", "url": "哪吒2/李靖.jpg",},
    { "name": "申公豹", "url": "哪吒2/申公豹.jpg",},
    { "name": "无量仙翁", "url": "哪吒2/无量仙翁.jpg",},
    { "name": "鹤童", "url": "哪吒2/鹤童.jpg",},
    { "name": "鹿童", "url": "哪吒2/鹿童.jpg",},
    { "name": "元始天尊", "url": "哪吒2/元始天尊.png",},
    { "name": "土拨鼠", "url": "哪吒2/土拨鼠.jpg",},
    {"name": "太乙真人","url": "哪吒2/太乙真人.jpg",},
    {"name": "殷夫人","url": "哪吒2/殷夫人.jpg",},
    {"name": "申小豹","url": "哪吒2/申小豹.jpg",},
    {"name": "石矶娘娘","url": "哪吒2/石矶娘娘.jpg",},
    {"name": "结界兽","url": "哪吒2/结界兽.jpg",},
    {"name": "海夜叉","url": "哪吒2/海夜叉.jpg",}
]
```

注意:
- 先查找人物个人信息, 并存储到对应字段上, 年龄 age,技能 skill,性格 character
- 所有文字信息都在卡片上叠加
```

#### 抽签页


```md

请用 前端代码 写一个点名系统, 代码放在一个html文件里, 可运行.

界面要求
- 天蓝色背景, 几个边缘模糊的云朵，随机分布在页面内, 从左往右匀速飘过, 右上角有太阳,边缘模糊, 光芒四射
- 页面中间显示标题 【玉虚宫抽签系统】, 大号字体, 加粗，下面另起一行, 显示当前调用的模型名称 model;
- 中间显示1张卡片,扑克牌风格，大小根据页面自动适配, 立体效果
- 卡片右侧显示两个按钮："开始点名" 绿色椭圆, "停止按钮" 红色椭圆, 都是立体效果

交互要求
- 点击“开始点名”按钮，抽签开始，卡片呈现小幅闪动
- 系统自动播放扑克牌样式的卡片；
- 卡片内容是集合里某个人物, 卡片内是人物头像, 来自 url, 图片大小超出范围时，缩放. 
- 卡片上浮动显示当前人物姓名 name, 隶书, 大号字体, 红色, 金色边缘
- 抽签前，卡片显示内容源自 "name": "人物姓名", "url": "哪吒2/电影.jpg"
- 点击“停止”按钮，轮播中止。
- 系统显示当前抽中的人物，并放大突出显示，周围是金色光照
- 卡片上逐个字段显示人物信息, 字段逐行显示, 雅黑, 中号字体, 绿色, 白边 


附加信息：
- 模型名称: model, 存储这个指令 "你是什么模型,直接返回模型名" 返回结果
- 候选人物集合信息：姓名 name, 头像地址 url

```json
[
    { "name": "哪吒", "url": "哪吒2/哪吒.jpg",},
    { "name": "敖丙", "url": "哪吒2/敖丙.jpg",},
    { "name": "李靖", "url": "哪吒2/李靖.jpg",},
    { "name": "申公豹", "url": "哪吒2/申公豹.jpg",},
    { "name": "无量仙翁", "url": "哪吒2/无量仙翁.jpg",},
    { "name": "鹤童", "url": "哪吒2/鹤童.jpg",},
    { "name": "鹿童", "url": "哪吒2/鹿童.jpg",},
    { "name": "元始天尊", "url": "哪吒2/元始天尊.png",},
    { "name": "土拨鼠", "url": "哪吒2/土拨鼠.jpg",},
    {"name": "太乙真人","url": "哪吒2/太乙真人.jpg",},
    {"name": "殷夫人","url": "哪吒2/殷夫人.jpg",},
    {"name": "申小豹","url": "哪吒2/申小豹.jpg",},
    {"name": "石矶娘娘","url": "哪吒2/石矶娘娘.jpg",},
    {"name": "敖光","url": "哪吒2/敖光.jpg",},
    {"name": "敖闰","url": "哪吒2/敖闰.jpg",},
    {"name": "结界兽","url": "哪吒2/结界兽.jpg",},
    {"name": "海夜叉","url": "哪吒2/海夜叉.jpg",}
]
```

注意:
- 先查找人物个人信息, 并存储到对应字段上, 年龄 age,技能 skill,性格 character
```


## 其他



