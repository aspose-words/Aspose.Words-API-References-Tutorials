---
title: 将 Docx 转换为 Mhtml 并发送电子邮件
linktitle: 将 Docx 转换为 Mhtml 并发送电子邮件
second_title: Aspose.Words 文档处理 API
description: 了解如何将 Word 文档从 Docx 转换为 MHTML，并使用 Aspose.Words 和 Aspose.Email 将其作为电子邮件发送。分步教程。
type: docs
weight: 10
url: /zh/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

在本分步教程中，我们将指导您如何使用 Aspose.Words for .NET 将 Docx 格式的 Word 文档转换为 MHTML，并使用 Aspose.Email 将其作为电子邮件发送。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

首先，请确保您已在开发环境中安装并设置了 Aspose.Words for .NET 和 Aspose.Email 库。如果您还没有这样做，请从其官方网站下载并安装这些库。

## 第 1 步：初始化文档对象

首先，初始化`Document`对象，其中包含 Docx 格式的源文档的路径：

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 步骤 2：将文档保存为 MHTML 格式

接下来，将文档保存到`Stream`MHTML 格式的对象：

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## 第 3 步：倒带流

由于 Aspose.Email 需要从头开始读取流，因此将流倒回到开头：

```csharp
stream.Position = 0;
```

## 步骤 4：创建 Aspose.Email MIME 消息

创建一个`MailMessage`使用流中的对象`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

您可以随意自定义消息属性，例如发件人、收件人和主题。

## 第 5 步：发送电子邮件

使用 Aspose.Email 的`SmtpClient`发送电子邮件：

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

确保您提供正确的 SMTP 服务器主机地址。

就是这样！您已成功将 Docx 格式的 Word 文档转换为 MHTML，并使用 Aspose.Words for .NET 和 Aspose.Email 将其作为电子邮件发送。

### Docx 转 Mhtml 并使用 Aspose.Words for .NET 发送电子邮件的示例源代码

```csharp

	//文档 doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//将流倒回到开头，以便 Aspose.Email 可以读取它。
	stream.Position = 0;

	//从流创建 Aspose.Email MIME 电子邮件。
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	//使用 Aspose.Email 发送消息。
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

请随意在您自己的项目中使用此代码，并根据您的具体要求进行修改。

### 常见问题解答

#### 如何将 DOCX 文件转换为 MHTML？

要将 DOCX 文件转换为 MHTML，您可以使用提供此功能的软件工具或库。 Aspose.Words for .NET 是这种转换的可靠选择。您可以使用库 API 加载 DOCX 文件并将其保存为 MHTML 格式。

#### 如何发送带有 MHTML 文件附件的电子邮件？

要发送带有 MHTML 文件作为附件的电子邮件，您可以使用特定于电子邮件发送的库或工具，例如 .NET 中的 System.Net.Mail。您必须创建电子邮件，指定收件人、主题和内容，然后将 MHTML 文件作为附件添加到邮件中，然后再发送。

#### 电子邮件转换和发送过程有哪些限制？

电子邮件转换和发送过程的限制取决于您使用的特定工具。某些工具可能具有与文件大小、安全设置或支持的电子邮件协议相关的限制。选择适合您需求的工具并在实施时考虑这些限制非常重要。

#### Aspose 是 DOCX 到 MHTML 转换和电子邮件发送的可靠工具吗？

是的，Aspose.Words for .NET 是 DOCX 到 MHTML 转换和电子邮件发送的可靠工具。它因其性能和质量而被开发人员和专业人士广泛使用。该工具提供全面的文档、高级功能和专门的技术支持，使其成为执行这些任务的推荐选择。