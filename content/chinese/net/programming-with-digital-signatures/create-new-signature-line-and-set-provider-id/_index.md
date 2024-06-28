---
title: 创建新签名行并设置提供商 ID
linktitle: 创建新签名行并设置提供商 ID
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建新的签名行并设置提供商 ID。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
在本教程中，我们将引导您完成通过 Aspose.Words for .NET 使用“创建新签名行”和“设置提供商 ID”功能的步骤。此功能允许您在 Word 文档中插入签名行、设置自定义选项并签署文档。请按照以下步骤操作：

## 第 1 步：创建文档和生成器

首先创建 Document 类的实例和 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：设置签名行选项

创建 SignatureLineOptions 类的实例并设置所需的选项：

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## 步骤 3：插入签名行

使用 DocumentBuilder 对象的 InsertSignatureLine() 方法将签名行插入到文档中：

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## 第 4 步：设置提供商 ID

使用 ProviderId 属性设置签名行的提供者 ID：

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

请务必为您的用例指定正确的提供商 ID。

## 第 5 步：保存文档

保存修改后的文档：

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

请务必指定正确的路径和文件名来保存文档。

## 第 6 步：签署文件

要签署文档，您需要设置签名选项并使用 DigitalSignatureUtil 类：

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

请务必指定文档、证书和签名文档的正确路径。

### 使用 Aspose.Words for .NET 创建新签名行并设置提供商 ID 的示例源代码

以下是创建新签名行并使用 Aspose.Words for .NET 设置提供程序 ID 的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

通过执行这些步骤，您可以使用 Aspose.Words for .NET 轻松创建新的签名行并在 Word 文档中设置提供商 ID。

## 结论

在本教程中，我们探索了使用 Aspose.Words for .NET 在 Word 文档中创建新签名行和设置提供者 ID 的功能。通过按照提供的步骤操作，您可以轻松插入带有自定义选项的签名行，并使用提供商 ID 将其与特定提供商关联。添加签名行和自定义提供商信息可以增强文档的真实性和可信度。 Aspose.Words for .NET 为 Word 文档中的签名行和数字证书提供了强大的文字处理 API，使您能够自动化签名过程并确保文档的有效性。

### 常见问题解答

#### 问：签名行中的提供商 ID 是什么？

答：签名行中的提供商 ID 是代表数字签名提供商的唯一标识符。它有助于识别负责签名的来源或组织。

#### 问：如何使用 Aspose.Words for .NET 在 Word 文档中创建新的签名行？

答：要使用 Aspose.Words for .NET 在 Word 文档中创建新的签名行，您可以按照以下步骤操作：
1. 创建一个实例`Document`类和一个`DocumentBuilder`目的。
2. 创建一个实例`SignatureLineOptions`类并设置所需的签名行选项。
3. 使用`InsertSignatureLine`的方法`DocumentBuilder`对象将签名行插入到文档中。

#### 问：我可以自定义签名行的选项，例如签名者姓名、标题和说明吗？

 A：是的，您可以自定义签名行的选项。这`SignatureLineOptions`类提供属性来设置所需的选项，例如`Signer`, `SignerTitle`, `Instructions`, `AllowComments`等。您可以在插入签名行之前修改这些属性。

#### 问：为签名行设置提供商 ID 的目的是什么？

答：为签名行设置提供商 ID 有助于识别负责数字签名的来源或组织。它允许您将签名与特定的提供商或实体关联起来，提供有关签名的来源和可信度的附加信息。

#### 问：如何使用 Aspose.Words for .NET 设置签名行的提供者 ID？

答：要使用 Aspose.Words for .NET 设置签名行的提供者 ID，您可以按照以下步骤操作：
1. 插入签名行后，访问`ProviderId`的财产`SignatureLine`目的。
2. 设置`ProviderId`使用以下方法将属性设置为所需的提供者 ID 值`Guid`数据类型。

#### 问：创建新签名行并设置提供商 ID 后可以签署文档吗？

答：是的，创建新的签名行并设置提供商 ID 后，您就可以签署文档。要签署文档，您需要设置签名选项，包括签名行ID、提供者ID、注释和签名时间。然后，使用`DigitalSignatureUtil.Sign`使用数字证书对文档进行签名的方法。

#### 问：我可以为 Word 文档中的每个签名行指定特定的提供者 ID 吗？

答：是的，您可以为 Word 文档中的每个签名行指定特定的提供商 ID。插入每个签名行后，您可以通过访问设置该特定签名行的提供商 ID`ProviderId`各自的财产`SignatureLine`目的。

#### 问：创建新的签名行并设置提供商 ID 后如何保存修改后的文档？

答：创建新的签名行并设置提供商 ID 后，要保存修改后的文档，可以使用`Save`的方法`Document`目的。指定保存文档的正确路径和文件名。

#### 问：Aspose.Words for .NET 支持什么文件格式来创建和签名签名行？

答：Aspose.Words for .NET 支持以 DOCX 文件格式创建和签名签名行。您可以使用提供的方法和类在 DOCX 文件中创建和签署签名行。

#### 问：签署后我可以修改签名行的提供商 ID 或其他选项吗？

答：签名行一旦签署，就成为文档内容的一部分，不能单独修改。对签名行的任何修改（例如更改提供者 ID 或其他选项）都需要删除现有签名并创建新签名行。