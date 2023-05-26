---
title: 使用证书持有者对 PDF 进行数字签名
linktitle: 使用证书持有者对 PDF 进行数字签名
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用带有 Aspose.Words for .NET 的证书持有者对 PDF 进行数字签名。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 证书创建数字签名 PDF 的步骤。数字签名为 PDF 文档增加了一层安全性和完整性。请按照以下步骤操作：

## 第 1 步：创建文档并添加内容

首先创建 Document 类的实例：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：向文档添加内容

然后使用`DocumentBuilder`向文档添加内容。例如，要添加包含文本“Test Signed PDF”的段落，请使用`Writeln`方法：

```csharp
builder.Writeln("Test Signed PDF.");
```

您可以根据需要添加其他内容项。

## 第 3 步：设置 PDF 保存选项

创建 PdfSaveOptions 类的实例并指定数字签名详细信息：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

请务必指定证书和关联密码的正确路径。您还可以自定义签名原因和位置。

## 第 4 步：将文档另存为数字签名的 PDF

使用`Save`通过指定保存选项将文档保存为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

确保指定正确的路径以保存数字签名的 PDF。

按照这些步骤，您可以使用 Aspose.Words for .NET 轻松创建带有证书的数字签名 PDF。

### 使用 Aspose.Words for .NET 使用证书持有者对 Pdf 进行数字签名的示例源代码

以下是使用 Aspose.Words for .NET 使用文档中的证书持有者对 Pdf 进行数字签名的完整源代码：

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
