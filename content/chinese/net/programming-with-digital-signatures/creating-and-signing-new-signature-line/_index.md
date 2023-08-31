---
title: 创建并签署新的签名行
linktitle: 创建并签署新的签名行
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建和签署新的签名行。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
在本教程中，我们将引导您完成使用 Aspose.Words for .NET 创建和签署新签名行功能的步骤。此功能允许您在 Word 文档中插入签名行、设置自定义选项并签署文档。请按照以下步骤操作：

## 第 1 步：创建文档和生成器

首先创建 Document 类的实例和 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：插入签名行

使用 DocumentBuilder 对象的 InsertSignatureLine() 方法将新签名行插入到文档中：

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 步骤 3：保存文档

保存修改后的文档：

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

请务必指定正确的路径和文件名来保存文档。

## 第四步：签署文件

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

请务必指定文档、签名行图像和签名文档的正确路径。

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

通过执行这些步骤，您将能够使用 Aspose.Words for .NET 在 Word 文档中轻松创建并签署新的签名行。

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档中创建和签署新的签名行。通过按照提供的步骤操作，您可以轻松地将签名行插入到文档中，自定义其选项，并使用数字证书签署文档。在文档中添加签名行和数字签名可以增强其真实性和完整性，使它们更加安全和值得信赖。 Aspose.Words for .NET 为 Word 文档中的签名和数字证书提供了强大的文字处理 API，允许您自动执行签名过程并确保文档的有效性。

### 常见问题解答

#### 问：Word文档中的签名行是什么？

答：Word 文档中的签名行是一个占位符，指示应放置签名的位置。它通常包括姓名、标题和日期，并提供手写或数字签名的空间。

#### 问：如何使用 Aspose.Words for .NET 在 Word 文档中创建签名行？

答：要使用 Aspose.Words for .NET 在 Word 文档中创建签名行，您可以按照以下步骤操作：
1. 创建一个实例`Document`类和一个`DocumentBuilder`目的。
2. 使用`InsertSignatureLine`的方法`DocumentBuilder`对象在文档中插入新的签名行。
3. 保存修改后的文档。

#### 问：我可以自定义签名行选项，例如姓名、标题和日期吗？

答：是的，您可以自定义签名行选项。这`SignatureLineOptions`类提供属性来设置所需的选项，例如`Signer`, `SignerTitle`, `ShowDate`等。您可以在插入签名行之前修改这些属性。

#### 问：创建签名行后如何在文档上签名？

答：要在创建签名行后对文档进行签名，您需要设置签名选项并使用`DigitalSignatureUtil`班级。步骤如下：
1. 设置`SignatureLineId`财产在`SignOptions`反对签名行的 ID。
2. 设置`SignatureLineImage`财产在`SignOptions`反对您要使用的签名图像。
3. 使用加载签名证书`CertificateHolder`班级。
4. 使用`DigitalSignatureUtil.Sign`方法签署文档，提供必要的参数。

#### 问：我可以使用数字签名图像来签署文档吗？

答：是的，您可以使用数字签名图像来签署文档。为此，您需要在`SignOptions`对象使用`SignatureLineImage`财产。图像可以是任何受支持的图像格式，例如 JPEG、PNG 或 EMF。

#### 问：在 Word 文档中创建并签署新签名行的目的是什么？

答：使用 Aspose.Words for .NET 在 Word 文档中创建并签署新的签名行允许您添加签名占位符，然后使用数字证书签署文档。此过程确保文件的真实性和完整性，提供批准或协议的证据。

#### 问：我可以使用 Aspose.Words for .NET 在 Word 文档中创建并签署多个签名行吗？

答：是的，您可以使用 Aspose.Words for .NET 在 Word 文档中创建并签署多个签名行。每个签名行可以有自己唯一的 ID 和选项。您可以重复这些步骤以在文档中创建并签署其他签名行。

#### 问：签名后我可以修改签名行或添加其他信息吗？

答：签名行一旦签署，就成为文档内容的一部分，不能单独修改。但是，您可以在签名行后添加其他信息或内容。

#### 问：我可以验证包含签名行的文档的数字签名吗？

答：是的，Aspose.Words for .NET 提供了验证包含签名行的文档的数字签名的功能。您可以使用`DigitalSignatureUtil.Verify`验证数字签名的有效性和真实性的方法。

#### 问：Aspose.Words for .NET 支持什么文件格式来创建和签署签名行？

答：Aspose.Words for .NET 支持以 DOCX 文件格式创建和签署签名行。您可以使用提供的方法和类在 DOCX 文件中创建和签署签名行。