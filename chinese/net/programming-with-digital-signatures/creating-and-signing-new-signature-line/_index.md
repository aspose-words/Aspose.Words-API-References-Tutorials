---
title: 创建并签署新的签名行
linktitle: 创建并签署新的签名行
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建和签署新的签名行。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 创建和签署新签名行功能的步骤。此功能允许您在 Word 文档中插入签名行，设置自定义选项并签署文档。请按照以下步骤操作：

## 第 1 步：创建文档和生成器

首先创建一个 Document 类的实例和一个 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入签名行

使用 DocumentBuilder 对象的 InsertSignatureLine() 方法将新的签名行插入到文档中：

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 第 3 步：保存文档

保存修改后的文档：

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

请务必指定正确的路径和文件名以保存文档。

## 第 4 步：签署文件

要签署文档，您需要设置签名选项并使用 DigitalSignatureUtil 类：

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

请务必为文档、签名行图像和签名文档指定正确的路径。

### 使用 Aspose.Words for .NET 创建和签署新签名行的示例源代码

以下是使用 Aspose.Words for .NET 创建和签署新签名行的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

通过执行这些步骤，您将能够使用 Aspose.Words for .NET 在您的 Word 文档中轻松创建和签署新的签名行。

