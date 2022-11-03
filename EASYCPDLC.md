基于https://github.com/josh-seagrave/EasyCPDLC/wiki/改动，

由Ziran Jin翻译。

接下来为大家介绍一个方便的外挂CPDLC应用，EasyCPDLC。

## 什么是EasyCPDLC？

管制员飞行机组数据链通信（CPDLC）是一种航空数据传输系统，允许通过文本消息传输指令，查询和请求，而不是使用无线电通信。其主要目的是减少 RTF 拥塞，并促进工作量较少的非紧急消息更轻松地传输，特别是在无线电覆盖范围不可靠的地区，或者由于与收发器的距离而强制要求使用高频无线电（HF）的地区。

EasyCPDLC的开发是为了方便机模没有内置CPDLC功能，并且使用VATSIM和Hoppie网络的用户。它的设计以易于设置和易用性为核心原则，避免了冗长的设置和复杂的 UI 以及窗口。

## 使用EasyCPDLC

### 窗口操作

EasyCPDLC的视觉外观设计干净且易于理解。这意味着应用可以尽可能不依赖菜单栏。所有窗口都可以通过单击并拖动窗口的右下角来调整大小，也可以通过单击并拖动 EasyCPDLC 徽标来移动。

### 窗口中的描述

本节包含 EasyCPDLC 中所有窗口和面板的视觉和文本描述，用作导航和理解 EasyCPDLC 的操作。

### 登录窗口

登录窗口是您进入 EasyCPDLC 的必经之路。它包含 2 个输入框，一个用于填写您的 Hoppie 登录代码，一个用于填写您的 VATSIM CID。如果您希望EasyCPDLC存储您的详细信息以备将来使用，请勾选“Remember Me?”框。填写完您的详细信息后，单击“Connect”。这将带您进入EasyCPDLC主窗口。

![Login Window Image](media/8a9d586c0e1f5d4609fddf38b345a71f.png)

### 主窗口

主窗口是启动或操作所有其他 CPDLC 功能的位置。它由几个单独的按钮组成，每个按钮都有一个专用功能。

![Main Window Image](media/8462bdc5268b723903e8bc111cbd313e.png)

| **按钮**               | **功能**                                                                                                                                                                                                                                      |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 消息区                 | 主窗口的前端和中心是消息界面。这是显示所有发送和接收消息的位置。单击任何消息将显示[消息管理菜单](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#the-message-management-menu)。右键单击任何空白位置将出现删除所有消息的选项。 |
| **CONNECT** 按钮       | **连接**按钮初始化应用与所有必要的外部网络的连接，例如Hoppie，Simbrief和您的飞行模拟器。                                                                                                                                                      |
| **TELEX**按钮          | **TELEX**按钮可打开“TELEX”窗口。                                                                                                                                                                                                              |
| **ATC**按钮            | **ATC** 按钮可打开 [CPDLC 窗口](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#the-atc-window)。                                                                                                                             |
| 设置按钮               | 点击设置按钮（在右上角显示为齿轮）打开设置窗口。                                                                                                                                                                                              |
| “Current ATC Unit”字段 | **当前 ATC 单元**字段将显示 EasyCPDLC 当前正在与之通信的空中交通服务单元 （ATSU） 的标识符。如果没有有效的 ATSU，该字段将显示 4 条虚线。                                                                                                      |

### 消息管理菜单

消息管理菜单用于消息管理。

| **元素**       | **功能**                                                      |
|----------------|---------------------------------------------------------------|
| **DELETE**按钮 | 删除当前消息。对于尚未确认或响应的 CPDLC 消息，将禁用此功能。 |
| 回复选项       | 根据上下文和收到的消息，将显示几个回复子选项。                |

### “回复”子菜单

“回复”子菜单有助于回复收到的消息。根据所收到的消息的不同，将提供不同的选项。EasyCPDLC 会自动推断哪些回复选项有效，因此只会显示适当的选项。

| **消息类型** | **功能**                                                             |
|--------------|----------------------------------------------------------------------|
| FREE TEXT    | 打开 TELEX 窗口的FREE TEXT模式，收件人已预先填充为原始信息的发件人。 |
| WILCO        | 发送 WILCO 消息作为回复。                                            |
| UNABLE       | 发送 UNABLE消息作为回复。                                            |
| ROGER        | 发送 ROGER 消息作为回复。                                            |
| STANDBY      | 发送STANDBY消息作为回复。                                            |
| AFFIRM       | 发送 AFFIRM 消息作为回复。                                           |
| NEGATIVE     | 发送NEGATIVE消息作为回复。                                           |
| ACCEPT       | 仅适用于DCL，接受放行                                                |
| REJECT       | 仅适用于DCL，拒绝放行                                                |

### “设置”窗口

设置窗口允许更改 EasyCPDLC的选项。

![Settings Window Image](media/4e2a9d2cefbff4c152d60ac780895c5e.png)

| **元素**                       | **功能**                                                                                                                 |
|--------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| 保持窗口位于顶部 （是/否）     | 适用于所有 EasyCPDLC 窗口。                                                                                              |
| 在消息接收时播放声音 （是/否） | 设置 EasyCPDLC 在收到消息时是否播放音频提醒。                                                                            |
| 使用模拟器连接 （是/否）       | 设置 EasyCPDLC 是否与模拟器交互。这可以实现某些功能，例如 ADS-C 自动位置报告和某些字段的预填充。                         |
| Simbrief Pilot ID              | 如果输入了有效的Simbrief Pilot ID，EasyCPDLC将从Simbrief加载最新的飞行计划，并使用它来生成可用于位置报告等的报告点列表。 |
| CANCEL                         | 取消所有更改并恢复到窗口打开之前的状态。                                                                                 |
| OK                             | 保存更改并使用它们。                                                                                                     |

### TELEX窗口

TELEX窗口便于发送TELEX消息和信息请求。默认情况下，TELEX 窗口处于“FREE TEXT”操作模式。

![TELEX Window Image](media/7cec5a2230f1dfbea08c783297d99e9b.png)

| **元素**          | **功能**                                                                                                                                        |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| “消息操作”面板    | “消息操作”面板有助于编辑消息。它将显示一个可编辑的模板，具体取决于窗口所处的操作模式。                                                          |
| **FREE TEXT**状态 | TELEX 窗口的默认状态。将“邮件操作面板”更改为[“FREE TEXT”模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#free-text-mode)。 |
| **METAR按钮**     | 将消息操作面板更改为 METAR 请求模式。                                                                                                           |
| **ATIS按钮**      | 将消息操作面板更改为 [ATIS 请求模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#atis-request-mode)。                       |
| **CLEAR按钮**     | 将邮件操作面板返回到默认 TELEX 状态并清除所有数据字段。                                                                                         |
| **SEND按钮**      | 发送消息。                                                                                                                                      |

## 接下来介绍TELEX界面子菜单。

### FREE TEXT 模式

FREE TEXT模式是 TELEX 子页面的默认模式。它有助于向Hoppie网络上的任何其他用户发送文本消息（最多255个字符），包括其他飞机，ACARS和调度站以及ATC。

![FREE TEXT Mode Image](media/7cec5a2230f1dfbea08c783297d99e9b.png)

| **元素**      | **描述**                              |
|---------------|---------------------------------------|
| **RECIPIENT** | 收件人的身份标识（如CCA2333，ZGZU等） |
| **MSG**       | 消息内容（最多允许 255 个字符）。     |

### METAR报文请求模式

METAR 报文请求模式允许发送 METAR 请求。如果成功，系统将返回指定机场的最新 METAR。

![METAR REQUEST Mode Image](media/b70fe5dc3c9479733c1640127d913e70.png)

| **元素** | **描述**                 |
|----------|--------------------------|
| 气象站   | 所请求台站的ICAO标识符。 |

### ATIS 请求模式

ATIS 请求模式允许发送 ATIS 请求。如果成功，系统将返回指定机场的最新VATSIM ATIS。

![ATIS REQUEST Mode Image](media/f558ece15a7936f5f2403f9dbcc764bc.png)

| **元素** | **描述**                 |
|----------|--------------------------|
| 台站     | 所请求台站的ICAO标识符。 |

### ATC窗口

ATC 窗口有助于发送给 ATC 的消息，例如登录/登出CPDLC、申请DCL 和 CPDLC 请求以及位置报告。ATC 窗口具有几种独特的操作模式，具体取决于要发送的消息类型。

![ATC Window Image](media/41d39767106cecc5eb85729089df82cb.png)

| **元素**       | **功能**                                                                                                                        |
|----------------|---------------------------------------------------------------------------------------------------------------------------------|
| “消息操作”面板 | “消息操作”面板有助于编辑消息。它将显示一个可编辑的模板，具体取决于窗口所处的操作模式。                                          |
| REQ PDC        | 将消息操作面板更改为 [DCL 模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#pdc-mode)。                     |
| LOGON          | 将消息操作面板更改为[CPDLC模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#connection-manage-mode).        |
| REQUEST        | 打开“REQUEST”子菜单以选择特定的[请求模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#the-request-submenu). |
| REPORT         | 将“消息操作”面板更改为[“REPORT”模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#report-mode)。             |
| CLEAR          | 清空消息面板。                                                                                                                  |
| SEND           | 发送消息。                                                                                                                      |

此外，所有操作模式都包含一个公共字段。

| **元素**  | **描述**                                                                                                                                                                           |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RECIPIENT | 预期收件人的标识符。如果在 PDC 模式下，此字段将自动预填充出发机场，或在所有其他模式下使用控制 ATSU（如果存在）自动预填充。它只能在 PDC 模式下或不存在 CPDLC 连接的情况下进行编辑。 |

### “REQUEST”子菜单

“REQUEST”子菜单列出了“消息操作”面板的几个子模式。

| **元素**     | **功能**                                                                                                         |
|--------------|------------------------------------------------------------------------------------------------------------------|
| DIRECT       | 将消息操作面板更改为[DIRECT模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#direct-mode)。  |
| LEVEL        | 将消息操作面板更改为[LEVEL模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#direct-mode).。  |
| SPEED        | 将消息操作面板更改为[SPEED模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#direct-mode)。   |
| WHEN CAN WE? | 将消息操作面板更改为[ENQUIRE模式](https://github.com/josh-seagrave/EasyCPDLC/wiki/Using-EasyCPDLC#direct-mode)。 |

### DIRECT 模式

直接模式有助于发送直接发送到的请求。此消息的格式如下所示。大括号之间的元素可由用户编辑。

请求直接到 {航点} {原因}

可以通过勾选“DUE TO WX（由于天气）”或“DUE TO A/C PERFORMANCE（由于空调性能）”框来选择“原因”字段。如果指定了有效的 Simbrief Pilot ID，EasyCPDLC 会生成航点列表。更改 WAYPOINT 字段时，会将文本与此列表进行比较。如果找到匹配的航点，EasyCPDLC 将使用该航点预填充 WAYPOINT 字段。

### LEVEL 模式

LEVEL 模式有助于发送高度更改请求。此消息的格式如下所示。大括号之间的元素可由用户编辑。

请求 FL{巡航高度} {原因}

可以通过勾选“DUE TO WX”或“DUE TO A/C PERFORMANCE”框来选择“原因”字段。

### SPEED 模式

速度模式有助于发送速度更改请求。速度模式有 2 个额外的子模式，马赫或表速，具体取决于用户的打算。可以通过根据需要选择马赫或IAS（表速）来更改此子模式。在撰写本文时，由于Hoppie网络的限制，马赫速度的最高限制是M0.99。此消息的格式如下所示。大括号之间的元素可由用户编辑。

REQUEST MACH: M{MACH NUMBER} {REASON}

或

REQUEST SPEED: {SPEED}KTS {REASON}

可以通过勾选“DUE TO WX”或“DUE TO A/C PERFORMANCE”框来选择“原因”字段。

### ENQUIRE 模式

查询模式有助于向当前 ATSU 发送查询指令。此消息的格式如下所示。大括号之间的元素可由用户编辑。

我们什么时候可以进行{请求}？

由于查询的性质，“请求”字段存在多个选项。可以通过勾选相应的框和改变输入的细节来选择所需的模式，如前所述。

## ADS-C集成与EasyCPDLC

### ADS-C是什么

协议式自动相关监视 （ADS-C） 是飞机与 ATSU 和调度员之间的一种数据共享方法，它以规则所定义的速率生成和发送数据包。由于它们是全自动的，飞行员不会意识到传输正在发生，只有在失败时才会意识到。

### EasyCPDLC 和 ADS-C

如果EasyCPDLC有有效的Simbrief和飞行模拟器连接，EasyCPDLC将处理并响应ADS-C请求

## 实操：使用EasyCPDLC申请DCL

**请你自己按照上方的所学内容，在支持DCL的机场申请一次DCL放行。**

**至此，你已经掌握了EasyCPDLC的基础使用方法了。**

**感谢您的阅读！**
