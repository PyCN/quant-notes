# 量化感知训练（3（：自定义卷积层 - P1 - 恶人老李 - BV1FE421L7wa

连续挫败出去做了几个引体向上回来了，哎呀，想一想，我觉得还是需要使用写一个自定义成，我靠新建Python自定义，自定义成就自定义成不对，叫自定义，量化感知成，但是自定义成怎么写。

我靠在自定义层里边写一个卷积层，卷积层，卷积层里边，自定义卷积层里边应该有15入函数，反向传播的时候使用，代理梯度T自动器就行了，哎呀这说起来简单，但是怎么写的，而且自定义程写完之后。

训练肯定也就变慢了，说不定，自定义成危险，把GBT交出来，还有现在可以可以上完了，这玩意有时候上不去，我嗯，用，By orch，写一个自定义成要求使用，呃，功能是，功能啊它是基于卷积层的，区别在于。

在进行，在进行卷积操作前，卷积层的权重全部乘以二的N次方，在四舍五入，然后再进行卷积，操作，哎卷积操作平翘舌不分啊，我靠嗯，由于四舍五入不是，可微的，所以反向传播的时候采用代理梯度，用Y等于X。

代理梯度即可购，要实现这样的什么。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_1.png)

成代码如下嗯，Good good。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_3.png)

OK先把他弄过来，引入库自定义卷积层初始化通道，Output kernel size，Stride，Padding zero，第，这什么玩意，Delete delection。



![](img/e3a4f7a6a7b8fa4ec83181761234db2b_5.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_6.png)

什么间隔大小，在传统中，保证默认字就行了，Group，BIOS等于true能行吗，默认是false，不需要bells，一切重点N等于零，N是什么东西，N等于零，那能行吗，至少等于四，等于四，再。

前向传播，反向传播，啊权重，我记得代理梯度好像可以用，Y，Y减X加X，前向传播的时候用Y反向传播的时候，用X反向传播的时候就用理查去呗，卧槽，呃这种方法吧，是的你说的是的，简单易懂的缺点是引入一些误差。

激活函数非线性，那肯定有误差呀，没有误差，那怎么能叫代理梯度呢，没看到代理在哪，这是啥，Backwar，哎呀，前进前进，那是什么怎么回事，啊这，还能运行还真能运行，我靠，那你是怎么怎么提出代理的呢。



![](img/e3a4f7a6a7b8fa4ec83181761234db2b_8.png)

我想知道下面的代码中梯度代理是在哪里，现在run函数是不可微的，那么weight是如何更新的，并没有显示的使用替代理，虽然run是不可悲的，但PYTHORITY中使用近似代理，简单地将梯度设置为一。

我要显示的再见，因为我可能会修改。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_10.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_11.png)

哎这玩意就得反复拷打才行，梯度代理为Y减X，真的假的，By ground，我靠我，靠。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_13.png)

去掉。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_15.png)

他们都是默认不，我看着烦。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_17.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_18.png)

Ok copy code，Ctrl a ctrl c，Ctrl a ctrl v，哎没有错误，那这算不算成功了呀，行吧，所以说他是在哪体现的代理，就不能小一点嘛，嘿，什么东西，out等于round。

Back forward，Y减X，A z，Breed in boot，Breathe out，Breathe out，四次函数，啊看不懂啊。

这个forward我看懂了这个bike forward什么意思，给一个输入。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_20.png)

这是什么工作的，我看不明白。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_22.png)

还有乘以二的N次方呢，不用考虑吗，我靠，那怎么能不考虑呢。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_24.png)

这就不理解了。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_26.png)

怎么能忽略呢，曲度明明已也乘以个二的N次方。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_28.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_29.png)

完了GDP就是智障啊，说的这个正确吗。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_31.png)

groups代理什么事都不用也不用，这个函数和com2D函数有什么区别呢，X bread output，Padding1234，他妈的，学个屁，这他妈是跟GPT学习呢，还是跟老师学习。

诶刚才那个是哪弄出来的。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_33.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_34.png)

放弃了放弃了，对吗，Shelf weight，嗯哼哼哼哼，我觉得应该也不用这个。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_36.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_37.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_38.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_39.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_40.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_41.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_42.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_43.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_44.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_45.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_46.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_47.png)

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_48.png)

哎什么玩意，他竟然没说我还能跑起来，rose下降了不是，怎么又上升了呀，靠谱，经note多少啊，91这么高，如果把这个去掉呢，这路是怎么越训练越大呀，嗯97，我靠，看来不用这个嗯。

就是直接在wait上就行，这路子也不知道是怎么算的，我靠，哎哎哎哎发挥，判定等于一卷积卷积F1F1卷，基本六磁化卷，基本60化，卷积本的磁化real，Ok ok，删，是啊，那我把它改成，删改删哎。

这怎么回事，我靠，Wows，不要乱下载，嗯讲不下去，三已经是极限了呀，五个epoch是不是太少了，我的训练十个EPOKE，11。5跟瞎蒙一样，卧槽，可能是质变的关键的，但是权重他全都变成这样了。

那也不好，嘶嗯，啊，这路子为什么变化这么大呀，哎呀，麦克风也没有声音，我靠，98以上最高就是97。

![](img/e3a4f7a6a7b8fa4ec83181761234db2b_50.png)