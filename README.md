**Notice:** This repository is not operated or maintained by /u/deepfakes. Please read the explanation below for details.
**Notice:** 此代码不由 /u/deepfakes 维护。请阅读以下解释说明获取更多信息。
# deepfakes_faceswap

Faceswap 是一个通过深度学习来识别和替换图片和视频中人物脸庞的工具。
![Screenshots](https://i.imgur.com/nWHFLDf.jpg)

<p align="center">
  <a href="https://www.youtube.com/watch?v=r1jng79a5xc"><img src="https://img.youtube.com/vi/r1jng79a5xc/0.jpg"></img></a>
<br />大表姐/Steve Buscemi Faceswap using the Villain model
</p>

在开始前请先查阅[INSTALL.md](INSTALL.md)。

- [声明](#manifesto)
- [如何安装运行项目](#how-to-setup-and-run-the-project)
  - [Overview](#overview)
  - [Extract](#extract)
  - [Train](#train)
  - [Convert](#convert)
  - [GUI](#gui)
  - [General notes:](#general-notes)
- [Help I need support!](#help-i-need-support)
  - [Discord Server](#discord-server)
  - [Faceswap-Playground](#faceswap-playground)
- [Donate](#donate)
  - [@torzdf](#@torzdf)
  - [@andenixa](#andenixa)
  - [@kvrooman](#@kvrooman)
- [How to contribute](#how-to-contribute)
  - [For people interested in the generative models](#for-people-interested-in-the-generative-models)
  - [For devs](#for-devs)
  - [For non-dev advanced users](#for-non-dev-advanced-users)
  - [For end-users](#for-end-users)
  - [For haters](#for-haters)
- [About github.com/deepfakes](#about-githubcomdeepfakes)
  - [What is this repo?](#what-is-this-repo)
  - [Why this repo?](#why-this-repo)
  - [Why is it named 'deepfakes' if it is not /u/deepfakes?](#why-is-it-named-deepfakes-if-it-is-not-udeepfakes)
  - [What if /u/deepfakes feels bad about that?](#what-if-udeepfakes-feels-bad-about-that)
- [About machine learning](#about-machine-learning)
  - [How does a computer know how to recognise/shape a faces? How does machine learning work? What is a neural network?](#how-does-a-computer-know-how-to-recogniseshape-a-faces-how-does-machine-learning-work-what-is-a-neural-network)

---
## 声明

### Faceswap 不是为了色情而生。

当 faceswaping 刚开发完成并发布时, 此项技术是破天荒的，它是AI发展进程中很大的一个进步。但它同时也被学术界所忽视。它的代码混乱且零碎，它要求对AI相关技术非常了解且付出大量努力才能使用它。终于有人把它整合。它终于成功的跑起来了，它像互联网中出现的其它新技术一样，它被立刻用来制作色情片。那么问题来了，这代码谁都可以下载运行而不必先读得PHD，也不必掌握数学，计算机理论，心理学等知识。在deepfake出现前AI技术就像黑魔法，只有那些读了很多书很多论文的人才有能力接触参与。
When faceswaping using an AI was first developed and became published, the technology was groundbreaking, it was a huge step in AI development. It was also completely ignored outside of academia. The code was confusing and fragmentary, it required a thorough understanding of state of the art AI techniques and a lot of effort to get anything out of it. One individual brought it together into one cohesive collection. It ran, it worked, and as is so often the way with new technology emerging on the internet, it was immediately used to create porn. The problem was that this was the first AI code that anyone could download, run and learn by experimentation without becoming a PHD candidate in math, computer theory, psychology, and more. Before "deepfakes" these techniques were like black magic, only practiced by those who could understand all of the inner workings as described in esoteric and endlessly complicated books and papers.

“Deepfakes”的出现改变了这一切，让任何人都可以参与AI的开发。对于开发者，这些代码开启了一个非常棒的学习机会。可以出点子，也可以和大牛共同开发，为这项新兴技术做出贡献，随着技术的发展，最终这项技术将应用与各个主流场景。
"Deepfakes" changed all that and anyone could participate in AI development. To us developers, the release of this code has opened up a fantastic learning opportunity. To build on ideas developed by others, to collaborate with coders with a huge variety of skills, to experiment with AI whilst learning new skills and ultimately contribute towards an emerging technology which will only see more mainstream use as it progresses.

是否有人在用相似的软件做一些糟糕的事情？显然，也正因为如此，开发者们开始遵循严格的道德标准。我们中的很多人甚至都没用此软件创建过视频，我们只是在修补代码看看它能做些什么。可惜，媒体只关注这软件的黑暗面。它可以作恶并不是我们创造它的目的，刀可以做菜也可以杀人（我加的，老外讲的有点啰嗦），让我们更加的关注这款软件的未来，我们的愿景是希望这款软件作为一个学习试验的工具让更多的开发者参与。
Are there some out there doing horrible things with similar software? Yes. And because of this, the developers have been following strict ethical standards. Many of us don't even use it to create videos at all, we just tinker with the code to see what it all does. Sadly, the media concentrates only on the unethical uses of this software. That is unfortunately a nature of how it was first exposed to the public, but it is not representative of why it was created, how we use it now, or what we see in its future. Like any technology, it can be used for good or it can be abused. It is our intention to develop faceswap in a way that its potential for abuse is minimized whilst maximizing its potential as a tool for learning, experimenting and, yes, for legitimate faceswaping.

我们不是在诽谤或妖魔化某些组织或个体。我们是程序员，工程师，好莱坞视觉特效师，我们激情，我们热爱，我们都是鲜活的人。我们觉得是时出台一个标准声明来定义此款软件的可为和不可为。
- Faceswap 不是为了创作色情
- Faceswap 不是为了未经同意或蓄意掩饰改变他人面孔
- Faceswap 不是为了进行违法，不道德，有待商榷的目的而使用
- Faceswap 是为了实验，发展AI技术，及各种合理，道德的使用
We are not trying to denigrate celebrities or to demean anyone. We are programmers, we are engineers, we are Hollywood VFX artists, we are activists, we are hobbyists, we are human beings. To this end, we feel that it's time to come out with a standard statement of what this software is and isn't as far as us developers are concerned.

- Faceswap is not for creating porn
- Faceswap is not for changing faces without consent or with the intent of hiding its use.
- Faceswap is not for any illicit, unethical, or questionable purposes.
- Faceswap exists to experiment and discover AI techniques, for social or political commentary, for movies, and for any number of ethical and reasonable uses.

面对此软件现在被各种不道德的使用的事实，我们非常的困扰。尽管如此，我们依然愿意在教育，学习，ai技术，工具方面有兴趣的人给予支持。同时我们将对非法及非道德的使用持零容忍态度。同时也将极力阻止此类应用扩散。
We are very troubled by the fact that faceswap can be used for unethical and disreputable things. However, we support the development of tools and techniques that can be used ethically as well as provide education and experience in AI for anyone who wants to learn it hands-on. We will take a zero tolerance approach to anyone using this software for any unethical purposes and will actively discourage any such uses.

## 如何安装和运行项目
Faceswap 是Python编写可运行于多个操作系统包括Windows, Linux, MacOS。
## How To setup and run the project
Faceswap is a Python program that will run on multiple Operating Systems including Windows, Linux and MacOS.

查看 [INSTALL.md](INSTALL.md) 获取安装介绍，你需要一个支持CUDA的GPU以获得最好运行性能。
See [INSTALL.md](INSTALL.md) for full installation instructions. You will need a modern GPU with CUDA support for best performance.

## 总览
该项目有多个开始准备，你必须：
 - 收集图片（或者直接使用下面提供的训练数据）
 - **解析** 出原图中的脸孔
 - **训练** 一个基于你的图片的模型（或者直接使用下面提供的训练数据）
 - **转化** 使用模型来转化资源

查阅[USAGE.md](USAGE.md)来获取更详细的介绍。
## Overview
The project has multiple entry points. You will have to:
 - Gather photos (or use the one provided in the training data provided below)
 - **Extract** faces from your raw photos
 - **Train** a model on your photos (or use the one provided in the training data provided below)
 - **Convert** your sources with the model

Check out [USAGE.md](USAGE.md) for more detailed instructions.

### 解析
进入setup目录，执行 `python faceswap.py extract`将`src`目录中的图片的脸孔解析到`extract`目录。
### Extract
From your setup folder, run `python faceswap.py extract`. This will take photos from `src` folder and extract faces into `extract` folder.

### 训练
进入setup目录，执行`python faceswap.py train`将从两个图片文件夹开始训练一个模型并保存进`models`目录。
### Train
From your setup folder, run `python faceswap.py train`. This will take photos from two folders containing pictures of both faces and train a model that will be saved inside the `models` folder.

### 转化
进入setup目录，执行`python faceswap.py convert`将从`original`目录中的图片换成新脸后保存在`modified`目录中。
### Convert
From your setup folder, run `python faceswap.py convert`. This will take photos from `original` folder and apply new faces into `modified` folder.

### GUI
你也可以通过执行`python faceswap.py gui`来跑GUI。
### GUI
Alternatively you can run the GUI by running `python faceswap.py gui`

## 常识：
- 所有脚本都可以 `-h`/`--help`来获取帮助信息，你懂的。
## General notes:
- All of the scripts mentioned have `-h`/`--help` options with arguments that they will accept. You're smart, you can figure out how this works, right?!

NB: 关于转化视频，则使用这个命令`python tools.py effmpeg -h`，原理就是将视频转图片，转化图片之后再转回视频，也可以使用[ffmpeg](https://www.ffmpeg.org)这个工具。
NB: there is a conversion tool for video. This can be accessed by running `python tools.py effmpeg -h`. Alternatively you can use [ffmpeg](https://www.ffmpeg.org) to convert video into photos, process images, and convert images back to video.

**提示**
**Some tips:**

利用现有的模型会比从新开始训练来的快很多。
如果训练数据不够，可以用长的像的来替代。
Reusing existing models will train much faster than starting from nothing.
If there is not enough training data, start with someone who looks similar, then switch the data.

## 当你需要帮助支持！
## Help I need support!
### 论坛
你最好加入[Faceswap Discord server](https://discord.gg/FdEwxXd)。那里有很多热心人愿意提供帮助。注意，论坛及本仓库拒绝讨论色情相关内容。
### Discord Server
Your best bet is to join the [Faceswap Discord server](https://discord.gg/FdEwxXd) where there are plenty of users willing to help. Please note that, like this repo, this is a SFW Server!

### Faceswap 闲谈区
你也可以在[Faceswap Playground](https://github.com/deepfakes/faceswap-playground)进行提问。但别提太普遍的问题，"比如faceswap怎么使用？"
### Faceswap-Playground
Alternatively you can post questions in the [Faceswap Playground](https://github.com/deepfakes/faceswap-playground). Please do not post general support questions in this repo.

## 捐献
开发者们夜以继日的开发和改进faceswap。花费了大量的时间才让软件发展至今日模样，此过程并没有任何的回报。如果你喜欢此软件，请考虑对开发组进行捐献，以便让他们可以花更多的时间进行改进。
## Donate
The developers work tirelessly to improve and develop faceswap. Many hours have been put in to provide the software as it is today, but this is an extremely time consuming process with no financial reward. If you enjoy using the software, please consider donating to the devs, so that they can spend more time implementing improvements.

### @torzdf ###
 绝大多数代码 this guy torzdf都参与了，包括并不仅限于，GUI的实现，FAN aligner, MTCNN detector and porting the Villain, DFL-H128 and DFaker models to faceswap。
### @torzdf ###
 There is very little faceswap code that hasn't been touched by torzdf. He is responsible for implementing the GUI, FAN aligner, MTCNN detector and porting the Villain, DFL-H128 and DFaker models to faceswap, as well as significantly improving many areas of the code.

**Bitcoin:** 385a1r9tyZpt5LyZcNk1FALTxC8ZHta7yq

**Ethereum:** 0x18CBbff5fA7C78de7B949A2b0160A0d1bd649f80

**Paypal:** [![torzdf](https://www.paypalobjects.com/en_GB/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=JZ8PP3YE9J62L)

### @andenixa ###
Unbalanced and OHR models的创建者，以及为模型训练扩展了许多功能。Andenixa现在攻克新的模型，希望可以收到资助。
### @andenixa ###
Creator of the Unbalanced and OHR models, as well as expanding various capabilities within the training process. Andenixa is currently working on new models and will take requests for donations.

**Paypal:** [![andenixa](https://www.paypalobjects.com/en_GB/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=NRVLQYGS6NWTU)

### @kvrooman ##
负责让转化器代码更加茁壮，添加修复了很多模型的代码使之更加的稳定，同时还显著推进了训练相关代码的模块化进程。Kvrooman仍在积极贡献代码。
### @kvrooman ###
Responsible for consolidating the converters, adding a lot of code to fix model stability issues, and helping significantly towards making the training process more modular, kvrooman continues to be a very active contributor.

**Ethereum:** 0x18CBbff5fA7C78de7B949A2b0160A0d1bd649f80

## 如何参与贡献
## How to contribute

### 对创建模型感兴趣的人
 - 去 'faceswap-model' 这里讨论，建议，提交针对当前算法的改进。
### For people interested in the generative models
 - Go to the 'faceswap-model' to discuss/suggest/commit alternatives to the current algorithm.

### 写给开发者
 - 读完整个README
 - Fork the repo
 - 下载上面链接里提供的数据
 - 把弄它
 - 查阅dev标签的issues
 - 对机器视觉及openCV感兴趣的，查阅有'openCV'标签的issues。欢迎提交改进
### For devs
 - Read this README entirely
 - Fork the repo
 - Download the data with the link provided above
 - Play with it
 - Check issues with the 'dev' tag
 - For devs more interested in computer vision and openCV, look at issues with the 'opencv' tag. Also feel free to add your own alternatives/improvments

### 写给非开发者的进阶用户
 - 读完整个README
 - Clone the repo
 - 下载上面链接里提供的数据
 - 把弄它
 - 查阅advuser标签的issues
 - 在'faceswap-playground'里帮助他人
### For non-dev advanced users
 - Read this README entirely
 - Clone the repo
 - Download the data with the link provided above
 - Play with it
 - Check issues with the 'advuser' tag
 - Also go to the 'faceswap-playground' repo and help others.

### For end-users
 - Get the code here and play with it if you can
 - You can also go to the 'faceswap-playground' repo and help or get help from others.
 - Be patient. This is relatively new technology for developers as well. Much effort is already being put into making this program easy to use for the average user. It just takes time!
 - **Notice** Any issue related to running the code has to be open in the 'faceswap-playground' project!

### For haters
Sorry, no time for that.

# About github.com/deepfakes

## What is this repo?
It is a community repository for active users.

## Why this repo?
The joshua-wu repo seems not active. Simple bugs like missing _http://_ in front of urls have not been solved since days.

## Why is it named 'deepfakes' if it is not /u/deepfakes?
 1. Because a typosquat would have happened sooner or later as project grows
 2. Because we wanted to recognize the original author
 3. Because it will better federate contributors and users

## What if /u/deepfakes feels bad about that?
This is a friendly typosquat, and it is fully dedicated to the project. If /u/deepfakes wants to take over this repo/user and drive the project, he is welcomed to do so (Raise an issue, and he will be contacted on Reddit). Please do not send /u/deepfakes messages for help with the code you find here.

# About machine learning

## How does a computer know how to recognise/shape a faces? How does machine learning work? What is a neural network?
It's complicated. Here's a good video that makes the process understandable:
[![How Machines Learn](https://img.youtube.com/vi/R9OHn5ZF4Uo/0.jpg)](https://www.youtube.com/watch?v=R9OHn5ZF4Uo)

Here's a slightly more in depth video that tries to explain the basic functioning of a neural network:
[![How Machines Learn](https://img.youtube.com/vi/aircAruvnKk/0.jpg)](https://www.youtube.com/watch?v=aircAruvnKk)

tl;dr: training data + trial and error
