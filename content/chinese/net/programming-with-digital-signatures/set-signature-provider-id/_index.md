---
title: 在 Word 文档中设置签名提供者 ID
linktitle: 在 Word 文档中设置签名提供者 ID
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置签名提供商 ID。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/set-signature-provider-id/
---
在本教程中，我们将引导您完成使用 Aspose.Words for .NET 的“设置签名提供商 ID”功能的步骤。此功能允许您为 Word 文档中的签名行指定签名提供商 ID。请按照以下步骤操作：

## 步骤 1：加载文档并访问签名行

首先上传包含签名行的文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 步骤 2：设置签名选项

创建 SignOptions 类的实例并设置签名选项，包括提供者 ID：

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## 步骤 3：签署文件

要签署文档，您必须使用 DigitalSignatureUtil 类并指定签名证书：

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

确保为文档、证书和签名文档指定正确的路径。

### 使用 Aspose.Words for .NET 设置签名提供商 ID 的示例源代码

以下是使用 Aspose.Words for .NET 设置签名提供商 ID 的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

使用 Aspose.Words for .NET 完成 Word 文档中的签名提供商 ID。


## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 为 Word 文档中的签名行设置签名提供商 ID。按照提供的步骤，您可以轻松加载文档、访问签名行、设置提供商 ID 并签署文档。设置签名提供商 ID 的能力有助于确定签名者的身份和可信度，从而增强 Word 文档的安全性和完整性。Aspose.Words for .NET 为带有数字签名的文字处理提供了强大的 API，使您可以轻松自定义和管理签名过程。

### 在 Word 文档中设置签名提供者 ID 的常见问题解答

#### 问：Word 文档中的签名提供商 ID 是什么？

答：Word 文档中的签名提供商 ID 是指定数字签名提供商的唯一标识符。它有助于识别负责创建和管理数字签名的实体或组织。

#### 问：如何使用 Aspose.Words for .NET 设置 Word 文档中签名行的签名提供商 ID？

答：要使用 Aspose.Words for .NET 设置 Word 文档中签名行的签名提供商 ID，您可以按照以下步骤操作：
1. 使用加载文档`Document`类并指定文档文件的路径。
2. 使用适当的方法或属性访问签名行。例如，您可以使用`GetChild`方法来检索签名线形状。
3. 从签名行中检索提供商 ID。
4. 创建一个实例`SignOptions`类并设置`ProviderId`属性添加到检索到的提供商 ID。
5. 使用`DigitalSignatureUtil.Sign`方法签署文件，提供必要的参数，包括`SignOptions`目的。

#### 问：如何使用 Aspose.Words for .NET 访问 Word 文档中的签名行？

答：要使用 Aspose.Words for .NET 访问 Word 文档中的签名行，您可以使用适当的方法或属性从文档结构中检索签名行形状。例如，您可以使用`GetChild`方法并使用适当的参数来获得所需的签名线形状。

#### 问：我可以为 Word 文档中的多行签名设置签名提供者 ID 吗？

答：是的，您可以为 Word 文档中的多个签名行设置签名提供商 ID。您可以遍历文档中的签名行集合，并使用`SignOptions.ProviderId`财产。

#### 问：Word 文档中的签名提供商 ID 有什么用途？

答：Word 文档中的签名提供商 ID 用于识别负责创建和管理数字签名的实体或组织。它通过将数字签名与特定提供商关联，帮助确定数字签名的真实性和可信度。

#### 问：哪种类型的数字证书可用于设置 Word 文档中的签名提供者 ID？

答：您可以使用包含适当提供商信息的 X.509 数字证书在 Word 文档中设置签名提供商 ID。数字证书应由受信任的证书颁发机构 (CA) 颁发，并包含识别提供商所需的元数据。