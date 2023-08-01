get service such as
- getting stack quotes
- send emails and SMS's
- interact with social media
- etc.

From ESP32 to wifi <br>
![transport data](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/transport%20data.png) <br>
Data structure <br>
![data composition](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/data%20composition.png) <br>
json structure <br>
![json](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/json.png) <br>
Develop API <br>
![develop API](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/rest%20API.png) <br>



# Words
- curl 卷曲的
- semicolon 分号
- JSON（JavaScript Object Notation）：一种轻量级的数据交换格式，用于在不同系统之间传输和存储数据。它基于JavaScript语言的对象字面量表示法，但已成为一种通用的数据格式，被广泛应用于Web开发和其他领域。<br>

JSON使用键值对的方式来组织数据，数据由键（属性名）和对应的值（属性值）组成，键和值之间用冒号分隔，多个键值对之间用逗号分隔。<br>

JSON支持以下数据类型：<br>
1. **对象（Object）：** 由一组键值对组成，使用花括号 `{}` 表示。键是字符串，值可以是字符串、数字、布尔值、数组、嵌套对象等。<br>
2. **数组（Array）：** 由一组值组成，使用方括号 `[]` 表示。值可以是字符串、数字、布尔值、对象、嵌套数组等。<br>
3. **字符串（String）：** 由双引号或单引号括起来的字符序列。<br>
4. **数字（Number）：** 整数或浮点数。<br>
5. **布尔值（Boolean）：** 表示真或假的值。<br>
6. **null：** 表示空值。<br>

JSON的优点包括：<br>
易于阅读和编写，对开发人员友好。<br>
轻量级，不占用过多的数据传输带宽。<br>
跨平台和语言，支持大多数编程语言。<br>
支持嵌套数据结构，可以表示复杂的数据关系。<br>
与JavaScript语言紧密相关，适用于Web前端开发。<br>
- ampersand 与号
- prolific 多产的
- Representational State Transfer（简称为REST）:用于设计网络应用程序的架构风格和通信协议。它是一种轻量级的、灵活的、简单的设计模式，常用于构建现代的Web服务和API。<br>

REST的设计原则基于以下几个核心概念：<br>
1. **资源（Resources）：** 在REST中，网络上的每个实体都被视为一个资源，例如用户、文章、订单等。资源可以用URI（统一资源标识符）来唯一标识。<br>
2. **状态转移（State Transfer）：** 客户端可以通过HTTP请求（如GET、POST、PUT、DELETE等）来对资源进行状态转移操作，例如获取资源、创建资源、更新资源、删除资源等。<br>
3. **无状态性（Statelessness）：** REST是无状态的，即每个请求都是独立的，服务器不保存客户端请求的状态。客户端的每个请求都应该包含足够的信息，以便服务器理解和处理请求。<br>
4. **表现层（Representation）：** 资源可以有不同的表现形式，比如JSON、XML、HTML等。客户端和服务器之间的通信通过资源的表现层来进行。<br>
5. **链接（Hypermedia）：** REST提倡使用超媒体链接来表示资源之间的关系。这样客户端可以通过链接来发现和访问其他相关资源。<br>
