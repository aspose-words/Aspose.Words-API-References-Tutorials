---
title: Docx 转 Mhtml 并发送邮件
linktitle: Docx 转 Mhtml 并发送邮件
second_title: Aspose.Words for .NET API 参考
description: 了解如何将 Word 文档从 Docx 转换为 MHTML，并使用 Aspose.Words 和 Aspose.Email 将它们作为电子邮件发送。分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 将 Docx 格式的 Word 文档转换为 MHTML，并使用 Aspose.Email 将其作为电子邮件发送。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您在开发环境中安装并设置了 Aspose.Words for .NET 和 Aspose.Email 库。如果您还没有这样做，请从他们的官方网站下载并安装这些库。

## 第 1 步：初始化文档对象

首先，初始化`Document`带有 Docx 格式源文档路径的对象：

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 第 2 步：将文档保存为 MHTML 格式

接下来，将文档保存到`Stream`MHTML 格式的对象：

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## 第 3 步：倒带流

由于 Aspose.Email 需要从头读取流，将流倒回到开头：

```csharp
stream.Position = 0;
```

## 第 4 步：创建 Aspose.Email MIME 消息

创建一个`MailMessage`来自流的对象使用`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

您可以随意自定义邮件属性，例如发件人、收件人和主题。

## 第 5 步：发送电子邮件

使用 Aspose.Email 的`SmtpClient`发送电子邮件：

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

确保提供正确的 SMTP 服务器主机地址。

就是这样！您已成功将 Docx 格式的 Word 文档转换为 MHTML，并使用 Aspose.Words for .NET 和 Aspose.Email 将其作为电子邮件发送。

### Docx 到 Mhtml 和使用 Aspose.Words for .NET 发送电子邮件的示例源代码

```csharp

	//文档 doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//将流倒回到开头以便 Aspose.Email 可以读取它。
	stream.Position = 0;

	//从流中创建一个 Aspose.Email MIME 电子邮件消息。
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	//使用 Aspose.Email 发送消息。
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。