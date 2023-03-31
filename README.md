**InStock股票系统**

InStock股票系统，抓取股票每日关键数据，计算股票各种指标，识别K线各种形态，内置多种选股策略，支持选股验证回测，支持批量时间，运行高效，是量化投资的好帮手。

# 功能介绍

##  一：股票每日数据
抓取A股票每日数据，主要为一些关键数据，同时封装抓取方法，方便扩展系统获取个人关注的数据。基于免费开源的akshare抓取，更多数据获取参见 [akshare官网文档](https://www.akshare.xyz/data/stock/stock.html)。

![](img/00.jpg)

## 二：股票统计/计算指标
统计：
```
1、交易量delta指标分析
2、计算n天价差
3、n天涨跌百分百计算
4、计算区间最大值
```

指标：

```
1、MACD指标
2、KDJ指标
3、BOLL指标
4、TRIX，TRMA指标
5、CR指标
6、SMA指标
7、RSI指标
8、VR，MAVR指标
9、ROC指标
10、DMI，+DI，-DI，DX，ADX，ADXR指标
11、W&R指标
12、CCI指标
13、TR、ATR指标
14、DMA、AMA指标
15、OBV指标
16、SAR指标
17、PSY指标
18、BRAR指标
19、EMV指标
20、BIAS指标
```

![](img/01.jpg)

![](img/02.jpg)

## 三：判断买入卖出的股票

根据指标判定可能买入卖出的股票，具体筛选条件如下：


```
KDJ:
1、超买区：K值在80以上，D值在70以上，J值大于90时为超买。一般情况下，股价有可能下跌。投资者应谨慎行事，局外人不应再追涨，局内人应适时卖出。
2、超卖区：K值在20以下，D值在30以下为超卖区。一般情况下，股价有可能上涨，反弹的可能性增大。局内人不应轻易抛出股票，局外人可寻机入场。
RSI:
1、当六日指标上升到达80时，表示股市已有超买现象，如果一旦继续上升，超过90以上时，则表示已到严重超买的警戒区，股价已形成头部，极可能在短期内反转回转。
2、当六日强弱指标下降至20时，表示股市有超卖现象，如果一旦继续下降至10以下时则表示已到严重超卖区域，股价极可能有止跌回升的机会。
CCI:
1、当CCI＞﹢100时，表明股价已经进入非常态区间——超买区间，股价的异动现象应多加关注。
2、当CCI＜﹣100时，表明股价已经进入另一个非常态区间——超卖区间，投资者可以逢低吸纳股票。
CR:
1、跌穿a、b、c、d四条线，再由低点向上爬升160时，为短线获利的一个良机，应适当卖出股票。
2、CR跌至40以下时，是建仓良机。
WR:
1、当％R线达到20时，市场处于超买状况，走势可能即将见顶。
2、当％R线达到80时，市场处于超卖状况，股价走势随时可能见底。
VR:
1、获利区域160－450根据情况获利了结。
2、低价区域40－70可以买进。
```

![](img/05.jpg)

## 四：K线形态识别

**精准识别61种K线形态，支持用户自选形态识别。**

**K线形态识别返回的结果有三种：**
**负：出现卖出信号**
**0：没有出现该形态**
**正：出现买入信号**

### 1、两只乌鸦

> 简介：三日K线模式，第一天长阳，第二天高开收阴，第三天再次高开继续收阴， 收盘比前一日收盘价低，预示股价下跌。


### 2、三只乌鸦

> 简介：三日K线模式，连续三根阴线，每日收盘价都下跌且接近最低价， 每日开盘价都在上根K线实体内，预示股价下跌。


### 3、三内部上涨和下跌

> 简介：三日K线模式，母子信号+长K线，以三内部上涨为例，K线为阴阳阳， 第三天收盘价高于第一天开盘价，第二天K线在第一天K线内部，预示着股价上涨。

### 4、三线打击

> 简介：四日K线模式，前三根阳线，每日收盘价都比前一日高， 开盘价在前一日实体内，第四日市场高开，收盘价低于第一日开盘价，预示股价下跌。


###  5、三外部上涨和下跌

> 简介：三日K线模式，与三内部上涨和下跌类似，K线为阴阳阳，但第一日与第二日的K线形态相反， 以三外部上涨为例，第一日K线在第二日K线内部，预示着股价上涨。


### 6、南方三星


> 简介：三日K线模式，与大敌当前相反，三日K线皆阴，第一日有长下影线， 第二日与第一日类似，K线整体小于第一日，第三日无下影线实体信号， 成交价格都在第一日振幅之内，预示下跌趋势反转，股价上升。


### 7、三个白兵

> 简介：三日K线模式，三日K线皆阳， 每日收盘价变高且接近最高价，开盘价在前一日实体上半部，预示股价上升。


### 8、弃婴

> 简介：三日K线模式，第二日价格跳空且收十字星（开盘价与收盘价接近， 最高价最低价相差不大），预示趋势反转，发生在顶部下跌，底部上涨。

### 9、大敌当前

> 简介：三日K线模式，三日都收阳，每日收盘价都比前一日高， 开盘价都在前一日实体以内，实体变短，上影线变长。


### 10、捉腰带线

> 简介：两日K线模式，下跌趋势中，第一日阴线， 第二日开盘价为最低价，阳线，收盘价接近最高价，预示价格上涨。


### 11、脱离

> 简介：五日K线模式，以看涨脱离为例，下跌趋势中，第一日长阴线，第二日跳空阴线，延续趋势开始震荡， 第五日长阳线，收盘价在第一天收盘价与第二天开盘价之间，预示价格上涨。


### 12、收盘缺影线

> 简介：一日K线模式，以阳线为例，最低价低于开盘价，收盘价等于最高价， 预示着趋势持续。


### 13、藏婴吞没

> 简介：四日K线模式，下跌趋势中，前两日阴线无影线 ，第二日开盘、收盘价皆低于第二日，第三日倒锤头， 第四日开盘价高于前一日最高价，收盘价低于前一日最低价，预示着底部反转。


### 14、反击线

> 简介：二日K线模式，与分离线类似。


### 15、乌云压顶


> 简介：二日K线模式，第一日长阳，第二日开盘价高于前一日最高价， 收盘价处于前一日实体中部以下，预示着股价下跌。



### 16、十字


> 简介：一日K线模式，开盘价与收盘价基本相同。


### 17、十字星


> 简介：一日K线模式，开盘价与收盘价基本相同，上下影线不会很长，预示着当前趋势反转。



### 18、蜻蜓十字/T形十字


> 简介：一日K线模式，开盘后价格一路走低， 之后收复，收盘价与开盘价相同，预示趋势反转。



### 19、吞噬模式


> 简介：两日K线模式，分多头吞噬和空头吞噬，以多头吞噬为例，第一日为阴线， 第二日阳线，第一日的开盘价和收盘价在第二日开盘价收盘价之内，但不能完全相同。



### 20、十字暮星

> 简介：三日K线模式，基本模式为暮星，第二日收盘价和开盘价相同，预示顶部反转。


### 21、暮星

> 简介：三日K线模式，与晨星相反，上升趋势中, 第一日阳线，第二日价格振幅较小，第三日阴线，预示顶部反转。


### 22、向上/下跳空并列阳线

> 简介：二日K线模式，上升趋势向上跳空，下跌趋势向下跳空, 第一日与第二日有相同开盘价，实体长度差不多，则趋势持续。


### 23、墓碑十字/倒T十字


> 简介：一日K线模式，开盘价与收盘价相同，上影线长，无下影线，预示底部反转。



### 24、锤头


> 简介：一日K线模式，实体较短，无上影线， 下影线大于实体长度两倍，处于下跌趋势底部，预示反转。



### 25、上吊线


> 简介：一日K线模式，形状与锤子类似，处于上升趋势的顶部，预示着趋势反转。



### 26、母子线


> 简介：二日K线模式，分多头母子与空头母子，两者相反，以多头母子为例，在下跌趋势中，第一日K线长阴， 第二日开盘价收盘价在第一日价格振幅之内，为阳线，预示趋势反转，股价上升。


### 27、十字孕线


> 简介：二日K线模式，与母子县类似，若第二日K线是十字线， 便称为十字孕线，预示着趋势反转。


### 28、风高浪大线


> 简介：三日K线模式，具有极长的上/下影线与短的实体，预示着趋势反转。



### 29、陷阱

> 简介：三日K线模式，与母子类似，第二日价格在前一日实体范围内, 第三日收盘价高于前两日，反转失败，趋势继续。


### 30、修正陷阱


> 简介：三日K线模式，与陷阱类似，上升趋势中，第三日跳空高开； 下跌趋势中，第三日跳空低开，反转失败，趋势继续。


### 31、家鸽


> 简介：二日K线模式，与母子线类似，不同的的是二日K线颜色相同， 第二日最高价、最低价都在第一日实体之内，预示着趋势反转。


### 32、三胞胎乌鸦


> 简介：三日K线模式，上涨趋势中，三日都为阴线，长度大致相等， 每日开盘价等于前一日收盘价，收盘价接近当日最低价，预示价格下跌。


### 33、颈内线

> 简介：二日K线模式，下跌趋势中，第一日长阴线， 第二日开盘价较低，收盘价略高于第一日收盘价，阳线，实体较短，预示着下跌继续。


### 34、倒锤头


> 简介：一日K线模式，上影线较长，长度为实体2倍以上， 无下影线，在下跌趋势底部，预示着趋势反转。


### 35、反冲形态


> 简介：二日K线模式，与分离线类似，两日K线为秃线，颜色相反，存在跳空缺口。



### 36、由较长缺影线决定的反冲形态

> 简介：二日K线模式，与反冲形态类似，较长缺影线决定价格的涨跌。



### 37、梯底

> 简介：五日K线模式，下跌趋势中，前三日阴线， 开盘价与收盘价皆低于前一日开盘、收盘价，第四日倒锤头，第五日开盘价高于前一日开盘价， 阳线，收盘价高于前几日价格振幅，预示着底部反转。


### 38、长脚十字


> 简介：一日K线模式，开盘价与收盘价相同居当日价格中部，上下影线长， 表达市场不确定性。


### 39、长蜡烛


> 简介：一日K线模式，K线实体长，无上下影线。



### 40、光头光脚/缺影线


简介：一日K线模式，上下两头都没有影线的实体， 阴线预示着熊市持续或者牛市反转，阳线相反。


### 41、相同低价


> 简介：二日K线模式，下跌趋势中，第一日长阴线， 第二日阴线，收盘价与前一日相同，预示底部确认，该价格为支撑位。



### 42、铺垫


> 简介：五日K线模式，上涨趋势中，第一日阳线，第二日跳空高开影线， 第三、四日短实体影线，第五日阳线，收盘价高于前四日，预示趋势持续。



### 43、十字晨星


> 简介：三日K线模式， 基本模式为晨星，第二日K线为十字星，预示底部反转。


### 44、晨星


> 简介：三日K线模式，下跌趋势，第一日阴线， 第二日价格振幅较小，第三天阳线，预示底部反转。


### 45、颈上线

> 简介：二日K线模式，下跌趋势中，第一日长阴线，第二日开盘价较低， 收盘价与前一日最低价相同，阳线，实体较短，预示着延续下跌趋势。



### 46、刺透形态


> 简介：两日K线模式，下跌趋势中，第一日阴线，第二日收盘价低于前一日最低价， 收盘价处在第一日实体上部，预示着底部反转。



### 47、黄包车夫


> 简介：一日K线模式，与长腿十字线类似， 若实体正好处于价格振幅中点，称为黄包车夫。



### 48、上升/下降三法


> 简介： 五日K线模式，以上升三法为例，上涨趋势中， 第一日长阳线，中间三日价格在第一日范围内小幅震荡， 第五日长阳线，收盘价高于第一日收盘价，预示股价上升。



### 49、分离线


> 简介：二日K线模式，上涨趋势中，第一日阴线，第二日阳线， 第二日开盘价与第一日相同且为最低价，预示着趋势继续。



### 50、射击之星


> 简介：一日K线模式，上影线至少为实体长度两倍， 没有下影线，预示着股价下跌



### 51、短蜡烛


> 简介：一日K线模式，实体短，无上下影线


### 52、纺锤


> 简介：一日K线，实体小。



### 53、停顿形态


> 简介：三日K线模式，上涨趋势中，第二日长阳线， 第三日开盘于前一日收盘价附近，短阳线，预示着上涨结束



### 54、条形三明治


> 简介：三日K线模式，第一日长阴线，第二日阳线，开盘价高于前一日收盘价， 第三日开盘价高于前两日最高价，收盘价于第一日收盘价相同。


### 55、探水竿


> 简介：一日K线模式，大致与蜻蜓十字相同，下影线长度长。



### 56、跳空并列阴阳线


> 简介：三日K线模式，分上涨和下跌，以上升为例， 前两日阳线，第二日跳空，第三日阴线，收盘价于缺口中，上升趋势持续。



### 57、插入


> 简介：二日K线模式，与颈上线类似，下跌趋势中，第一日长阴线，第二日开盘价跳空， 收盘价略低于前一日实体中部，与颈上线相比实体较长，预示着趋势持续。


### 58、三星

> 简介：三日K线模式，由三个十字组成， 第二日十字必须高于或者低于第一日和第三日，预示着反转。


### 59、奇特三河床

> 简介：三日K线模式，下跌趋势中，第一日长阴线，第二日为锤头，最低价创新低，第三日开盘价低于第二日收盘价，收阳线， 收盘价不高于第二日收盘价，预示着反转，第二日下影线越长可能性越大。


### 60、向上跳空的两只乌鸦

> 简介：三日K线模式，第一日阳线，第二日跳空以高于第一日最高价开盘， 收阴线，第三日开盘价高于第二日，收阴线，与第一日比仍有缺口。



### 61、上升/下降跳空三法


> 简介：五日K线模式，以上升跳空三法为例，上涨趋势中，第一日长阳线，第二日短阳线，第三日跳空阳线，第四日阴线，开盘价与收盘价于前两日实体内， 第五日长阳线，收盘价高于第一日收盘价，预示股价上升。


![](img/09.jpg)

![](img/10.jpg)

## 五：策略选股

内置放量上涨、停机坪、回踩年线、突破平台、放量跌停等多种选股策略，同时封装了策略模板，方便扩展实现自己的策略。


```
1、放量上涨
2、均线多头
3、停机坪
4、回踩年线
5、突破平台
6、无大幅回撤
7、海龟交易法则
8、高而窄的旗形
9、放量跌停
10、低ATR成长
```

![](img/04.jpg)

## 六：选股验证



对指标、策略等选出的股票进行回测，验证策略的成功率，是否可用。


![](img/05.jpg)

![](img/06.jpg)

## 七：支持批量


可以通过时间段、枚举时间、当前时间进行指标计算、策略选股及回测等。同时支持智能识别交易日，可以输入任意日期。

具体执行设置如下：
```
------整体作业，支持批量作业------
当前时间作业 python execute_daily_job.py
单个时间作业 python execute_daily_job.py 2022-03-01
枚举时间作业 python execute_daily_job.py 2022-01-01,2021-02-08,2022-03-12
区间时间作业 python execute_daily_job.py 2022-01-01 2022-03-01

------单功能作业，支持批量作业，回测数据自动填补到当前
基础数据作业 python basic_data_daily_job.py
指标数据作业 python indicators_data_daily_job.py
K线形态作业 klinepattern_data_daily_job.py
策略数据作业 python strategy_data_daily_job.py
回测数据 python backtest_data_daily_job.py
```

## 八：存储采用数据库设计

数据存储采用数据库设计，能保存历史数据，以及对数据进行扩展分析、统计、挖掘。系统实现自动创建数据库、数据表，封装了批量更新、插入数据，方便业务扩展。

![](img/07.jpg)

## 九：展示采用web设计

采用web设计，可视化展示结果。对展示进行封装，添加新的业务表单，只需要配置视图字典就可自动出现业务可视化界面，方便业务功能扩展。

## 十：运行高效


采用多线程、单例共享资源有效提高运算效率。1天数据的抓取、计算、策略选股、回测运行时间大概3分钟，计算天数越多效率越高。


## 十一：方便调试

系统运行的重要日志记录在stock_execute_job.log(数据抓取、处理、分析)、stock_web.log(web服务)，方便调试发现问题。

![](img/08.jpg)


# 安装说明

建议windows下安装，方便操作及使用系统，同时安装也非常简单。以下安装及运行以windows为例进行介绍。

1.安装最新的 python

```
（1）在官网 https://www.python.org/downloads/ 下载安装包，一键安装即可，安装切记勾选自动设置环境变量。
（2）配置永久全局国内镜像库（因为有墙，无法正常安装库文件），执行如下dos命令：
python pip config --global set  global.index-url https://mirrors.aliyun.com/pypi/simple/
# 如果你只想为当前用户设置，你也可以去掉下面的"--global"选项
```
2.安装最新的 mysql

```
在官网 https://dev.mysql.com/downloads/mysql/ 下载安装包，一键安装即可。
```
3.安装库文件，库都是目前最新版本

```
dos切换到本系统的根目录，执行下面命令：
python pip install -r requirements.txt

也可以通过下面命令生成自己的requirements.txt
python pip freeze > requirements.txt
```

4.安装 talib，安装见以下：

```
第一种方法. pip 下安装
（1）https://www.ta-lib.org/下载并解压ta-lib-0.4.0-msvc.zip
（2）解压并将ta_lib放在C盘根目录
（3）https://visualstudio.microsoft.com/zh-hans/downloads/下载并安装Visual Studio Community，安装切记勾选Visual C++功能
（4）Build TA-Lib Library # 构建 TA-Lib 库
    ①在开始菜单中搜索并打开[Native Tools Command Prompt](根据操作系统选择32位或64位)
    ②输入 cd C:\ta-lib\c\make\cdr\win32\msvc
    ③构建库，输入 nmake
（5）安装完成。
第二种方法. Anaconda 下安装
（1）打开Anaconda Prompt终端。
（2）在终端输入命令行conda install -c conda-forge ta-lib 。
（3）此处确认是否继续安装？输入y 继续安装，直到完成
（4）安装完成。
```
5.安装 Navicat（可选）

Navicat可以方便管理数据库，以及可以手工对数据进行查看、处理、分析、挖掘。

Navicat是一套可创建多个连接的数据库管理工具，用以方便管理 MySQL、Oracle、PostgreSQL、SQLite、SQL Server、MariaDB 和 MongoDB 等不同类型的数据库

```
（1）在官网 https://www.navicat.com.cn/download/navicat-premium 下载安装包，一键安装即可。

（2）然后下载破解补丁: https://pan.baidu.com/s/18XpTHrm9OiLEl3u6z_uxnw 提取码: 8888 ，破解即可。
```
6.配置数据库

一般可能会修改的信息是”数据库访问密码“。

修改database.py相关信息:

```
db_host = "localhost"  # 数据库服务主机
db_user = "root"  # 数据库访问用户
db_password = "root"  # 数据库访问密码
db_port = 3306  # 数据库服务端口
db_charset = "utf8mb4"  # 数据库字符集
```

# 运行说明

1.执行数据抓取、处理、分析

支持批量作业，具体参见_run_job.bat中的注释说明。

建议将其加入到任务计划中，工作日的每天17：00执行。

```

运行 _run_job.bat
```
2.启动web服务

```
运行 _run_web.bat
```

# 特别声明
本系统参考了pythonstock、sngyai。

股市有风险投资需谨慎，本系统只能用于学习、股票分析，投资盈亏概不负责。
