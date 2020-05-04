# patent-analysis
本专利分析系统主要完成的任务为：1、预测侵权专利赔偿金额；2、根据产品特征和权利要求说明书文本判断产品是否侵权。

对于任务一，首先在3000份左右专利相关的判决书文本中提取出了：
# 专利类型
#案件受理年份
#案件判决年份
#专利权人是否为外国人
#'原告数量
#'原告类型
#'被告数量
#'被告类型
#'侵权企业规模
# '请求赔偿金额
#'地区变量
# '侵权行为数量
# 请是否恶意侵权
# '赔偿金额
几个变量，经相关性分析和回归分析处理之后得到了与赔偿金额最相关的几个因素。并搭建了DNN深度神经网络对赔偿金额进行预测。

对于任务二,处理思路是使用word2vec增强的vsm模型，计算专利的权利要求说明书文本和产品特征文本的相似度，如果相似度大于0.5，则认为产品侵权。

先使用python对以上任务进行处理，处理完成后，利用argprase封装，以供web后台调用。之后利用springboot搭建了一个简单的web系统，通过调用
算法接口实现用户对算法的使用。web服务是以jar包方式，运行在linux服务器上以供用户访问的。
 
