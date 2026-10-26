# 阿里云99计划开通和续费避坑指南：ECS、RDS、OSS购买入口与真实踩坑记录

> **先说结论：** 如果你想买或者买过阿里云99计划，续费时先核对活动资格和最终订单金额，别看到普通续费价格就直接付款。
> 本文整理我实际使用ECS、RDS和OSS的经历，以及活动入口、配置与踩坑提醒。
>
> 最后更新：2026年10月24日。文中价格来自个人购买经历和当时活动页面，具体优惠、库存、续费资格以阿里云当前订单页面为准。

最近在续费阿里云的99计划，发现阿里云的99计划，续费的入口藏起来了，找不到差点就按照原价续了。

记录一下99计划各个项目的开通和续费的链接，以备不时之需。

## 一、阿里云99计划怎么买、怎么续费？先说结论

说真的，阿里云网页和App的产品入口太多，活动页、控制台、优惠券页来回跳，生怕用户血压低。

我把常用入口整理在这里，省得下次再找：

- [新用户8折券领取入口](https://www.aliyun.com/minisite/goods?userCode=dta1yxw3)
- [ECS 99计划活动页](https://www.aliyun.com/activity/ecs/99program?source=5176.29345612&userCode=dta1yxw3)
- [RDS MySQL优惠活动页](https://www.aliyun.com/benefit/waitou/polardb?source=5176.29345612&userCode=dta1yxw3)
- [OSS 优惠活动页](https://www.aliyun.com/activity/storage/storage_promotion_?source=5176.29345612&userCode=dta1yxw3)

## 二、为什么我最后买了RDS和OSS？

最开始我买99计划，只买了两台ECS，99元和199元的都买了。

99元的机器主要部署Nginx和Python服务，199元的机器部署MySQL和Redis，文件就存ECS上。

后来又加了一个Java项目。99元那台2G内存的机器有点吃力，只能把Java项目塞进199元的机器。但MySQL、Redis和Java服务放在一起，CPU和内存都要抢，后续维护也不省心。

我想过再买一台ECS自己部署mysql，后来觉得数据库备份、升级和故障恢复还是得自己处理，不如把数据库和缓存拆出去，**关键是原价的ECS太太太贵了！**

最后买了：

- **ECS 2C2G：99元/年**（99计划）
- **ECS 2C4G：199元/年**（99计划）
- **RDS MySQL：99元/年**（99计划）
- **OSS：119元/年**（99计划）
- **Tair(Redis)：72元/年**（新用户）

ECS专门跑应用，RDS存业务数据，Tair做缓存，文件存OSS。不是说这个架构多高级，主要是把资源拆开以后，不用再让数据库和Java服务挤一台机器。

当然，如果只是临时测试项目，直接在ECS上用Docker装MySQL和Redis也没问题，不必为了用云数据库而用云数据库。

## 三、阿里云99元ECS购买入口在哪里？

ECS的入口相对好找：

**[阿里云99元ECS活动入口](https://www.aliyun.com/activity/ecs/99program?source=5176.29345612&userCode=dta1yxw3)**

![阿里云99计划ECS云服务器活动页面截图](https://github.com/user-attachments/assets/f4f5d374-79f0-482c-9a64-02cc99889bd1)

配置如下：

| 项目 | ECS经济型e实例 |
|---|---|
| CPU | 2核 |
| 内存 | 2GB |
| 公网带宽 | 3Mbps固定带宽 |
| 系统盘 | 40GB ESSD Entry |
| 参考活动价 | 99元/年 |
| 续费 | 以实例资格和活动条款为准 |

### ECS 99计划怎么续费？

1. 登录阿里云，进入ECS实例列表。

2. 找到原来参加99计划的实例，核对实例ID、规格和到期时间。

3. 打开[99计划活动页](https://www.aliyun.com/activity/ecs/99program?source=5176.29345612&userCode=dta1yxw3)，查看当前续费权益说明。

4. 从对应实例发起续费，确认是否享有活动优惠。

5. **核对最终支付金额**，确认无误后再付款。

## 四、阿里云RDS MySQL 99元购买入口

相比ECS，RDS活动入口更不好找。网上很多教程点进去就是推广页面，往下翻半天才看到数据库。

我整理的入口：**[阿里云RDS MySQL优惠活动页](https://www.aliyun.com/benefit/waitou/polardb?source=5176.29345612&userCode=dta1yxw3)**。

打开后向下滚动，找云数据库活动区域：

![阿里云RDS MySQL活动页面和数据库套餐入口截图](https://github.com/user-attachments/assets/29af12b0-3e3a-41e9-9a1e-433b54389251)

### RDS MySQL 2核2G 50GB：参考价99元/年

| 项目 | 配置 |
|---|---|
| 数据库 | RDS MySQL |
| 系列 | 基础系列经济版 |
| CPU | 2核 |
| 内存 | 2GB |
| 存储 | 50GB |
| 云盘 | 通用云盘 |
| 当时活动价 | 99元/年 |

### RDS MySQL 2核4G 100GB：参考价227.99元/年

| 项目 | 配置 |
|---|---|
| 数据库 | RDS MySQL |
| 系列 | 基础系列 |
| CPU | 2核 |
| 内存 | 4GB |
| 存储 | 100GB |
| 云盘 | 高性能云盘 |
| 当时活动价 | 227.99元/年 |

### RDS 99元套餐能同价续费吗？

目前看，是可以原价续费的，明年的事明年再说。

## 五、OSS 99元购买入口

我整理的入口：**[阿里云OSS优惠活动页](https://www.aliyun.com/activity/storage/storage_promotion_?source=5176.29345612&userCode=dta1yxw3)**。

打开后向下滚动，找到："存" 享优惠

新老用户同享优惠活动，OSS 低至 118.99 元/1 年

### OSS 对象存储 标准 - 本地冗余

海量、安全、低成本、高可靠的云存储服务

标准 - 本地冗余存储规格

500GB 1年

> 同时还有其它容量、安全等级可选，以及 NAS文件存储

## 六、阿里云99计划续费为什么会变贵？

我觉得最容易踩的就是这三个坑：

**1. 直接在普通续费页付款。** 活动优惠不一定自动显示。价格不对，先别付款。

**2. 中途改了实例配置。** 升配、变更产品规格可能影响优惠资格，操作前先看活动条款。

**3. 把首购价当长期价。** 尤其是数据库和缓存产品，首年便宜不等于后续一直便宜。

## 七、阿里云99计划常见问题（FAQ）

### 阿里云99元ECS第二年还是99元吗？

符合指定活动规则的实例可能享受同价续费，但是否满足资格、是否有次数限制、是否变配，都需要按当前活动条款判断。

### 99计划能叠加优惠券吗？

不一定。是否允许与优惠券叠加，要看券的使用条件及订单结算页，不要默认所有活动都能折上折。

## 八、最后聊两句

这次续费折腾下来，我最大的感受就是：买的时候挺容易，续费时真得仔细找。

我现在的方案是99元ECS跑Nginx和Python，199元ECS跑Java，MySQL和Redis分别放到RDS和Redis上，文件就存OSS上。主要是资源分开以后维护更省心。

99计划对个人开发者确实有吸引力，但买之前还是得想清楚项目需不需要这些资源。**先看需求，再看配置，最后看价格和续费条款。**

如果你也在找阿里云99计划的购买或续费入口，希望这篇记录能帮你少折腾一会儿。

> **推广链接说明：** 文中部分活动链接包含 `userCode` 推广参数，介意的话可以去掉哈。

## 官方参考资料

- [阿里云99计划ECS活动页](https://www.aliyun.com/activity/ecs/99program?source=5176.29345612&userCode=dta1yxw3)
- [阿里云资源续费常见问题](https://help.aliyun.com/zh/user-center/support/renewal-guide-q-a)
- [阿里云RDS续费政策](https://help.aliyun.com/zh/rds/product-overview/renewal-policy)
- [阿里云OSS续费政策](https://help.aliyun.com/zh/oss/renew-resource-plans)
