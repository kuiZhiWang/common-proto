[TOC]

## 规范
- proto文件只增不减
- proto文件的接口只增不减
- proto文件的message字段只增不减
- proto文件中的message字段类型和序号不得修改


## 常识
Google的Protocol Buffers (protobuf) 提供了一些预定义的消息类型，
这些类型被广泛用于各种协议和服务中，以提供一致的接口和数据结构。
这些预定义的类型包含在google/protobuf目录下的.proto文件中。
有以下一些常用的预定义消息类型：
1. google.protobuf.Any

用于包装任意类型的消息。Any包含一个类型URL（用于标识包装的消息类型）和字节串（包装的消息的序列化形式）。
2. google.protobuf.Empty

用于表示空消息。Empty通常用于表示不包含任何字段的消息。类似json：`{}`
4. google.protobuf.Timestamp

表示一个时间点，精确到纳秒。Timestamp用于表示自UNIX纪元（1970年1月1日UTC）以来经过的秒数和纳秒数。
3. google.protobuf.Duration

表示一段时间长度，以秒和纳秒为单位。Duration用于表示时间间隔。
4. google.protobuf.Struct

提供了一种灵活的数据结构来表示JSON-like的数据。Struct包含一个字段映射，每个字段都是google.protobuf.Value。
5. google.protobuf.Value

是Struct的一部分，可以表示不同类型的值（包括null、number、string、bool、struct和list）。Value用于构建复杂的、动态的数据结构。
6. google.protobuf.ListValue

用于表示值的列表。ListValue是Value的数组。
7. google.protobuf.NullValue

枚举类型，表示null值。通常用在google.protobuf.Value中。
8. google.protobuf.FieldMask

用于指定一组字段，通常用于指示哪些字段应该被修改或返回。FieldMask在API中用于部分更新资源或选择性地读取资源的特定字段。
9. google.protobuf.DoubleValue, FloatValue, Int64Value, UInt64Value, Int32Value, UInt32Value, BoolValue, StringValue, BytesValue

这些是包装基本数据类型的消息类型，允许将基本类型作为可选字段使用，提供了一种方式来处理基本类型的值和null。