# 数据分析+金融量化+数据清洗，零基础数据分析金融量化从入门到实战课程，带你从金融基础知识到量化项目实战！【入门必备】 - P47：07 分组表交叉表透视表 - Senior数据分析媛 - BV1Ak61YVEYX

分类处理。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_1.png)

那么什么叫分类，其实分类也要分组，分组这个概念应该不陌生了。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_3.png)

我们数据库是学过分组啊，对吧啊，它其实跟数据库的分组是一个道理啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_5.png)

那我们呃这个以谁为例呢。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_7.png)

以我们这个hero这个为例啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_9.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_10.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_11.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_12.png)

以我们这个data为例啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_14.png)

它我们想分组，比如说我们现在想统计什么呢，现在我想统计近战的嗯，血上限的平均值和远程的血上限的平均值。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_16.png)

这可怎么办呢，那我们就要根据它的attrack arrange啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_18.png)

attract range来进行分组处理啊，分组的话呢一般都是要去做聚合的对吧，你像数据库的话，你分组不聚合是是有语法错误的，对吧啊，所以分组一定是伴随着聚合的，不然你分组干嘛呢，对吧啊。

分组的话一定是求每一个组内的一些，这个指指标啊，比如分组的他的平均年龄是多少，然后分组他的平均消费额是多少，分组的他们的平均购买量是多少等等等等是吧，都算这些信息啊，那这里边如果我们想根据这个。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_20.png)

近战和远程来分组的话，从语法上怎么去实现呢，这样啊，我们用这个date，我们去group by。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_22.png)

根据谁呢，根据我们这个根据谁分组，根据我们这个attract range来分组是吧，根据它来分组，这样的我们就可以得到一个data frame group by对象，就是一个分组对象啊。

就拿到这么一个分组对象，我把它记为叫group object o b j啊，这样一个分组对象，那这个分组对象呢它它是个什么样的东西呢，我们可以通过groups来查看啊，这个查看分组的情况怎么看呢。

这是分组分成两组，分成近战和远程了对吧，我们是根据这个这个列来分的，分成近战和远程，那么哪些被归为近战呢，0123456789十十一十二十七，然后到十八三十三七，这些数据被分划分为近战的这个组了。

剩下这些69等等等等。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_24.png)

这些东西被分配到远程这个组了，这就是它的分组状况啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_26.png)

那我们现在分完组之后呢，要求聚聚合聚合，关键看什么呢，比如说我想看他的最大血量的平均值。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_28.png)

那怎么做呢，我们可以根据这个分组对象啊，去调一个AGG。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_30.png)

这个里边呢我们传参，啊这个参数怎么写呢，你看这个啊AGG，然后里边可以写一个最大值和最小值啊，还有什么和是不是。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_32.png)

然后还有没有均值啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_34.png)

这没给他们写均值是吧啊，也不过也无所谓啊，因为我可以直接给一个。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_36.png)

啊，那面的话相当于把把这个我们所有能够运算的，比如说这个血量蓝上限，还有攻击范围，是不是都求出来了，求都是什么，都是均值，那我比如说想求最大值max对吧，就把每一个值的最大值都求出来了啊。

但这个roman显然它没什么用是吧，你看是这个对象类型，或者我们求这个比如最小值，这也能求出来啊，啊那他这个这个值其实是什么，它其实就是按照那个阿斯克码进行排序，得到的一个最小值啊，所以一般来讲。

这个求这个聚合，肯定是算那种那种数学指标对吧，像像这种对象类型没什么意义啊，它没什么参考价值，那这求每一个指标的一个这个数据啊，你也可以定制它啊，可以定制就是定制不同的不同的聚合函数。

比如说我现在想求的是hp max的均值，m p max的最大值，我想求这样一组数据。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_38.png)

那怎么办呢，我还是可以用这个group by啊，这个group object对象通过AACG进行传递，传什么呢，传一个字典，然后第一个呃hp max它我求什么呢，我求均值。

然后对于这个m p max我求最大值。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_40.png)

是这样。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_42.png)

我求出来的值就就是可以自己定制的啊，而他这种什么他这种是对它默认的，这个是对所有可运算的类型去求求这个均值啊，就如果没有分字段，如果只指定了函数啊，则对所有这个可以运算出结果的，这个数据求解哦。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_44.png)

那这种呢是可以根据不同的字段，定制不同的求解方式啊，求解函数。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_46.png)

那还有一种一种写法啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_48.png)

就是我们这种这种东西都可以连着写，比如说我们现在想求的是呃hp max的平均值啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_50.png)

那我不用说把这个对象单拿出来啊，一般我会这么干，直接对咱们这个data啊去group by。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_52.png)

然后根据谁啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_54.png)

根据这个attract rage啊来分组。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_56.png)

跟他分组，那得到分组对象之后呢，我们去算谁呢，去找这里边的hp a max，然后对它做什么，做平均值，直接去掉这个函数就行了是吧，这样也可以拿到啊，就这是一种这个便捷的一种写法，或者什么呢。

或者你直接在这边去调ADG对吧，因为这个东西，它是不是返回了一个什么分组对象啊是吧，那你用它去AGG，这也一样啊，但你如果是这样去AGG的话，里边你就得传什么呢，就传这个。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_58.png)

你就这么干了是吧。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_60.png)

这个就跟跟他是一个道理嘛，对不对。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_62.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_63.png)

所以说我们可以直接写写成这个样子啊，好那我们来做个练习啊，咱们来练练一下。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_65.png)

现在我们这个data这个数据是这样子的啊，我们现在呢根据职业，我们根据职业来做分组，然后来求我们的血量的平均值和攻击的最大值。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_67.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_68.png)

这应该怎么写呢。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_70.png)

根据职业来划分。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_72.png)

那么就怎么样，group by根据职业是不是这块要写这个roman啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_74.png)

嗯把roman传进去，roman传进去啊，然后呢对它我们要求那个一个是血量最大值，一个是攻血量的平均值和攻击的最大值是吧，工具价值，那么这写成head了吧，这下我们来一个说AGG啊，A g。

然后给个字典，第一个是hp max，我们去对他求什么求均值是吧，然后对于这个，attract max对它求最大值。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_76.png)

max是不是。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_78.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_79.png)

那还有一种情况是什么呢，就是我想根据先根据这个近战和远程分组，然后再根据职业来分组，只是它是多层级的分组，这样也可以啊，那我这个group里边呢就可以传一个列表就行，就是这个多层级的分组。

就是多个条件啊，data点group by，我先根据，attract range来分，然后再根据roll面来分，好先做这样一个分组，然后呢对这个分组我在求什么，求我这个血量的平均值点AGG。

然后我们求的是这个用字典来写吧，啊血量hp max min。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_81.png)

是吧，这样我可以这样，他成了什么，是不是成了一个多层级索引的表了，说两级啊啊首先近战里边啊，刺客的血量的均值是6090，坦克8300，战士6900，六千二六千八，远程里边远程里面没有刺客啊。

这时候那个谁还没上完是吧，司马懿没上完啊，司马懿上的话就远程刺客了是吧，眼睛里边没有坦克，对不对嗯，法师是那个芈月，不是坦，不是坦克吗，法坦克吗，战士6900，啊所以说一般新手都愿意玩玩这种坦克是吧。

因为血厚啊，血厚容错率高对吧，给别人多砍几刀哈，反正打得死，打不死，上线冲冲上去是吧，现在噼里啪啦一顿干，然后感觉自己好好牛逼啊是吧，哎没死啊哈好像像像我玩那个东西就比较菜啊，玩的东西比较菜。

一般就是别人打团的时候，我也我也会冲上去打团啊，人但总是打不出来伤害啊，但我还是觉得自己挺厉害的，因为老不死啊，后来发现了，原来是原来我玩的东西都是坦克啊，哈所以不爱死啊，哎刚开始玩，刚开始玩刺客时。

也是刚开始玩刺客的时候，那那会是一几年来着，就是李白李白上映，今年今年是哪年，是17年吧，今年啊今今今年是今年啊，今年是一几年，16年还是17年是吧，因为那年李白上上网，那年我也我也刚开始玩。

我又买了个李白，我说李白这好帅啊，靠买了李白哐哐就往前冲啊，折磨人怎么死，咳咳咳。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_83.png)

后来我就后来我就转型了，我就后来我这个游戏就变了，变了个玩法，我后来就变成收集皮肤收集器啊，就只收集皮肤啊，一般一般来讲干干谁干，不过你别走，换个皮肤，咱们再来一盘啊，皮肤压制啊。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_85.png)

好。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_87.png)

我们这个再说一下这个高级聚合啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_89.png)

高级数据集合，高级数据集合呢就是我们聚合函数呢，如果它满足普通的聚合函数，如果满足不了我们需求的话，我们可以去定制定制一些自定义的聚合函数，那这个自定义聚合函数我们怎么传递呢，关键就在于传的问题。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_91.png)

还还有就是我们这个自定义这个函数，它怎么去用的问题啊，这两个问题解决掉，我们就可以用了。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_93.png)

那么如果你是group分组的话，他想传这个聚合函数的话呢，用什么用apply函数恶化的时候，把这个把这个函数传进去。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_95.png)

那我们举个例子啊，比如说我现在对这个数据。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_97.png)

这个data啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_99.png)

点head，现在呢我还是根据这个我trattrack rage。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_101.png)

来分组，我date点group by，然后把这个attract range，然后我求什么呢，我求血量最大值，那hp杠max，然后去求max是吧，哎这样我求我求近战跟远程血量最大值。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_103.png)

那近战是9300，远程是6900，这是一个普通聚合对吧，这是个普通聚合函数啊，那这个东西呢它等价于什么呢，等价于这样的啊，我把这个max呢给他干掉。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_105.png)

啊这值是一样的对吧，也就是说我这个函数的调用呢，可以通过apply进行传递进行传递啊，那如果能这样传递的话，因为因为我们那个自定义函数是没法这么调的，对吧，但是呢因为这是什么。

这是data frame的聚合函数嘛对吧，所以只有data frame能调，所以如果你想给data frame对象，传递一个自定义函数，咱们用apply就能实现，那现在的问题就在于我传这个自定义函数。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_107.png)

它应该怎么去实现的问题啊，我们定义一个啊，比如我们定义一个叫，叫，Dancer max，这是dancer的max函数哈，那这个函数我你要想想研究它怎么用，就像像这种传递的时候啊，你可以在里面做一个输出。

其实无外乎就是这个参数是啥，他是啥的问题啊，好了我们看一下啊，这个我们先运行一下，然后我们对它做一个处理，这，块我apply一下，我把这个dancer max传进去，近战远程，你看啊，这是什么东西。

我还得加个加个分割线啊，再加一个分割线，不然看不清楚，看到分割线在哪啊，这有个分割线对吧，然后再往下走，这有一个分割线，那也就是说我们这个函数被调了几次。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_109.png)

这就两次。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_111.png)

为什么是两次呢，因为我们根据个track润的分组就分成两个组，是不是一个近战一个组，远程一个组啊对吧，所以说我们对于这种分组对象来讲的话，他的这个聚合函数啊，其实接收的X是啥呀，分组对象的聚合函数。

这个接收的，值是每一个分组嗯，分组它是一个集合对吧，就这么一个东西啊，你看所以说我们这个X其实什么，它是0123456789，一直到这，这其实是一个分组的，是一个什么，是不是一个series啊。

是不是servers啊，其实我们拿到的是一个sales对象啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_113.png)

那如果你知道这个参数是啥的话，那我想写聚合就就能办了啊，就有思路了，如果他是一个，每一次我们拿到的都是一个service的话，那我们要做的就是什么呢，我们应该对每一个分组都返回一个，他想要的一个值。

我们现在求的是最大值对吧，那我们就给他干嘛呢，我们就直接返回这个，X的max不就行了吗，是不是就出来了，93286900对吧，就是近战给的是9328，远程给的是6900啊，我只接两个值。

那么每一个值每一个分组给这样一个数啊，那这个数的话我们我们就求出来了啊，那那我们如果想把这个值给它，再整合到我们这个data里面去。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_115.png)

我想加一个sp max，然后再加个max是吧，那我现在相当于加一列这个hp max，最大值，那我是不是要把这个值给它写到这里面去啊，是吧，我想做这个整合的话，那怎么办呢。

比如说你近战时都应该标记这个9328，远程数应该都标记这个6900啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_117.png)

对不对，就是我想把这个数据汇总一下。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_119.png)

因为我聚合求求完之后，我这个数据肯定要汇总的嘛对吧，不然你不汇总的话，也只是只能是观测一下是吧，我想给他保留下来，那这种情况我说就合并就行了，因为他有近战，远程，近战。

远程我是可以根据这个近战和远程来合并值啊，碰到近战我给个9328，碰到远程我给个6900，对不对，是不是啊，那这样我可以这样啊，我们把这个这个结果我们记为一个result。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_121.png)

这是个series，我把它呢转换一下，Data frame，是吧，现在变成这个了啊，然后这个这个名字肯定是跟我那边会冲突的，对吧，啊我们来先做一个这个咳。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_123.png)

先做个合并吧，我想把这个这个结果，近战对应的结果和远程对应的结果，给它合到这里面去，那我就直接用这个pd点末日，左表是我们这个data，右边是我们这个result。

然后左边我们是得根据个track range来合呀，你是left on，left on等于ATTRACCURRENT，然后那write呢是write index还是write on啊，这个东西是什么。

是不是得根据它来和是不是index啊，所以把这index设置为true来这和是吧。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_125.png)

那这个是原始值，这个是新值，那我们可以把这个通过SELFIXES给他，重新设定一下是吧，原始值我们不动，然后新值我们加一个最大值是吧。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_127.png)

那这就是我们刚才聚合出来的结果啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_129.png)

我们再把它放到这个原始结果当中啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_131.png)

当然了，这最后这一步是可选的啊，你想想聚合还是不想聚合，看你这个想不想把这个值保留下来，那一般肯定是我我们求完值肯定是要保留的啊。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_133.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_134.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_135.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_136.png)

另外还有一个方式就是通过transform来传递啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_138.png)

transform的传递呢，它的它的结果其实跟这是一样的。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_140.png)

但是呢展示的方式不一样，咱们来试一下啊，我们刚才是用个plan来传递这个自定义函数啊，OPPLY来传递自定函数，然后我们看这个如果是用transform来传递，又会怎么样，把它改成transform。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_142.png)

然后这块呢我们还是做一个输出啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_144.png)

这个先不要。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_146.png)

看他传的啥呀，这是一个近战。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_148.png)

这是一个远程对吧，也是两个组对吧，也是两个组啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_150.png)

然后那两个组他的这个返回值是多少个，看看啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_152.png)

多了是68个呀，他返回值是68个，它是根据什么返回的，根据你的索引来返回的对吧，有一个索引我就返回一个值。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_154.png)

而跟那个apple i有区别是什么，你看API怎么返回的。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_156.png)

OPPLY就返回一个啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_158.png)

他都没有返回是吧，这块没有返回是，也就是说他拿到的参数相同，但是呢我们这个返回值是不一样的啊，它返回是两个值，最终哎啊我这边做赋值了，我怎么看不到呢，把这些删了啊，这是返回值对吧。

LOFILOFI的返回值是这样的，我把它拿过来啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_160.png)

是这样的，然后另外一个是这个transform，它我们调用一次。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_162.png)

这是它的返回值对吧，0123456，一直到到60。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_164.png)

下边还有到68，到这是吧，这边中间的部分给删了啊，所以你看它有什么区别啊，它俩的区别就在于返回值的个数不一样，是不是，a fly返回的是是以分组作为索引来返回的，而transform是什么。

是以原始值的索引来返回的，对吧是吧，所以说其实其实这个逻逻辑是完全一样的，就是返回的方式不一样，那它如果是这么返回的话，那么它的结果啊，它的结果的话，就我们在这个做这个最终的一个汇总的时候呢。

你就不能用像这种方式，像这种这个合并来处理了，直接什么几点就行了对吧，因为形状是完全一样的呀，嗯你看啊。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_166.png)

我们现在呢用它来来这个处理一下，我把这个函数恢复一下啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_168.png)

把这个恢复一下，把它删掉，X接收的值都一样对吧。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_170.png)

都是两个组，两个分组对象，那我还是都返回max啊，那如果我们用transform返回的话，那就是我碰到零，如果啊碰到零，我就算这个零所属的分组它的最大值是多少，我给你返回。

我碰到一那么一所属的分组的最大值多少，我就一返回，明白吧，就碰到哪一个，我就判断我就把你把你所属的分组给你算出来，然后把这个值给你返回。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_172.png)

所以说我们如果是用transform来计算的话，我们得到了什么，每一个值都会对应一个对应一个值对吧，那012345这时都是那个近战啊，返回的都是一个值，都是9328，那六这个显然是那个远程对吧。

返回是6900，这七是近战，那这是十九二十二十一，这都是远程对吧，所以他就是返回的套路变了。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_174.png)

实际上呢结果的本质是没什么区别的，那这个结果我们保存为一个result。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_176.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_177.png)

那只不过这个result你在跟data做这个聚合，做这个汇总的话，那这会儿我们就不能用合并了是吧，因为什么，因为它的是索引是0123456，而这个result结果也是0123456。

所以他俩之间直接怎么样，直接做个几点就行了对吧，pd点contact at，左边是date，右边是result，然后我们做一个横向节点，还得少个括号。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_179.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_180.png)

是吧啊，然后那那你这个地方，我们是不是得给给他做一个替换啊，想把它替换掉的话，那我们只能去改谁改这个这个hp max的值是吧。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_182.png)

我可以把这个点name给它设置为hp max最大值。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_184.png)

然后再连接一下是吧，这样就出来了。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_186.png)

所以这里边我们就用用那个apply就行了啊，然后transform的话，就是你注意它返回的格式会有变化啊，那这个格式不会影响值的算计算。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_188.png)

只会影响咱们那个就是最终的这个一个。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_190.png)

汇总操作的方式，那这块呢我们就总结一下啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_192.png)

就是这个呃transform，返回的值啊，要使用这个吉连汇总，啊而这个apply返回的值要使用合并来汇总，这是它们的区别，所以我们其实用就光用这个额外line就行了啊。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_194.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_195.png)

好然后另外还有一个交叉表和透视表。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_197.png)

这个交叉表跟透视表呢，其实说白了，它就是我们group by分组的一种特殊的一个场景啊，它们实现的功能我们用group by其实也可以实现啊。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_199.png)

那我举个例子啊，比如说这个交叉表，它是用来计算分组频率的特殊透视表。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_201.png)

比如它其实本它是什么，它就是个透视表对吧。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_203.png)

但它是用来计算分组频率的，比如说我们现在想看什么呢，嗯这个data啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_205.png)

现在比如说我想看这个近战和这个职业，它们之间的一种对应关系，我看他们之间的这个嗯，比如说hp max吧啊那怎么办呢。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_207.png)

可以这么玩啊，pd点cross table，然后这里面有index，有columns，就是index就是你把哪一列作为行索引，然后columns就是把拿哪一列作为列索引啊。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_209.png)

那这里边我们把这个date的我track range吧，比如说以它作为啊，以它吧，以roman作为行索引啊。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_211.png)

那我们就把这个index设置为date roman，然后columns呢我们就以这个date的。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_213.png)

我track range作为列索引。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_215.png)

然后这里边这个values我们我们写上一个count吧，啊，做一个计数，然后这个。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_217.png)

啊不是这个啊，比如我们value是什么，是我们要查看的值啊，比如说这样我们查看的是hp的max，那我们把这个hp max写下来，hp max啊，然后呢他还要有一个什么呢，AGG的funk。

就是那个分组对象的聚合函数啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_219.png)

那我们给他指定一个比如说平均值吧，面嗯是吧，这样我们就可以求出来近战和远程，远程下，各个职业的这个他们的一个平均值了是吧，那像这种没有的话意味着什么，我没有远程刺客是吧。

也没有远程坦克这块呢也没有近战射手是吧啊，近战射手实在太二了，哈哈感觉刘备就挺近战了是吧，刘备刘备应该是最近的射手了是吧，贴脸输出是吧，张脸嘎放枪，啪啪啪打死还挺二的啊啊。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_221.png)

但是你说就这个需求的话，其实我们用GROUBT能不能实现呢。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_223.png)

一样的啊，用葛肉by来实现的话，那就是相当于是多层级的分组，你可以根据近战，再根据职业来分，比如说我们说这个data点group by，先来一个，我们先根据职业是吧啊，先根据这个攻击范围啊。

然后呢再加一个实验，加个职业加上是多分组，然后求谁求hp max的。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_225.png)

平均值是吧，再说得到一个多层索引啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_227.png)

那多层索引的话，我们再做一个i stake数不就行了，把这个level设置为二是不一样的。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_229.png)

下载结果完全一样，对不对，好。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_231.png)

所以它只是我们呃就是分组的一个特殊用法啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_233.png)

那这是这是这个交叉表，还有个透视表，透视表也是一样的啊，它的道理差不多。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_235.png)

它是我们直接对data直接去pivot table，这里边也是一样的，你要计算的values是谁，那我这个values我指定为啊，这个它里边的hp max，我要对这个算啊，那同样的你的index是谁。

把谁作为行索引，那我就把这个data里边的啊，这不用date了，直接给标签就行了，因为这是我们对data直接操作是吧。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_237.png)

而这个是什么，这是我们通过pd来操作，所以我们必须要告诉他这是哪一列数据。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_239.png)

哪一列数据，而这个我们是直接对这个数据本身操作，所以我们直接告诉他，我们要取的是哪一列就行了啊，这会不用再写这个了，这是一个小细节。



![](img/e9a62dfaf2dc9bd6b64456fe750e134d_241.png)

我们把行把谁作为行呢。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_243.png)

把这个roman作为行。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_245.png)

然后columns把这个呃check rage组为列。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_247.png)

然后它里边也是有一个a g g funk。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_249.png)

那这个默认值是什么，也是一个求均值对吧，in啊一样的哈。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_251.png)

道理是一样的，嗯嗯快车嗯。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_253.png)

然后它这里边有一个有一个参数啊，就是这个啊。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_255.png)

这个可以提一下叫number alize嗯，这是干嘛的呢，它就是做规划处理的。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_257.png)

就是因为我们的数据线量级数都不一样啊，是吧，也都都很大啊，那那normalize是把什么把它规范到那个，就是标准正态分布的那种方式啊，你把它设置为true，你看数据是全变成什么了，全面小数了，对不对啊。

这个以后我们做建模的时候可能会用啊，现在还用不到。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_259.png)

好嗯对交叉表透视表啊，它就是一种特殊的分组表。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_261.png)

所以你能你能你能把这个分组表搞清楚的话，其实叫他透视。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_263.png)

你不用也行啊，好。

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_265.png)

![](img/e9a62dfaf2dc9bd6b64456fe750e134d_266.png)