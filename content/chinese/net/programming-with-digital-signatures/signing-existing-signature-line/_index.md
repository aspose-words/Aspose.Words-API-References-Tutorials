---
title: 在 Word 文档中签署现有签名行
linktitle: 在 Word 文档中签署现有签名行
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中签署现有签名行。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/signing-existing-signature-line/
---
在本教程中，我们将引导您完成使用 Aspose.Words for .NET 的现有签名行的签名功能的步骤。此功能允许您对 Word 文档中已有的签名行进行数字签名。请按照以下步骤操作：

## 步骤 1：加载文档并访问签名行

首先上传包含现有签名行的文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 步骤 2：设置签名选项

创建SignOptions类的实例，设置签名选项，包括签名线ID、签名线图像：

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

请确保指定签名行图像的正确路径。

## 步骤3：加载证书

首先使用 CertificationHolder 类加载签名证书：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

请确保指定证书和相关密码的正确路径。

## 步骤 4：签署现有签名行

使用 DigitalSignatureUtil 类对现有的签名行进行签名：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

确保为源文档、签名文档和证书指定正确的路径。

### 使用 Aspose.Words for .NET 签署现有签名行的示例源代码

以下是使用 Aspose.Words for .NET 对现有签名行进行签名的完整源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

通过遵循这些步骤，您可以使用 Aspose.Words for .NET 轻松地在 Word 文档中签署现有的签名行。

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档中签署现有签名行。按照提供的步骤，您可以轻松加载文档、访问现有签名行、设置签名选项并签署文档。签署现有签名行的功能提供了一种方便的方法，可以将数字签名添加到 Word 文档中的预定义区域，从而确保文档的完整性和身份验证。Aspose.Words for .NET 提供了一个强大的带有数字签名的文字处理 API，允许您自定义签名过程并增强 Word 文档的安全性。

### 常见问题解答

#### 问：Word 文档中现有的签名行是什么？

答：Word 文档中的现有签名行是可以放置签名的预定义区域。它通常由文档中的形状或对象表示，并作为签名者添加数字签名的指定空间。

#### 问：如何使用 Aspose.Words for .NET 在 Word 文档中签署现有的签名行？

答：要使用 Aspose.Words for .NET 在 Word 文档中签署现有签名行，您可以按照以下步骤操作：
1. 使用加载文档`Document`类并指定文档文件的路径。
2. 使用适当的方法或属性访问现有签名行。例如，您可以使用`GetChild`方法来检索签名线形状。
3. 创建一个实例`SignOptions`类并设置`SignatureLineId`属性添加到现有签名行的 ID。
4. 设置`SignatureLineImage`的财产`SignOptions`类到代表数字签名的图像。
5. 使用加载签名证书`CertificateHolder`课程并提供必要的证书和密码。
6. 使用`DigitalSignatureUtil.Sign`方法签署文件，提供必要的参数，包括`SignOptions`目的。

#### 问：如何使用 Aspose.Words for .NET 访问 Word 文档中现有的签名行？

答：要使用 Aspose.Words for .NET 访问 Word 文档中的现有签名行，您可以使用适当的方法或属性从文档结构中检索签名行形状。例如，您可以使用`GetChild`方法并使用适当的参数来获得所需的签名线形状。

#### 问：我可以自定义现有签名行中的数字签名的外观吗？

答：是的，您可以通过提供代表签名的图像文件来自定义现有签名行中的数字签名的外观。图像可以是徽标、手写签名或任何其他签名的图形表示。您可以设置`SignatureLineImage`的财产`SignOptions`类到图像文件的字节。

#### 问：我可以在 Word 文档中签署多个现有的签名行吗？
答：是的，您可以在 Word 文档中签署多个现有签名行。您需要分别按照每个签名行的步骤进行操作，设置适当的`SignatureLineId`和`SignatureLineImage`中的值`SignOptions`每个签名行的对象。

#### 问：现有签名行中的数字签名的图像文件应该是什么格式？

答：现有签名行中的数字签名的图像文件可以是多种格式，例如 PNG、JPEG、BMP 或 GIF。您可以指定文件路径或读取图像文件的字节并将其分配给`SignatureLineImage`的财产`SignOptions`班级。
