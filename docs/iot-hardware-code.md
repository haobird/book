# 硬件程序

## example 普通例子路程梳理

### 第一区块

定义设备的身份三元组


### 定义 结构体


### 定义函数

* 上报属性temperature到云端(app_post_event_hotAlarm)
* 上报事件hotAlarm到云端(app_post_event_hotAlarm)
* 解析所有属性设置的值(app_parse_property)
* 建连成功事件回调(user_connected_event_handler)
* 断开连接事件回调(user_disconnected_event_handler)
* 设备初始化成功事件回调(user_initialized)
* 事件回调：接收到云端回复属性上报应答(user_report_reply_event_handler)
* 事件回调：接收到云端回复的事件上报应答(user_trigger_event_reply_event_handler)
* 事件回调：接收到云端下发的属性设置(user_property_set_event_handler)
* 事件回调：接收到云端下发的服务请求(user_service_request_event_handler)
* 事件回调：接收到云端回复的时间戳(user_timestamp_reply_event_handler)
* FOTA事件回调处理（user_fota_event_handler）
* 事件回调：接收到云端错误信息(user_cloud_error_handler)
* 事件回调：通过动态注册获取到DeviceSecret（dynreg_device_secret）
* 事件回调: SDK内部运行状态打印（user_sdk_state_dump）

