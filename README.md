Fork from http://code.google.com/p/protobuf-java-format/

[![Build Status](https://travis-ci.org/bivas/protobuf-java-format.svg?branch=master)](https://travis-ci.org/bivas/protobuf-java-format)

## Description

Provide serialization and de-serialization of different formats based on Google’s protobuf Message. Enables overriding the default (byte array) output to text based formats such as XML, JSON and HTML.

##Example
For XML output, use XmlFormat

```java
Message aMessageObject = MessageClassName.parseFrom(InputStream);
XmlFormat xmlFormat = new XmlFormat();
String asXml = xmlFormat.printToString(aMessageObject);
```

For XML input, use XmlFormat
```java
Message.Builder builder = SomeProto.newBuilder();
String asXml = _load xml document from a source_;
XmlFormat xmlFormat = new XmlFormat();
xmlFormat.merge(asXml, builder);
```

For Json output, use JsonFormat
```java
Message someProto = SomeProto.getDefaultInstance();
JsonFormat jsonFormat = new JsonFormat();
String asJson = jsonFormat.printToString(someProto);
```

For Json input, use JsonFormat
```java
Message.Builder builder = SomeProto.newBuilder();
String asJson = _load json document from a source_;
JsonFormat jsonFormat = new JsonFormat();
jsonFormat.merge(asJson, builder);
```

For HTML output, use HtmlFormat
```java
Message someProto = SomeProto.getDefaultInstance();
HtmlFormat htmlFormat = new HtmlFormat();
String asHtml = htmlFormat.printToString(someProto);
```
