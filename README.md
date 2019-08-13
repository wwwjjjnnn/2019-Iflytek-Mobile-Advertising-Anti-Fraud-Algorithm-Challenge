# Iflytek-Mobile-Advertising-Anti-Fraud-Algorithm-Challenge
2019 iFlytek 移动广告反欺诈算法挑战赛 

队伍编号：人工执杖


赛事概要

一、赛题背景
讯飞AI营销云基于深耕多年的人工智能和大数据技术，赋予营销智慧创新的大脑，以健全的产品矩阵和全方位的服务，帮助广告主用AI+大数据实现营销效能的全面提升，打造数字营销新生态。

广告欺诈是数字营销面临的一个重大挑战，随着基础技术的成熟化（篡改设备信息、IPv4服务化、黑卡、接码平台等），广告欺诈呈现出规模化、集团化的趋势，其作弊手段主要包括机器人、模拟器、群控、肉鸡/后门、众包等。广告欺诈不断蚕食着营销生态，反欺诈成为数字营销领域亟待突破的关键问题。



二、赛事任务
移动广告反欺诈需要强大的数据作为支撑，本次大赛提供了讯飞AI营销云海量的现网流量数据作为训练样本，参赛选手需基于提供的样本构建模型，预测流量作弊与否。



三、评审规则
1. 数据说明

本次比赛为参赛选手提供了5类数据：基本数据、媒体信息、时间、IP信息和设备信息。基本数据提供了广告请求会话sid，以及“是否作弊”的标识。媒体信息、时间、IP信息和设备信息等4类数据，提供了对作弊预估可能有帮助的辅助信息。

出于数据安全保证的考虑，所有数据均为脱敏处理后的数据。数据集提供了若干天的样本，最后一天数据用于预测，不提供“是否作弊”标识，其余日期的数据作为训练数据。

此次比赛分为初赛和复赛两个阶段，两个阶段的区别是所提供样本的量级有所不同，其他的设置均相同。

数据类别	变量	                         数值格式	           解释



基本数据	sid	                             string	                 样本id/请求会话sid

基本数据	label	                         int	                       是否作弊



媒体信息	pkgname	                string	                包名(MD5加密)

媒体信息	ver	                             string	                 app版本

媒体信息	adunitshowid	      string	                对外广告位ID（MD5加密）

媒体信息	mediashowid	       string	                  对外媒体ID（MD5加密）

媒体信息	apptype	                  int	                         app所属分类




时间	         nginxtime	              bigint	                请求到达服务时间，单位ms



IP信息	     ip	                               string	                  客户端IP地址

IP信息	     city	                            string	                 城市

IP信息	     province                  string	                  省份

IP信息	     reqrealip	               string	                    请求的http协议头携带IP，有可能是下游服务器的ip



设备信息	adidmd5	                string	                    Adroid ID的MD5值

设备信息	imeimd5	                 string	                    imei的MD5值

设备信息	idfamd5	                  string	                   idfa的MD5值

设备信息	openudidmd5	      string	                   openudid的MD5值

设备信息	macmd5	                string	                   mac的MD5值

设备信息	dvctype	                   int	                         设备类型 0 – 未知,1 – PC,2 – 手机, 3– 平板,4– 电视盒,5– 智能电视,6 – 可穿戴设备,7 – 智能家电,8 - 音箱,9 - 智能硬件

设备信息	model	                       string	                    机型

设备信息	make	                       string	                     厂商

设备信息	ntt                              	int	                           网络类型 0-未知, 1-有线网, 2-WIFI, 3-蜂窝网络未知, 4-2G, 5-3G, 6–4G

设备信息	carrier                     	string	                    运营商 0-未知, 46000-移动, 46001-联通, 46003-电信

设备信息	os	                              string	                    操作系统 : Android, iOS

设备信息	osv                             	string	                   操作系统版本

设备信息	orientation	            int	                            横竖屏:0竖屏，1横屏

设备信息	lan	                             string	                     语言

设备信息	h	                                 int	                          设备高

设备信息	w	                                int	                           设备宽

设备信息	ppi                            	 int	                          屏幕密度




2. 评估指标

本模型依据提交的结果文件，采用宏平均F1-score进行评价。

1) 统计TP（正确预测作弊记录），FP（错将正常记录预测为作弊记录），FN（作弊记录预测为非作弊记录）；
2) 通过第一步的统计值计算模型的precision和recall，计算公式如下：
3) 通过第二步计算结果计算F1-score,得到最后评测结果，计算方式如下：

3. 评测及排行

1) 初赛和复赛均提供下载数据，选手在本地进行算法调试，在比赛页面提交结果；
2) 每支团队每天最多提交3次；
3) 排行按照得分从高到低排序，排行榜将选择团队的历史最优成绩进行排名；


四、作品提交要求
文件格式：按照csv格式提交；
文件大小：无要求；
提交次数限制：每支队伍每天最多3次；
文件详细说明：编码为UTF-8，第一行为表头；
不需要上传其他文件；
可点击左侧导航“赛题数据”，下载相应的提交示例文件


五、奖项设置&赛程规则
1. 初赛

1) 初赛截止成绩以团队在初赛时间段内最优成绩为准（不含测试排名）；
2) 初赛作品提交截止日期为８月20日17:00；初赛名次公布日期为8月21日10:00；

2. 复赛

1) 排名前20%的团队晋级复赛，大赛官网将公示团队信息。选手通过大赛官网下载新增的训练集和开发集，本地调试算法，在线提交结果；
2) 复赛成绩以参赛团队在复赛时间段内最优成绩为准；
3) 复赛作品提交截止日期为９月20日17:00；复赛名次公布日期为９月21日10:00；

3.	决赛

1) 前三名团队将受邀参加科大讯飞全球1024开发者节并于现场进行决赛；
2) 决赛以答辩（10min陈述+5min问答）的形式进行；
根据复赛成绩和答辩成绩综合评分（复赛成绩占比70%，现场答辩分数占比30%）。
3) 各赛道TOP10选手将阶梯获得赛道奖金，第一名3万元、第二名2万元、第三名1万元、第四-第十名分别获得“算法菁英奖”2500元；

其他奖项

除对应奖金外，入围复赛的团队将获得定制Geek礼包、大赛入围证书、定制文化衫及科大讯飞全球1024开发者节通票等福利。


问题：



[设备信息]

一、 [操作系统][os] 仅为：['Android' 'android']？
    
    1、通过转换为小写，然后判断这列数据是否相同如果相同则删除掉, 否则返回.


二、 [横竖屏][orientation] 应该只能有0/1, 训练集中有 2, 测试集/训练集中有 90,
    
    1、将90/2均转化为0, 提升幅度0.06左右.


三、 [语言][lan]
    
    1、全部转化为小写字母
    2、粗粒度
        空值, 0
        如果包含cn, 即为大陆 简体 1
        如果包含tw, 即为台湾 繁体 2
        如果包含hk, 即为香港 繁体 2
        如果包含en, 则为外国 英语 3
        如果包含zh, 则为大陆 简体 1
        其他  4