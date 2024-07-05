---
title: 使用证书持有者将数字签名添加到 PDF
linktitle: 使用证书持有者将数字签名添加到 PDF
second_title: Aspose.Words 文档处理 API
description: 了解如何使用带有 Aspose.Words for .NET 的证书持有者将数字签名添加到 PDF。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 的证书持有者向 PDF 添加数字签名的步骤。数字签名为 PDF 文档增加了一层安全性和完整性。请按照以下步骤操作：

## 步骤 1：创建文档并添加内容

首先创建 Document 类的实例：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：向文档添加内容

然后使用`DocumentBuilder`向文档添加内容。例如，要添加包含文本“测试签名 PDF”的段落，请使用`Writeln`方法：

```csharp
builder.Writeln("Test Signed PDF.");
```

您可以根据需要添加其他内容项。

## 步骤 3：设置 PDF 保存选项

创建 PdfSaveOptions 类的实例并指定数字签名详细信息：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

请务必指定证书的正确路径和相关密码。您还可以自定义签名原因和位置。

## 步骤 4：将文档保存为数字签名的 PDF

使用`Save`通过指定保存选项将文档保存为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

确保指定正确的路径来保存数字签名的 PDF。

通过遵循这些步骤，您可以使用 Aspose.Words for .NET 轻松创建带有证书的数字签名的 PDF。

### 使用 Aspose.Words for .NET 的证书持有者进行数字签名的 PDF 的示例源代码

以下是使用 Aspose.Words for .NET 从文档中使用证书持有者对 PDF 进行数字签名的完整源代码：

```csharp

            //文档目录的路径。
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## 结论

在本教程中，我们探索了使用 Aspose.Words for .NET 证书向 PDF 文档添加数字签名的步骤。数字签名为文档增加了一层安全性和完整性，从而保证了其真实性并可以检测到任何后续修改。按照给定的步骤，您可以轻松使用 Aspose.Words for .NET 证书创建数字签名的 PDF。

### 经常问的问题

#### 问：什么是数字签名？为什么它在 PDF 文档中很重要？
答：数字签名是一种安全技术，有助于确保电子文档（如 PDF 文件）的真实性、完整性和不可否认性。它使用数字证书为文档添加一层安全性，有助于验证作者的身份并检测对内容的任何后续更改。

#### 问：如何使用 Aspose.Words for .NET 的证书向 PDF 文档添加数字签名？
答：要使用 Aspose.Words for .NET 的证书向 PDF 文档添加数字签名，请按照以下步骤操作：

创建一个实例`Document`类来表示文档。

使用`DocumentBuilder`类来将所需内容添加到文档中。

创建一个实例`PdfSaveOptions`类并使用指定数字签名详细信息`PdfDigitalSignatureDetails`类。您需要提供证书的路径（`CertificateHolder.Create`)、关联密码以及签名原因和位置。

使用`Save`方法将文档保存为 PDF 格式，并指定保存选项。

#### 问：如何获取证书以便为 PDF 文档添加数字签名？
答：要获取证书以向 PDF 文档添加数字签名，通常可以联系证书颁发机构 (CA) 或信任服务提供商。这些实体在验证您的身份并确认您的请求后颁发数字证书。获得证书后，您可以在应用程序中使用它向 PDF 文档添加数字签名。

#### 问：是否可以自定义数字签名的详细信息，例如原因和位置？
答：是的，您可以通过指定签名的原因和位置来自定义数字签名详细信息。在提供的示例代码中，您可以修改`reason`和`location`创建时的参数`PdfDigitalSignatureDetails`对象。请确保为每个参数提供适当的信息，以反映 PDF 文档中签名的原因和位置。