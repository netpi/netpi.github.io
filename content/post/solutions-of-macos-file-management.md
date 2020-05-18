---
title: '"多多益善"的MacOS文件管理方案'
date: 2020-05-08T01:45:20+08:00
categories:
- MacOS效率提升
tags:
- 效率
- MacOS
keywords:
- 效率
- MacOS
description: 满足快速决策、自动执行、归类有序、查阅便捷的文件管理方案，便是节省心力、且一劳永逸的。
keywords: 效率 MacOS

---

汉高祖刘邦曾问大将韩信：“你看我能带多少兵？”韩信斜了刘邦一眼说：“你顶多能带十万兵吧！”汉高祖心中有三分不悦，心想：你竟敢小看我！“那你呢？”韩信傲气十足地说：“我呀，当然是多多益善啰！”

大将运兵多多益善，即使统领百万雄兵也能做到运筹帷幄。可军队数量也不是越多越好，如若统领不当，数量太多的军队反而会拉低胜利的可能性。淝水之战中，坐拥八十万大军的苻坚自恃兵力强大，可他将才不足且用人不力，最终败给了兵力仅八万的东晋军。

管理文件如同带兵，文件数量越多越杂，管理的门槛也就越高。合适文件管理方案，可以让计算机井然有序、效率提升、事半功倍。可如若管理不当，大量繁杂的文件很容易使我们的时间被浪费、心力被消耗、灵感被扼杀。

本文所介绍的是一个“多多益善”文件管理方案，且同时满足了**快速决策、自动执行、归类有序、查阅便捷**四个要点。

面对待整理的文件，我们要能够像大将军一样的**快速决策**，或者说快速反应“发号施令”，而文件便会**自动执行**到它该去的地方，就好像将军下令“立刻回营（command）”，将军不必知道士兵（file）营地的具体位置(path)，士兵便会自己回到的营地。当然，实现自动化的前提是所有文件都要**归类有序**，文件要提前被规划好路径。规划路径就好比步兵、炮兵默认被规划到了到陆军大本营，军医、炊事员默认归属后勤保障阵地，只有做到归类合理有序，士兵才能自动归位，以便于管理。最后便是**查阅便捷**，做到大量文件多维、快速、便捷的检索。

对我而言，满足以上条件的文件管理方案，便是节省心力、且一劳永逸的。

PS. 文章最后会提供本方案所涉及到的所有工具、hazel规则、Smart Folder、以及安装方法。笔者推荐先阅读全文掌握原理之后再setup。当然你也可以跳过前四部分，直接阅读5. 配置并使用。



## 0.效果展示

![](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/ijnwc.gif)



## 1.快速决策

你喜欢做选择题还是喜欢做填空题？我想大多数人的答案都会是选择题。有时候我们面对突如其来的填空问题，大脑会一片空白，无法决策。例如有时候某个人的名字“挂在嘴边”但就是想不起来。这叫“舌尖现象”，英文tip of the tongue phenomenon，简称TOT。TOT现象虽然很常见，但是却不会出现在选择题中，我们看到选项时，大脑的“短路”就接通了，TOT现象也就消失了。

我们来看下一个典型场景：如何处理你桌面上的foo.pdf文件呢？

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/taulo.jpg)

按照以往的模式，我们会想把它拖动到某个文件夹下，具体应该在哪个文件夹下呢，可能一下子“脑筋短路”想不起来... 这种“脑筋短路”也属于TOT现象，反复多次便是非常消耗心力的事情，随着文件的增多繁复，这种隐性消耗会使我们不断徒增疲惫。

为了避免TOT现象的出现，我们要尽量避免填空题，而改做选择题，当把处理foo.pdf变成一道选择题，情况将会大大改善。

### 1-1.通过选择标签来下发指令

foo.pdf 下出现了几个可决策的选项，你要做的事情是通过选择Tag来快速决策如：

- localSaved&mark自动归类到本地目录（具体参看：3-1.目录结构优化）
- iCloudSaved&mark自动归类到云端目录
- mark只标记 （便于搜索）

有了这些选项，我们便能够轻松的快速决策了。

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/ial3p.png)



通过选择标签下发指令还有个最大优势是：同时操作多个文件。

一次性为多个不同类型文件下达指令后，所有文件便能自己找到方向各归其所。

就好像总司路一声令下，三军几十个兵种都能各自找到方向，回到属于自己的营地。

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/k5hny.png)

### 1-2.快捷添加Tags的方法

以上添加Tags方式一定要使用快捷键才能完成，我个人把加Tags的快捷设置为：command+e

关于给标签加快捷键的方法，请参考：https://medium.com/innovation-design/how-to-add-a-shortcut-for-finder-tags-on-macos-mojave-65d1502ffd98

## 2.自动执行

指令下达之后，就要执行了，这时候我们要用到一个软件 Hazel ，可以帮助我们完成文件的自动化管理。Hazel就像一个会魔法的女巫，文件被她的小毛胆轻轻一扫，便具有了生命。

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/wnkwj.png)



Hazel 不做过多介绍，软件使用方法推荐少数派文章[点击查看](https://sspai.com/post/35212)。

我要介绍的是，本方案中Hazel的使用思路。

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/vu6gl.png)

*PS. 文章最后会提供本方案的Hazel规则，可直接下载安装。*

如上图，我们把触发条件设置成只要Tags里包含 localSaved&mark 便会触发下面的执行步骤。 

1. 系统会run shell script，这个脚本的作用使把文件归类到它的“大本营”（在3.归类有序中说明）
2. 移除 Tag localSaved&mark ，目的是避免Hazel条件二次触发
3. 添加 Tag marked 便于搜索（在4.查找便捷中说明）

通过Hazel的魔法，文件便神奇的像“长了腿似的”，在接受到收到指令后，便一往无前的奔向他的目的地。

### 3.归类有序

空间感影响着我们的心理，我们的心理感受与空间感是有相对关联的。例如中国的汉字中就往往用大方、小气、仔细、粗心等带有空间感的词汇来表述褒贬。美国耶鲁大学的心理学家Lawrence E.Williams通过实验发现，人们看到的物体之间的物理距离自动地在人的脑海中转换成抽象的心理距离，并影响我们对外部世界的判断。看见的物体之间距离越远，心理距离也就越开阔，人也会越乐观积极，看到的物体间物理距离越近，人就会变的更加悲观和紧张。

### 3-1.干净有序的目录结构

我们看到的电脑桌面是否干净，会对我们一整天的心情有影响。

`~/Desktop`、`~/Documents`、`~/Downloads` 保持干净，这三个文件夹只做临时使用，绝大部分时间这三个文件夹都是空的。

平时存放在以上三个文件夹中的文件全部归类到下面这个目录中：~/Marked_local

~/Marked_local 将集中存放大部分文件，它是所有文件的总兵营，被Tag为localSaved&mark的文件都会自动的进入这个文件夹， 并在文件夹中自动分类到子文件夹中。

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/zdrfs.png)

如上图所看到的，文件进入到~/Marked_local 之后，又被进行了两次分类。

第一次分类按照Apple的 [Uniform Type Identifiers](https://developer.apple.com/library/archive/documentation/Miscellaneous/Reference/UTIRef/Articles/System-DeclaredUniformTypeIdentifiers.html) ，以及我个人摸索的，且适合大多数人的分类方式将文件分成9个一级分类

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/7frr3.png)

**第二次分类我们根据文件元数据中的Kind。**

例如brewinstall.sh文件的一级分类属于Source-code，二级分类的Kind类型是Shell Script。那么文件最后会分类到~/Marked_local/Documents/Shell Script/brewinstall.sh

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/8zena.png)



### 3-2.文件重命名

苏东坡说：“世间唯名实不可欺”。

此话对于计算机文件来说更加适用，例如我们可以通过文件名后缀来判断文件类型是.JPG还是.PDF(最正确的参看文件类型的方式是通过元数据，但在无恶意篡改类型的情况下通过文件名最为快捷)。

文件名中适当加入元数据中的内容，可以让使用者一眼快速了解文件。而且统一规律的文件命名可以让文件系统整齐划一，排列有序。

因此本方案在文件文件归类的同时，也为文件做了重命名。

重命名的规则为：年-月-文件名（创建时间）。

例如：brewinstall.sh 会被Hazel自动重命名为 2020-03-brewinstall.sh

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/2tlj6.png)

### 3-3.自动归类到 iCloud

我们为文件多增加了一个选项：同步到iCloud云端。被Tag为iCloudSaved&mark的文件将整理到 iCloud Drive/Marked_iCloud/

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/it76p.png)

Finder的侧边栏有个iCloud Drive 的文件夹，在iCloud Drive中创建的文件，会自动同步到 iCloud 云端，例如我们创建的云端大本营Marked_iCloud。

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/1znep.png)

iCloud Drive 中的Marked_iCloud

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/l0f82.png)

手机端iCloud Drive中的Marked_iCloud目录

ps.相关的Hazel规则可在文章底部下载



## 4.查阅便捷

我们都看过阅兵，各兵种列队整齐，气势雄健。领导登高而望，三军尽收眼底。

这种即能分类检阅，又能统领全军的阅兵式检阅法，就是本方案种的文件查阅法。

### 4-1 用Smart Folders查看文件

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/89nam.png)

用 Smart Folder 查看文件

使用Smart Folder可以满足我们既能分类细查、又能鸟瞰全机的需求。

苹果官方对Smart Folders的解释：

Smart Folders automatically gather files by type and subject matter. Smart Folders are updated as you change, add and remove files on your Mac.

翻译过来就是：

Smart Folders 会按类型和主题事项自动收集文件。当你更改、添加和删除 Mac 上的文件时，Smart Folders 会自动更新。

我个人的解读是：

Smart Folders里是一组依据固定搜索条件所产生的搜索结果，并且这搜索结果是实时更新的，因此Smart Folders的后缀名是.savedSearch 。

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/is4qj.png)



下面我们来看下，创建图片类搜索的Smart Folder的规则。

- Tags中包含marked， 所有被我们的Hazel管理过的文件都被自动加上marked标签
- 文件类型是image、或者Tags中包含Picture_folder(文件夹的单独处理方式)

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/09jcm.png)

这时候，点击右上角的save，便会生成一个Smart Folder，实时的更新着以上调节所产生的搜索结果。

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/pbj4w.png)

实时查看图片的Smart Folder

### 4-2 必要6的Smart Folders

想要满足我们查阅便捷的需求我们总共需要6个智能文件夹

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/phlrl.png)

- All_marked.savedSearch: 这是个鸟瞰全局的文件夹，用来通览所有被标记过的文件，对我来说最为常用。每当想找一个最近使用的文件时，只要打开它按照创建时间排序，基本上都可以快速找到。
- 其它智能文件夹代表着不同类型文件的入口，使用起来也非常的便捷。

在本方案中，智能文件夹的最大意义在于统一了入口，当文件入口被限定在6个智能文件夹中时，我们做选择的效率也会增加。即便是使用网页在需要上传图片或文件时，依然可以从智能文件夹中快速找到目标文件。

### 4-3 Smart Folders分享

既然Smart Folders是一组规则，那么也就可以分享。别人电脑生成的Smart Folders，你可以拿来直接使用，我会本方案使用到的Smart Folders放在文章末尾。

tips: 将Smart Folders拉到侧边栏时，要同时按住command键

## 5. 配置并使用

通过以上的四个部分的说明，我们知道了文件管理的流程是：

用Tags标记下达指令-->Hazel实现自动整理-->用Smart Folders查阅文件。

### 5-1.添加Tags

- 为Tags添加快捷键（参考：2-2.快捷添加Tags的方法）。
- 在Finder中添加三个 Tags 。localSaved&mark 、iCloudSave&mark、mark

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/uhull.png)

三个Tags

### 5-2.Hazel安装及规则导入

- 下载安装Hazel
- 创建两个文件夹~/Marked_local 和iCloud Drive/Marked_iCloud
- 打开Hazel，侧添加以下5个文件夹:`~/Desktop`、 `~/Documents`、`~/Downloads` 、`~/Marked_local` 、`Cloud Drive/Marked_iCloud`

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/sa70n.png)

- 倒入规则并全部勾选

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/wvtbt.png)

- 对剩下文件夹做同样操作，将规则应用到其它四个文件夹，也可以将规则选中，拖动到其它文件夹
- 启动 Hazel

### 5-3.Smart Folder 导入

- 将所有Smart Folder添加到 `~/Library/Saved Searches/`文件夹，`~/Library`是默认隐藏文件，进入Finder后按键shift+command+>可显示隐藏文件
- 按住command 将Smart Folder逐个托到侧边栏

![img](https://chendongze.oss-cn-shanghai.aliyuncs.com/ipic/m7xvt.gif)

添加Smart Folder

### 5-4 资源附件

MacOS文件管理.zip

- management.hazelrules
- SmartFolder
- All_marked.savedSearch
- Archives_marked.savedSearch
- Audios_marked.savedSearch
- Documents_marked.savedSearch
- Pictures_marked.savedSearch
- Videos_marked.savedSearch

[资源附件点击下载](https://chendongze.oss-cn-shanghai.aliyuncs.com/article/MacOS文件管理.zip)



## 参考

1. 可以自动化管理Mac文件的工具 https://www.noodlesoft.com/
2. Apple的统一类型标识符 https://developer.apple.com/library/archive/documentation/Miscellaneous/Reference/UTIRef/Articles/System-DeclaredUniformTypeIdentifiers.html
3. iCloud Drive/Marked_iCloud 的实际路径为：~ /Library/Mobile\ Documents/com\~apple\~CloudDocs/marked_iCloud/
4. 附件资源地址 [https://chendongze.oss-cn-shanghai.aliyuncs.com/article/MacOS%E6%96%87%E4%BB%B6%E7%AE%A1%E7%90%86.zip](https://chendongze.oss-cn-shanghai.aliyuncs.com/article/MacOS文件管理.zip)···