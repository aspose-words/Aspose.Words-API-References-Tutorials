---
title: 在 Word 文档中签署现有签名行
linktitle: 在 Word 文档中签署现有签名行
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 对 Word 文档中的现有签名行进行签名。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/signing-existing-signature-line/
---
在本教程中，我们将引导您完成通过 Aspose.Words for .NET 使用现有签名行的签名功能的步骤。此功能允许您对 Word 文档中已有的签名行进行数字签名。请按照以下步骤操作：

## 第 1 步：加载文档并访问签名行

首先上传包含现有签名行的文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 第2步：设置签名选项

创建 SignOptions 类的实例并设置签名选项，包括签名行 ID 和签名行图像：

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

请务必指定签名行图像的正确路径。

## 第三步：加载证书

首先使用 CertificateHolder 类加载签名证书：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

请务必指定证书和关联密码的正确路径。

## 第 4 步：签署现有签名行

使用 DigitalSignatureUtil 类对现有签名行进行签名：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

请务必指定源文档、签名文档和证书的正确路径。

### 使用 Aspose.Words for .NET 签署现有签名行的示例源代码

以下是使用 Aspose.Words for .NET 签署现有签名行的完整源代码：


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

通过执行以下步骤，您可以使用 Aspose.Words for .NET 轻松签署 Word 文档中的现有签名行。

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 对 Word 文档中的现有签名行进行签名。通过按照提供的步骤操作，您可以轻松加载文档、访问现有签名行、设置签名选项并签署文档。对现有签名行进行签名的功能提供了一种将数字签名添加到 Word 文档中的预定义区域的便捷方法，从而确保文档的完整性和身份验证。 Aspose.Words for .NET 提供了强大的 API，用于带有数字签名的文字处理，允许您自定义签名过程并增强 Word 文档的安全性。

### 常见问题解答

#### 问：Word 文档中的现有签名行是什么？

答：Word 文档中的现有签名行是可以放置签名的预定义区域。它通常由文档中的形状或对象表示，并用作签名者添加数字签名的指定空间。

#### 问：如何使用 Aspose.Words for .NET 对 Word 文档中的现有签名行进行签名？

答：要使用 Aspose.Words for .NET 在 Word 文档中签署现有签名行，您可以按照以下步骤操作：
1. 使用加载文档`Document`类并指定文档文件的路径。
2. 使用适当的方法或属性访问现有签名行。例如，您可以使用`GetChild`检索签名线形状的方法。
3. 创建一个实例`SignOptions`类并设置`SignatureLineId`属性到现有签名行的 ID。
4. 设置`SignatureLineImage`的财产`SignOptions`代表数字签名的图像的类。
5. 使用加载签名证书`CertificateHolder`类并提供必要的证书和密码。
6. 使用`DigitalSignatureUtil.Sign`方法签署文档，提供必要的参数，包括`SignOptions`目的。

#### 问：如何使用 Aspose.Words for .NET 访问 Word 文档中的现有签名行？

答：要使用 Aspose.Words for .NET 访问 Word 文档中现有的签名行，您可以使用适当的方法或属性从文档结构中检索签名行形状。例如，您可以使用`GetChild`方法与适当的参数来获得所需的签名线形状。

#### 问：我可以在现有签名行中自定义数字签名的外观吗？

答：是的，您可以通过提供代表签名的图像文件来自定义现有签名行中数字签名的外观。该图像可以是徽标、手写签名或签名的任何其他图形表示。您可以设置`SignatureLineImage`的财产`SignOptions`类到图像文件的字节。

#### 问：我可以在 Word 文档中签署多个现有签名行吗？
答：是的，您可以在 Word 文档中签署多个现有签名行。您需要单独按照每个签名行的步骤进行操作，设置适当的`SignatureLineId`和`SignatureLineImage`中的值`SignOptions`每个签名行的对象。

#### 问：现有签名行中的数字签名的图像文件应采用什么格式？

答：现有签名行中的数字签名的图像文件可以是多种格式，例如PNG、JPEG、BMP或GIF。您可以指定文件路径或读取图像文件的字节并将其分配给`SignatureLineImage`的财产`SignOptions`班级。
