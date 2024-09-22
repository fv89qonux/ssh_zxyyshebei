## 本项目实现的最终作用是基于SSH在线预约高校科研实验室设备平台
## 分为3个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 实验室管理
 - 实验室预约
 - 技术参数管理
 - 查看预约记录
 - 用户信息管理
 - 电子文档管理
 - 管理员登录
 - 设备保修日志管理
 - 设备借用日志管理
 - 设备借用管理
 - 设备维修管理
 - 运行数据管理
 - 通知管理
### 第2个角色为教师角色，实现了如下功能：
 - 实验室预约管理
 - 教师登录
 - 用户信息管理
 - 设备借用管理
 - 通知管理
### 第3个角色为学生角色，实现了如下功能：
 - 学生登录
 - 用户信息管理
 - 设备借用管理
 - 通知管理
## 数据库设计如下：
# 数据库设计文档

**数据库名：** ssh_zxyyshebei

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [t_brand](#t_brand) |  |
| [t_category](#t_category) | 分类表 |
| [t_equipment](#t_equipment) |  |
| [t_equipmentlog](#t_equipmentlog) |  |
| [t_introduction](#t_introduction) |  |
| [t_laboratory](#t_laboratory) |  |
| [t_laboratorylog](#t_laboratorylog) |  |
| [t_message](#t_message) |  |
| [t_notice](#t_notice) |  |
| [t_photo](#t_photo) |  |
| [t_purchase](#t_purchase) |  |
| [t_repairlog](#t_repairlog) |  |
| [t_role](#t_role) |  |
| [t_user](#t_user) | 用户表 |

**表名：** <a id="t_brand">t_brand</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | isDelete |   int   | 10 |   0    |    Y     |  N   |   NULL    | 是否删除  |
|  3   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |
|  4   | Category_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_category">t_category</a>

**说明：** 分类表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | isDelete |   int   | 10 |   0    |    Y     |  N   |   NULL    | 是否删除  |
|  3   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |
|  4   | photo |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 照片  |

**表名：** <a id="t_equipment">t_equipment</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | bz |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 备注  |
|  3   | isBx |   int   | 10 |   0    |    N     |  N   |   0    |   |
|  4   | isDelete |   int   | 10 |   0    |    N     |  N   |   0    | 是否删除  |
|  5   | jg |   double   | 23 |   0    |    Y     |  N   |   NULL    |   |
|  6   | sbxlh |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | time |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 时间  |
|  8   | xh |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  9   | zzs |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  10   | Laboratory_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  11   | fwTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    |   |
|  12   | ht |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  13   | isFw |   int   | 10 |   0    |    N     |  N   |   0    |   |
|  14   | photo |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 照片  |
|  15   | bxLogid |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  16   | isJy |   int   | 10 |   0    |    N     |  N   |   0    |   |
|  17   | jyId |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  18   | JyUser_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_equipmentlog">t_equipmentlog</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | endTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 结束时间  |
|  3   | isYy |   int   | 10 |   0    |    N     |  N   |   0    |   |
|  4   | qx |   tinyblob   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | time |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 时间  |
|  6   | user |   tinyblob   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | Equipment_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  8   | qx_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  9   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |

**表名：** <a id="t_introduction">t_introduction</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | gg |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  3   | isDelete |   int   | 10 |   0    |    Y     |  N   |   NULL    | 是否删除  |
|  4   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |

**表名：** <a id="t_laboratory">t_laboratory</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | address |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 地址  |
|  3   | bz |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 备注  |
|  4   | fzr |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | fzrDh |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | isDelete |   int   | 10 |   0    |    N     |  N   |   0    | 是否删除  |
|  7   | isYy |   int   | 10 |   0    |    N     |  N   |   0    |   |
|  8   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |
|  9   | time |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 时间  |
|  10   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |
|  11   | laboratoryLogId |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_laboratorylog">t_laboratorylog</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | isYy |   int   | 10 |   0    |    N     |  N   |   0    |   |
|  3   | time |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 时间  |
|  4   | laboratory_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  5   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |
|  6   | endTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 结束时间  |
|  7   | userQx_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_message">t_message</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | count |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  3   | isDelete |   int   | 10 |   0    |    Y     |  N   |   NULL    | 是否删除  |
|  4   | msg |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | time |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 时间  |
|  6   | User_Fsr |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  7   | User_Jsr |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_notice">t_notice</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | isDelete |   int   | 10 |   0    |    N     |  N   |   0    | 是否删除  |
|  3   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |
|  4   | nr |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | time |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 时间  |

**表名：** <a id="t_photo">t_photo</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | count |   int   | 10 |   0    |    Y     |  N   |   NULL    | 数量  |
|  3   | fileName1 |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  4   | fileName2 |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | fileName3 |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | fileName4 |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | isDelete |   int   | 10 |   0    |    Y     |  N   |   NULL    | 是否删除  |
|  8   | jg |   double   | 23 |   0    |    N     |  N   |       |   |
|  9   | js |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  10   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |
|  11   | brand_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  12   | category_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  13   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |

**表名：** <a id="t_purchase">t_purchase</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | count |   int   | 10 |   0    |    Y     |  N   |   NULL    | 数量  |
|  3   | isDelete |   int   | 10 |   0    |    Y     |  N   |   NULL    | 是否删除  |
|  4   | money |   double   | 23 |   0    |    N     |  N   |       | 金额  |
|  5   | price |   double   | 23 |   0    |    N     |  N   |       | 价格  |
|  6   | time |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 时间  |
|  7   | photo_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  8   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |

**表名：** <a id="t_repairlog">t_repairlog</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | bxTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    |   |
|  3   | bz |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 备注  |
|  4   | endTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 结束时间  |
|  5   | isDelete |   int   | 10 |   0    |    N     |  N   |   0    | 是否删除  |
|  6   | title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  7   | wz |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  8   | Equipment_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_role">t_role</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | enName |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  3   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |

**表名：** <a id="t_user">t_user</a>

**说明：** 用户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | bj |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  3   | isDelete |   int   | 10 |   0    |    N     |  N   |   0    | 是否删除  |
|  4   | isSh |   int   | 10 |   0    |    N     |  N   |   0    |   |
|  5   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |
|  6   | number |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | pass |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 密码  |
|  8   | phone |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 电话  |
|  9   | realname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 真实名字  |
|  10   | time |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 时间  |
|  11   | xy |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  12   | role_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 角色ID  |
|  13   | address |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 地址  |
|  14   | bz |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 备注  |
|  15   | fzr |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  16   | fzrDh |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  17   | isYy |   int   | 10 |   0    |    N     |  N   |   0    |   |
|  18   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |

