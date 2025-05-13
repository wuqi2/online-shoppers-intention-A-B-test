# 线上购物者购物意图A/B测试分析 | Online Shopper Purchasing Intention A/B Test Analysis Project

## 项目概述
本项目利用"Online Shoppers Purchasing Intention Dataset"数据集，分析电商用户行为并进行营销策略的A/B测试。通过对用户行为模式、时间因素和技术环境的深入分析，提出有针对性的营销策略建议。

## 数据集信息
- **数据来源**: UCI机器学习存储库
- **链接**: https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset
- **引用**: Sakar, C.O., Polat, S.O., Katircioglu, M. et al. (2019). Real-time prediction of online shoppers' purchasing intention using multilayer perceptron and LSTM recurrent neural networks. Neural Computing and Applications, 31(10), 6893-6908.
- **数据规模**: 12,330个电商会话数据

## 特征说明
数据集包含以下特征：

### 页面访问相关变量 (6个)
- Administrative: 管理类页面访问次数
- Administrative_Duration: 管理类页面停留时间(秒)
- Informational: 信息类页面访问次数
- Informational_Duration: 信息类页面停留时间(秒)
- ProductRelated: 产品相关页面访问次数
- ProductRelated_Duration: 产品相关页面停留时间(秒)

### 网站质量指标 (3个)
- BounceRates: 跳出率(单页访问比例)
- ExitRates: 退出率(从该页面离开网站的比例)
- PageValues: 页面价值(该页面对最终交易的贡献值)

### 时间相关变量 (2个)
- SpecialDay: 与特殊日期的接近度(0-1)
- Month: 访问月份

### 技术环境变量 (3个)
- OperatingSystems: 操作系统类型(1-8)
- Browser: 浏览器类型(1-13)
- Region: 地理区域(1-9)

### 流量和用户特征 (3个)
- TrafficType: 流量来源类型(1-20)
- VisitorType: 访客类型(新访客/回访客/其他)
- Weekend: 是否为周末访问(布尔值)

### 目标变量
- Revenue: 是否完成购买(布尔值)

## 数据分析结果摘要

### 用户行为分析
- 产品页面是用户主要访问的页面类型，平均访问约31.5次，平均停留约1180秒
- 页面价值与转化率呈强烈正相关关系，是预测转化的最强指标
- 退出率与转化率呈正相关关系
- 跳出率与转化率的关系较为复杂，呈现非线性特征

### 时间因素影响
- 电商平台转化率存在明显季节性，下半年(7-11月)转化率普遍高于上半年
- 11月达到全年最高转化率(25.4%)，2月转化率最低(1.6%)
- 特殊日期前一段时间(接近度0.6)的转化率高于特殊日当天或临近日

### 用户细分分析
- 新访客转化率(24.9%)显著高于回访用户(13.9%)
- 周末访问的转化率(17.4%)高于工作日(14.9%)
- 浏览器和操作系统类型对转化率有显著影响，最高差距可达6倍

### A/B测试结果
- 基于用户活跃度的分组测试最成功，测试组转化率提升了132.5%
- 基于访客类型的分组测试也非常有效，测试组转化率提升了76.7%
- 不同用户群体对测试干预的反应不同，新用户提升幅度略高于回访用户

## 营销策略建议

1. **季节性优化**: 加强11月等高转化月份的营销投入，为2月等低转化月份制定专门策略
2. **特殊日期策略**: 在特殊日期前(接近度0.6和0.2)部署促销活动，而非特殊日当天
3. **新用户获取**: 增加新用户获取渠道和首单优惠策略
4. **回访用户激活**: 针对占比最大但转化率较低的回访用户群体制定重激活计划
5. **周末营销**: 增加周末特别促销活动
6. **技术优化**: 优先支持转化率高的浏览器和操作系统用户体验

## 项目结构
```
├── data/
│   └── online_shoppers_intention.csv
├── analysis/
│   ├── user_behavior_analysis.ipynb
│   ├── time_factors_analysis.ipynb
│   └── ab_test_analysis.ipynb
├── src/
│   ├── data_preprocessing.py
│   └── ab_test.py
└── README.md
```

## 数据来源引用
Sakar, C.O., Polat, S.O., Katircioglu, M. et al. (2019). Online Shoppers Purchasing Intention Dataset. UCI Machine Learning Repository. https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset

---

# Project Overview
This project uses the "Online Shoppers Purchasing Intention Dataset" to analyze e-commerce user behavior and conduct A/B testing of marketing strategies. Through in-depth analysis of user behavior patterns, time factors, and technical environment, targeted marketing strategy recommendations are proposed.

## Dataset Information
- **Data Source**: UCI Machine Learning Repository
- **Link**: https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset
- **Citation**: Sakar, C.O., Polat, S.O., Katircioglu, M. et al. (2019). Real-time prediction of online shoppers' purchasing intention using multilayer perceptron and LSTM recurrent neural networks. Neural Computing and Applications, 31(10), 6893-6908.
- **Data Size**: 12,330 e-commerce session records

## Feature Description
The dataset includes the following features:

### Page Visit Variables (6)
- Administrative: Administrative page visit count
- Administrative_Duration: Time spent on administrative pages (seconds)
- Informational: Informational page visit count
- Informational_Duration: Time spent on informational pages (seconds)
- ProductRelated: Product-related page visit count
- ProductRelated_Duration: Time spent on product-related pages (seconds)

### Website Quality Metrics (3)
- BounceRates: Bounce rate (percentage of single-page visits)
- ExitRates: Exit rate (percentage of exits from page)
- PageValues: Page value (contribution to transaction)

### Time Variables (2)
- SpecialDay: Proximity to special day (0-1)
- Month: Visit month

### Technical Environment Variables (3)
- OperatingSystems: Operating system type (1-8)
- Browser: Browser type (1-13)
- Region: Geographic region (1-9)

### Traffic and User Characteristics (3)
- TrafficType: Traffic source type (1-20)
- VisitorType: Visitor type (New_Visitor/Returning_Visitor/Other)
- Weekend: Weekend visit (boolean)

### Target Variable
- Revenue: Purchase completion (boolean)

## Analysis Results Summary

### User Behavior Analysis
- Product pages are the main page type visited by users, with an average of 31.5 visits and 1180 seconds spent
- Page value shows a strong positive correlation with conversion rate and is the strongest predictor of conversion
- Exit rate has a positive correlation with conversion rate
- The relationship between bounce rate and conversion rate is complex and non-linear

### Time Factor Impact
- E-commerce platform conversion rates show clear seasonality, with higher rates in the second half of the year (July-November)
- November has the highest annual conversion rate (25.4%), while February has the lowest (1.6%)
- Conversion rates are higher a period before special days (proximity 0.6) than on or near the special day itself

### User Segmentation Analysis
- New visitor conversion rate (24.9%) is significantly higher than returning visitors (13.9%)
- Weekend visits have a higher conversion rate (17.4%) than weekdays (14.9%)
- Browser and operating system types significantly impact conversion rates, with differences up to 6 times

### A/B Test Results
- Activity-based grouping test was most successful, with a 132.5% increase in conversion rate for the test group
- Visitor type-based grouping was also very effective, with a 76.7% increase
- Different user groups respond differently to test interventions, with new users showing slightly higher improvement than returning users

## Marketing Strategy Recommendations

1. **Seasonal Optimization**: Strengthen marketing investment in high-conversion months like November and develop specific strategies for low-conversion months like February
2. **Special Day Strategy**: Deploy promotional activities before special days (proximity 0.6 and 0.2) rather than on the special day itself
3. **New User Acquisition**: Increase new user acquisition channels and first-order discount strategies
4. **Returning User Activation**: Develop reactivation plans for returning users who comprise the largest proportion but have lower conversion rates
5. **Weekend Marketing**: Increase special promotional activities on weekends
6. **Technical Optimization**: Prioritize support for browsers and operating systems with higher conversion rates

## Project Structure
```
├── data/
│   └── online_shoppers_intention.csv
├── analysis/
│   ├── user_behavior_analysis.ipynb
│   ├── time_factors_analysis.ipynb
│   └── ab_test_analysis.ipynb
├── src/
│   ├── data_preprocessing.py
│   └── ab_test.py
└── README.md
```

## Data Source Citation
Sakar, C.O., Polat, S.O., Katircioglu, M. et al. (2019). Online Shoppers Purchasing Intention Dataset. UCI Machine Learning Repository. https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset
