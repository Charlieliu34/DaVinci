# 叁、信号参数定义
## 一、MC 回测模板

 >**<font color=#1E90FF>@DVC5_PassEq_Chart:</font>  <font color=#32CD32>将自定义策略的绩效进行多空拆解，多空个别评价，于圖表上使用。</font>**
 
1. <font color=#FF0000>Strategy:  </font> 
    <br>
    <font color=#32CD32>该商品之策略编号，从数字1起依序向上编号。不同商品皆须从1开始编号，不可混合接续编号。</font>

<br>

>**<font color=#1E90FF>@DVC5_PassEq: </font> 将自定义策略的绩效进行多空拆解，多空个别评价，<font color=##32CD32>于PT上使用。</font>** 

<br>

>**<font color=#1E90FF>@DVC5_OriginalMM: </font> 輸出原始策略組合之績效。**

1.  <font color=#FF0000>CapitalName: </font>
    原始策略组合之权益曲线名称，命名规则为"UD.MCQuote.xxx"，其中xxx为自定义字串。

2. <font color=#FF0000> RealCapital:</font> 
        
    实际交易使用的资金基底。

<br>

>**<font color=#1E90FF>@DVC7_Set:  </font>计算评分函数&风险平价手数信号。**

1.	<font color=#FF0000>Lookbackdays:</font> 
    动能观察天期，选择区间大小影响股价变化对给分的敏感程度，选择越小的观察区间，股价短时间的 变动对动能给分影响越大。
   
2.	<font color=#FF0000>NegLeverage:</font>
    
    是否使用负动能反向模式，设定1为开启，0为关闭。
    
3.	<font color=#FF0000>WithSpread:</font>
    
    是否做策略换月价差调整，设定1为开启，0为关闭。鉴于新旧合约在转仓时，其因为换月所造成的价差跳空非属正常交易行为，容易造成回测失真，因此可透过此参数来修正持仓损益。
    
4.  <font color=#FF0000>StrategyChannel:</font>
    
    策略类别编号，比方波段策略都设定为1，当冲策略都设定为2，需为大于0之整数。
    
5.  <font color=#FF0000>StrategyChannelLimit:</font>
    
    该策略类别开放整合之策略总数上限，如设定5，代表该策略类别取评分前5名的策略进行整合，注意相同编号的策略类别，此上限值都须设定一样。
    
6. 	<font color=#FF0000>pCapital:</font> 
    
    用以计算风险平价手数的涉险金额，默认采取此值的5%进行每笔投资，涉险金额设定越高，每个商品的风险评价手数越大。
   
7.	<font color=#FF0000>RPLen:</font>
    
    波动率观察天期，用以计算风险评价手数。
    
8.	<font color=#FF0000>VolType:</font>
    
    波动率采用的计算方式，设定1为标准差，2为ATR，用以计算风险评价手数。
    
9.	<font color=#FF0000>PositionWeight:</font>
    
    该策略之下单权重，供使用者调整策略间之下单比例。

    <br>
    
> **<font color=#1E90FF>@DVC7_Order: </font> 策略评分整合&下单信号。**


1.  <font color=#FF0000>pCapital:  </font>
    
    该商品下单之参考资金，与资金基底搭配进行比例式下单，建议设定一个相对较大的数值，如10000000。
    
2.  <font color=#FF0000>CommodityChannel: </font>
    
    商品类别编号，比方指数期货都设定为1，农产品期货都设定为2，需为大于0之整数。
    
3.  <font color=#FF0000>CommodityChannelLimit: </font>
    
    该商品类别开放交易之商品总数上限，如设定3，代表该商品类别取总评分前3名的商品进行交易。
    
4.  <font color=#FF0000>StrategyTotalN: </font>
    
    该商品开放整合之策略总数上限，如设定12，代表该商品的策略池中，至多取12名策略进行整合。
    
5.  <font color=#FF0000>StrategyScoreThres: </font>
    
    策略评分门槛，评分高于此值才有资格进入整合名单。门槛越高，策略品质也相对高，但交易次数较少。
    
6.  <font color=#FF0000>WithSpread: </font>
    
    是否做商品换月价差调整，设定1为开启，0为关闭。鉴于新旧合约在转仓时，其因为换月所造成的价差跳空非属正常交易行为，容易造成回测失真，因此可透过此参数来修正持仓损益。

<br>

> **<font color=#1E90FF>@DVC7_XeusMM: </font> 商品管理信号。**

 
1.  <font color=#FF0000>CommodityTotalN:</font> 
    
    开放交易之商品总数上限，如设定15，代表整个投资组合至多交易15个商品。

2.  <font color=#FF0000>ChangeThres:</font> 
    
    商品总评分有效变量，当商品已持仓，且总评分变动超过此值，才进行加减码手数调整。有效变量设定越高，可避免策略受到杂讯而频繁进出。

3.  <font color=#FF0000>CommodityScoreThres:</font> 
    
    商品总评分门槛，当总评分超过此门槛，才开放该商品交易进场，且在此门槛之上，评分有效变量机制才会启用。

4.  <font color=#FF0000>CapitalName:</font>  
    
    评价后之权益曲线名称，命名规则为"UD.MCQuote.xxx"，其中xxx为自定义字串。

5.  <font color=#FF0000>RealCapital:</font>  
    
    实际交易使用的资金基底，与参考资金搭配进行比例式下单，建议设定一个相对参考资金较小的数值，如2000000。

6.  <font color=#FF0000>PosSize:</font>  
    
    资金杠杆参数，此值设定越大，涉险金额与部位规模也越大。

7.  <font color=#FF0000>IncWeight:</font>  
    
    即时损益再投入比例，将即时损益纳入加减码部位之比例，输入0代表不使用此条件。

8.  <font color=#FF0000>IncLimit:</font>  
    
    损益权重分配之上限。

9.  <font color=#FF0000>MaxLossPercent:</font>  
   
    策略最大亏损百分比，若当前浮动损益达到此值则强制平仓。以百分比表示，输入5代表5%，输入0代表不使用此条件。

10. <font color=#FF0000>RiskTakeType:</font>  
动用风险模式选择，用以控管新策略是否进场

    * 输入0: 关闭，对于新进场项目没有任何限制。
    * 输入1: 如果旧有部位加仓或新策略加入后会超过风险上限，则限制加仓或新策略加入。

11. <font color=#FF0000>RiskTakenLimit: </font> 
    
    动用风险上限。

12. <font color=#FF0000>NonProtect:</font> 
   
    未受保护商品数，为不受加仓保护垫级距限制的最大信号数量。

13. <font color=#FF0000>ProtectPad:</font> 
    
    加仓保护垫级距，当持仓商品数超过NonProtect但是尚未达到CommodityTotalN，则后续每新增一个商品，就会增加一个ProtectPad。

    例如NonProtect=4 (个)、CommodityTotalN=6 (个)、ProtectPad=50000，

    则当第5个商品要进来，需要前 4个商品浮动损益到达ProtectPad =50000，

    当第6个商品要进来需要前 5个商品浮动损益到达2*ProtectPad=2*50000=100000

<br>
 
>**<font color=#1E90FF>AutoLeverage:</font>  自动调整杠杆与可用资金缩放。**

1.  <font color=#FF0000>Len:</font> 
 
    模拟资金曲线之观察天期，比如可用于计算权益曲线之波动率、布林通道等。

2.  <font color=#FF0000>mainleverage:</font> 
    
    资金杠杆水位，可根据自定义演算法调整，来达到杠杆缩放。

3.  <font color=#FF0000>ReinvestmentDelta:</font> 
    
    可用资金缩放比例，以百分比表示，输入5代表5%，则当可用资金成长至105%(95%)时，会将可用资金更新至当前数值，进行资金缩放，输入0代表不使用此条件。

 <br>

## 二、MC 与 评价大师 实盘模板
 >**<font color=#1E90FF>@DVC7_ToDaVinci: </font>评分函数及风险平价口数信号，<font color=##32CD32>挂载于图表或PT皆可使用。</font>**

1.  <font color=#FF0000>Lookbackdays:</font> 
    动能观察天期，选择区间大小影响股价变化对给分的敏感程度，选择越小的观察区间，股价短时间的变动对动能给分影响越大。

2.  <font color=#FF0000>NegLeverage:</font>
    
    是否使用负动能反向模式，设定1为开启，0为关闭。

3.  <font color=#FF0000>WithSpread:</font>
    
    是否做策略换月价差调整，设定1为开启，0为关闭。鉴于新旧合约在转仓时，其因为换月所造成的价差跳空非属正常交易行为，容易造成损益计算失真，因此可透过此参数来修正持仓损益。

4.  <font color=#FF0000>StrategyChannel:</font>
    
    策略类别编号，比方波段策略都设定为1，当冲策略都设定为2。

5.  <font color=#FF0000>StrategyName:</font>
    
    由MC输出至评价大师所显示之策略名称，以两个双引号所涵盖的文字格式，如"MACD-L"。每个Strategy请输入不同名称，如有同策略但周期或参数不同，请加上其他文字或编号以供区隔，如"MACD-L1"、"MACD-L2"。

6.  <font color=#FF0000>pCapital:</font>
    
    该商品下单之参考资金，与资金基底搭配进行比例式下单，建议设定一个相对较大的数值，如10000000，注意此值须与评价大师中的参考资金设定相同。

7.  <font color=#FF0000>RPLen:</font> 
    
    波动率观察天期，用以计算风险评价手数。

8.  <font color=#FF0000>VolType:</font>
    
    波动率采用的计算方式，设定1为标准差，2为ATR，用以计算风险评价手数。

9.  <font color=#FF0000>PositionWeight:</font>
    
    该策略之下单权重，供使用者调整策略间之下单比例。


