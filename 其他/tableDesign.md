# 表设计

## 消息日志表 （twins_message_log）

| 字段名称       | 字段类型      | 备注                      |
| -------------- | ------------- | ------------------------- |
| id             | bigint        | 主键id                    |
| topic          | varchar(100)  | 管道名称                  |
| type           | varchar(100)  | 事件类型                  |
| message_key    | varchar(100)  | 事件key                   |
| message_value  | varchar(2000) | 消息内容                  |
| message_status | int(2)        | 消息状态 1：成功  0：失败 |
| create_time    | datetime      | 消息产生时间              |
| create_user    | varchar(100)  | 创建消息的用户id          |



## 孪生体表（twins_info）
| 字段名称     | 字段类型      | 备注                                                         |
| ------------ | ------------- | ------------------------------------------------------------ |
| id           | bigint        | 主键id                                                       |
| twins_name   | varchar(100)  | 孪生体名称                                                   |
| twins_desc   | varchar(1000) | 孪生体介绍                                                   |
| twins_status | int           | 1：创建中  2：修改中  3：已发布  4：订阅？？  5：已停用   6：已删除 |
| create_time  | datetime      | 创建时间                                                     |
| create_user  | varchar(50)   | 创建人                                                       |
| update_time  | datetime      | 更新时间                                                     |
| update_user  | varchar(50)   | 更新人                                                       |



## 动态属性表（twins_dynamic_property）

| 字段名称       | 字段类型     | 备注                   |
| -------------- | ------------ | ---------------------- |
| id             | bigint       | 主键id                 |
| telemetry_name | varchar(50)  | 动态属性名称           |
| telemetry_tag  | varchar(50)  | 动态属性对应的位号名称 |
| instance_id    | varchar(100) | 实例id                 |
| create_time    | datetime     | 创建时间               |
| create_user    | varchar(50)  | 创建人                 |
| update_time    | datetime     | 更新时间               |
| update_user    | varchar(50)  | 更新人                 |



## 仿真属性表 （twins_simulation_property）

| 字段名称        | 字段类型     | 备注         |
| --------------- | ------------ | ------------ |
| id              | bigint       | 主键id       |
| simulation_name | varchar(100) | 仿真属性名称 |
| instance_id     | varchar(100) | 实例id       |
| service_id      | bigint       | 仿真服务id   |
| task_id         | varchar(100) | 任务id       |
| create_time     | datetime     | 创建时间     |
| create_user     | varchar(50)  | 创建人       |
| update_time     | datetime     | 更新时间     |
| update_user     | varchar(50)  | 更新人       |



## 服务配置表（twins_service）

| 字段名称         | 字段类型      | 备注                                                         |
| ---------------- | ------------- | ------------------------------------------------------------ |
| id               | bigint        | 主键id                                                       |
| service_name     | varchar(100)  | 仿真服务名称                                                 |
| service_url      | varchar(200)  | 仿真服务地址                                                 |
| service_params   | varchar(1000) | 仿真请求参数（json格式描述字符串）<br />[{"index":1,"name":"温度s","dataType":"double"},{"index":2,"name":"湿度s","dataType":"double"}] |
| service_response | varchar(1000) | 仿真响应结果（json格式描述字符串）                           |
| request_type     | varchar(10)   | GET / POST                                                   |
| create_time      | datetime      | 创建时间                                                     |
| create_user      | varchar(50)   | 创建人                                                       |
| update_time      | datetime      | 更新时间                                                     |
| update_user      | varchar(50)   | 更新人                                                       |



## 位号历史表（twins_history_telemetry）
| 字段名称 | 字段类型 | 备注 |
| -------- | -------- | ---- |




## 仿真结果历史表（twins_history_service）

| 字段名称 | 字段类型 | 备注 |
| -------- | -------- | ---- |



## 消息定义表（twins_message）
| 字段名称     | 字段类型      | 备注                 |
| ------------ | ------------- | -------------------- |
| id           | bigint        | 主键id               |
| message_name | varchar(100)  | 名称                 |
| message_desc | varchar(1000) | 描述                 |
| instance_id  | bigint        | 实例id               |
| service_id   | bigint        | 服务id               |
| telemetries  | varchar(1000) | 位号列表（逗号分割） |
| create_time  | datetime      | 创建时间             |
| create_user  | varchar(50)   | 创建人               |
| update_time  | datetime      | 更新时间             |
| update_user  | varchar(50)   | 更新人               |



## APP订阅表（twins_message_app）

| 字段名称     | 字段类型     | 备注         |
| ------------ | ------------ | ------------ |
| id           | bigint       | 主键id       |
| message_id   | bigint       | 消息定义id   |
| app_id       | varchar(100) |              |
| message_host | varchar(500) | 消息推送地址 |
| create_time  | datetime     | 创建时间     |
| create_user  | varchar(50)  | 创建人       |
| update_time  | datetime     | 更新时间     |
| update_user  | varchar(50)  | 更新人       |