# Python多因子量化选择全流程 - P4：因子滚动筛选 - 代码解析与论文精读 - BV1JfDLYjEdL

哈喽各位小伙伴们大家好，嗯之前我们嗯今天这一节呢，我们继续讲多因子选股与机器学习的系列。

![](img/febc0cb302eb8246082c73f64e4ad87a_1.png)

那前面几节呢，前面三节我们讲了数据预处理，还有单调性检验，以及ICIR因子收益率。

![](img/febc0cb302eb8246082c73f64e4ad87a_3.png)

这些概念和相应的代码的操作方式，那今天我们这一节重点讲解因子筛选，也就是说到了一个非常重要的一个步骤了，呃我们有非常多的因子，哪些因子被用来作为选股的一个，重要的参考依据，好那话不多说。

我们来先来看一下代码，我们直接来看代码，首先呢我们嗯还是先导入一下这个数据。

![](img/febc0cb302eb8246082c73f64e4ad87a_5.png)

这个数据呢就是有这么多个因子，换手率啊，市净率啊，市现率啊。

![](img/febc0cb302eb8246082c73f64e4ad87a_7.png)

呃还有什么市值毛利率这些所有的因子数据呢。

![](img/febc0cb302eb8246082c73f64e4ad87a_9.png)

经过我们前面几步的操作，如果大家不知道的话，可以看前面几部的视频呃。

![](img/febc0cb302eb8246082c73f64e4ad87a_11.png)

数据处理单调性检验和因子的ICRR值计算。

![](img/febc0cb302eb8246082c73f64e4ad87a_13.png)

前面视频我们都讲解的非常清楚了，这些因子的值呢，是经过了中性化处理和数据的预处理的，所以已经不是原来的值了。



![](img/febc0cb302eb8246082c73f64e4ad87a_15.png)

好有这么多个因子，到底哪些因子用来作为我们选股的一个标准嗯。

![](img/febc0cb302eb8246082c73f64e4ad87a_17.png)

那所以要进行一个因子筛选。

![](img/febc0cb302eb8246082c73f64e4ad87a_19.png)

首先呢我们这里要采用的那个方式呢是IC值。

![](img/febc0cb302eb8246082c73f64e4ad87a_21.png)

就是IC值的因子筛选，那还有一种方式呢可以进行一个相关系数，correlation的一个筛选。

![](img/febc0cb302eb8246082c73f64e4ad87a_23.png)

如果两个因子的相关系数比较大，我们也可以对它进行一个呃因子的一个筛选，这里大家看到没有，如果呃两两种进行筛选，第一种筛选呢是直接根据IC值，我们先讲一下个笼统的概念，然后我们再细讲。

是直接根据IC值大于0。03，作为我们筛选因子的标准，第二个步骤呢是如果筛选因子就是IC值，筛选完，筛选一轮之后，相关系数值大于0。8，两个因子的相关系数值大于0。8，我们对其进行删除，就是这样。

删除后的因子既能保值，保证它的IC值比较大，好那我们来看一下这个步骤吧，这一步骤是核心，就是我们是阅读数据，我们阅读数据呢要哦使用，就比如说我们这一个月就要进行因子，要进行股票选股了。

那么我们要回望历时12个月，就是这个count，就是因为我们这边是大于等于嘛，所以加了一个11，是是呃加了一个11，因为他其实是12个月，因为因为其实是12个月，因为这里面是取等了，后面不取等。

所以他就是12个月嗯，我们取过去一年的数据嗯，split data来计算，我们可以打印一下。

![](img/febc0cb302eb8246082c73f64e4ad87a_25.png)

我们看一下这个split data，看到没有，是2020年12月到2021年8月，这个数据呃，10月到8月是有时多少个月来着。



![](img/febc0cb302eb8246082c73f64e4ad87a_27.png)

我来算一下哈，点data应该是12个月，这个好久之前做代码了，我来验证一下点UIQUE。

![](img/febc0cb302eb8246082c73f64e4ad87a_29.png)

好我来算一下哈。

![](img/febc0cb302eb8246082c73f64e4ad87a_31.png)

哦那就是11，那就是11，这里也可以设置成12，那这里也可以设置12大，大家自行去设置哈，我这里就暂且按照11来算，就是历史过去11个月的数据。



![](img/febc0cb302eb8246082c73f64e4ad87a_33.png)

类似于这样的一个数据，我们计算它的IC值嗯。

![](img/febc0cb302eb8246082c73f64e4ad87a_35.png)

怎么计算IC值呢，上一节课我已经讲过了，就是使用当前因子值和未来时刻的呃。

![](img/febc0cb302eb8246082c73f64e4ad87a_37.png)

收益率值取一个相关系数。

![](img/febc0cb302eb8246082c73f64e4ad87a_39.png)

那么这个值呢就是IIC值。

![](img/febc0cb302eb8246082c73f64e4ad87a_41.png)

所以我们要计算这一列就是因子值。

![](img/febc0cb302eb8246082c73f64e4ad87a_43.png)

这一列和最后一列的相关系数，我们取因子值，这一列和最后一列的一个相关系数，Group by，这里有一个啊，这里有一个correlation，我来看一下这个这里这里有一个correlation。



![](img/febc0cb302eb8246082c73f64e4ad87a_45.png)

我们就是取当前因子值和最后一个值的一个呃，大家看到没有，这个f name呢是一，就是取最后一个最后一列，取最后一列，然后所有的因子与最后一列值取一个相关系数，得到的因子值就是IIC值。



![](img/febc0cb302eb8246082c73f64e4ad87a_47.png)

好，我讲的非常清楚，大家可以不懂的，可以去自己仔细再看一下我的代码。

![](img/febc0cb302eb8246082c73f64e4ad87a_49.png)

然后计算完IC值之后呢，我们来计算一下它的平均值。

![](img/febc0cb302eb8246082c73f64e4ad87a_51.png)

大家懂吧，就是每一个每一个日期，每每一每一每一个月每一个月，你看二0220年10月十月十月十月，每一个月都有一组因子值和一组收益率值，求一组均值。



![](img/febc0cb302eb8246082c73f64e4ad87a_53.png)

大概就是这样的一个结果，大家看一下，就是2月有一组IC值。

![](img/febc0cb302eb8246082c73f64e4ad87a_55.png)

3月有一组，4月有一组，5月有一组对吧。

![](img/febc0cb302eb8246082c73f64e4ad87a_57.png)

这个我们都理解哈，就是每一个月做了，这里面有个group by，就是每一个月做一个相关系数。

![](img/febc0cb302eb8246082c73f64e4ad87a_59.png)

做一个correlation，那么我们对。

![](img/febc0cb302eb8246082c73f64e4ad87a_61.png)

就是对这些十二十一个月呢的IIC值呢。

![](img/febc0cb302eb8246082c73f64e4ad87a_63.png)

求一个均值，IIC的求一个均值。

![](img/febc0cb302eb8246082c73f64e4ad87a_65.png)

判断一下这个IC值的均值是不是大于啊，我们对它进行排序，排序我们取零点大于0。03的，我们看一下这个salt i c啊。



![](img/febc0cb302eb8246082c73f64e4ad87a_67.png)

SAAIC我们大于0。03的这个值，这个因子作为我们选股的一个标准，好这里面有一个0。03，这，然后我们嗯选出来的因子就是这个这四个因子，这五个音呃，123456这六个因子。



![](img/febc0cb302eb8246082c73f64e4ad87a_69.png)

然后还要再判断一下这些因子之间的相关性，是不是大于0。8，如果大于0。8的话，这说明存在贡献性，我们就要对它再进行，第二轮的一个因子的剔除好，然后我们嗯得到一个select factor。

就相当于是我们选了一组因子，然后我们可以打印一下这个select factor，那么我们由于我们的财务数据是季度数据，我们每个季度筛选一次，加三个月。



![](img/febc0cb302eb8246082c73f64e4ad87a_71.png)

每个季度进行筛选一次，好好这个select factor呢就是相当于是存储起来哎，那我们打印这个。

![](img/febc0cb302eb8246082c73f64e4ad87a_73.png)

那这个就相当于是呃，二0212年1月选择这么多因子，204月选择这么多因子。

![](img/febc0cb302eb8246082c73f64e4ad87a_75.png)

7月选择这么多因子，1月选择这么多因子，这个就是我们选择因子的一个列表。

![](img/febc0cb302eb8246082c73f64e4ad87a_77.png)

相当于是我们每个月我们只选择这几个因子。

![](img/febc0cb302eb8246082c73f64e4ad87a_79.png)

作为我们选股的一个标准。

![](img/febc0cb302eb8246082c73f64e4ad87a_81.png)

好然后呢嗯然后呢这个地方相当于是啥呢啊。

![](img/febc0cb302eb8246082c73f64e4ad87a_83.png)

这个是对这个日期对它进行了一个处理。

![](img/febc0cb302eb8246082c73f64e4ad87a_85.png)

对日期进行了一个处理，得到一个这样的一个结果。

![](img/febc0cb302eb8246082c73f64e4ad87a_87.png)

每一个月一号，每个月11号的一个因子的筛选的一个结果。

![](img/febc0cb302eb8246082c73f64e4ad87a_89.png)

好今天我们讲到这里，就是因子筛选结果，我再我给大家再重复一遍。

![](img/febc0cb302eb8246082c73f64e4ad87a_91.png)

就是首先你要对数据进行预处理，中型化标准化啊，市值中呃，行业化等操作，得到一个一组因子值和未来收益率的那值。



![](img/febc0cb302eb8246082c73f64e4ad87a_93.png)

我们取一个相关系数，取个相关系数之后。

![](img/febc0cb302eb8246082c73f64e4ad87a_95.png)

我们再取，我们再取它的因子值大于0。03。

![](img/febc0cb302eb8246082c73f64e4ad87a_97.png)

然后对它的相关系数大于0。8的进行过滤，经过两轮过滤之后。

![](img/febc0cb302eb8246082c73f64e4ad87a_99.png)

我们就得到了每一个月的，每一个季度的最终的因子的一个列表。

![](img/febc0cb302eb8246082c73f64e4ad87a_101.png)

用于我们最后一轮的回测。

![](img/febc0cb302eb8246082c73f64e4ad87a_103.png)

好今天就讲到这里。

![](img/febc0cb302eb8246082c73f64e4ad87a_105.png)