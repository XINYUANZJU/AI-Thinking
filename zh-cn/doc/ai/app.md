<!--
  Copyright (c) 2019, Xin YUAN, courses of Zhejiang University
  All rights reserved.

  This program is free software; you can redistribute it and/or
  modify it under the terms of the 2-Clause BSD License.

  Author contact information:
    yxxinyuan@zju.edu.cn
-->

# 应用分析

## 场景分析

人工智能在现实中的确也获得了不少领域的应用，但目前来看，其应用范围还是比较窄的。
这是由于它理论上的局限性决定的。

围棋所在的游戏领域，是具有明确规则的，因而其局面评估函数也是确定的，
通过深度学习拟合函数的方法来做到自动对弈是合理的。

这类方法想要推广到其他领域和行业，需要先分析其他行业对应要拟合函数的自变量取值规模有多大，
自变量之间相关性如何。比围棋规模小的能成功，规模大的不可能成功。
此外对拟合函数精度要求不高的场合，如电子商务推荐系统，也可以开发成产品。

而一般图像的分类问题，医学图像的病灶识别问题，是没有明确的规则的。
事实上，到现在为止，人工提取或者卷积神经网络提取的图像特征并不能准确反映这样的语义信息。
就算用计算机按一定的规则产生大量训练图片，此时模型将依赖规则所暗含的假设，
对于要测试的新图像，若不符合该假设，算法将无法估计或者判断这是什么类别，是不是有病灶等。
这时，AlphaGo的方法就无效了。
所以训练集需要的高质量样本还是要依靠人类来标注，这样就回到机器学习的老路上去了。
同时，医疗图像的标注和医生的经验有关，也和其他不可见因素有关，其准确性很难保证。
最终结果是训练出的模型很容易过拟合，泛化能力差。

另外可以看到，医疗界面临的问题规模远比围棋要大，所以深度学习方法基本不可能成功。

## 医疗AI

AI+X成为2016年之后的热潮，AI+医疗也不例外，数百亿资本投入了这个领域。
那么AI+医疗会成功吗？答案是否定的。

1. 从频率学派的观点看，医疗处理的对象具有个体差异，不服从机器学习需要的独立同分布假设。

1. 从贝叶斯学派的观点看，作为证据的样本是已有的数据，机器学习只是根据它们来拟合函数，
这些样本并不能覆盖问题涉及的所有情况，包括所有种族、不同年龄阶段、同一个人的不同时刻等等情况，
即便有一类数据能覆盖大部分情况，判断疾病仍需要很多其他因素的考虑，
并且已收集的数据上可能会存在大量自相矛盾的情况。
所以机器学习的方法无法应对临床中不断出现的新病例。

当前，AI+医疗是资本热炒的重点之一。我们来看看媒体的报道中有哪些炒作套路：

1. [微软：用计算机技术治愈癌症，这不是在开脑洞](http://mp.weixin.qq.com/s/F61ekPZ3OBVExBvRzRwyRw)

1. [人工智能诊断正在快速兴起](http://mp.weixin.qq.com/s/3Bnz3EN4IIcd8kEYvF52VQ)

1. [同济CT “阿尔法狗” 5秒读结果 阅片水平已接近主治医师！](http://mp.weixin.qq.com/s/tNrYY4sQGthE6mLJRfvYMw)

1. [清华大学医学院开启人工智能辅助临床教学新模式](http://news.sciencenet.cn/htmlnews/2017/7/383736.shtm)

1. [人工智能撬动智慧医疗](http://news.sciencenet.cn/htmlnews/2017/8/384582.shtm)

1. [人工智能研究的中国力量](http://blog.sciencenet.cn/blog-614989-1066358.html)

1. [结局超预想：医疗AI“成才”记](http://news.sciencenet.cn/htmlnews/2018/8/416424.shtm)

1. [想知道吗？人工智能可以预测你能活多大了](http://digi.tech.qq.com/a/20170603/003625.htm?pgv_ref=aio2015&ptlang=2052)

1. [早期肺癌陷入AI天网！谷歌联合多家医院打造肺癌筛查AI](https://new.qq.com/omn/20190521/20190521A0PS5V.html)

1. [更胜一筹！早期诊断肺癌，这款AI已超越人类医生](https://new.qq.com/omn/20190522/20190522A03XNH.html)

1. [Nature子刊 | 谷歌出手，肺癌筛查准确率超越医学专家](https://mp.weixin.qq.com/s/4gfrFQEFU66ubYn84Jft4A)

1. [“腾讯觅影”再下一城 正式发布AI电子阴道镜辅助诊断系统](https://new.qq.com/cmsn/20190522/20190522006047.html)

1. [腾讯医疗人工智能研究院院长范伟：超越认知，AI重塑运动评估](https://new.qq.com/cmsn/20190524/20190524004048.html)

1. [医疗 AI 战场狭路相逢，GPS 三巨头的新故事](https://new.qq.com/omn/20190528/20190528A0CX10.html)

1. [重磅：人工智能牛大了！AI识别结直肠癌MSI准确率达到84%](https://new.qq.com/omn/20190604/20190604A0R8ER.html)

1. [阿里AI攻克心血管识别技术，0.5秒可提取单根心脏冠脉](https://new.qq.com/omn/20190628/20190628A09SUK.html)

1. [《Nature》子刊提出AI病理诊断解释方案，或解决人工智能CFDA三类申报获批关键难点](https://mp.weixin.qq.com/s/U6s8gdksHe6RUpZOk3aNpA)

1. [IBM的医疗AI为何失败](http://blog.sciencenet.cn/blog-306242-1177032.html)

1. [AI助力医疗不成功, 不是AI的错, 是你的垃圾数据](https://mp.weixin.qq.com/s/8HE_Fnf300JwIXV3txB85A)

1. [医疗AI渐入深水区](https://new.qq.com/omn/20190618/20190618A0FSDG.html)

1. [NEJM：回顾IBM Watson，AI如何发挥优势、避开陷阱来来优化医患护理？](https://mp.weixin.qq.com/s/kwt5FrbD2R8OIc4tTvC-Cg)

要识别有关医疗AI的新闻报道是否可靠和有应用价值，只要看是否包含有以下内容：

1. 精度(灵敏度)
1. 假阳性(特异度)
1. 临床试验

而这些指标的含义可以看以下文章：

1. [听说日本“一滴血验多种癌”要上市了，这几件事你应该了解！](https://mp.weixin.qq.com/s/2YQ6v5GEVByYed47viLzHw)

1. [什么样的工作容易被机器取代？](http://blog.sciencenet.cn/blog-70036-1066085.html)

而医疗AI产品要想上市销售，同样需要进行临床验证：

1. [人工智能科技系列连载之三：人工智能产品的临床验证](https://mp.weixin.qq.com/s/ZsQHcHoFt8CrFLYoIXk3rA)

1. [影像医师怎么看 AI ？北大人民医院杜湘珂：医生不止是看片子这么简单](https://www.leiphone.com/news/201707/A8xZmLH5E6uDPJY0.html)

遗憾的是，目前市场上FDA，CFDA批准的仅是二类医疗器械证，没有企业能拿到三类医疗器械证。
