---
title: 签署文件
linktitle: 签署文件
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 对 Word 文档进行数字签名。
type: docs
weight: 10
url: /zh/net/programming-with-digital-signatures/sign-document/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 的文档签名功能的步骤。此功能允许您使用证书对 Word 文档进行数字签名。请按照以下步骤操作：

## 第1步：加载证书

首先使用 CertificateHolder 类加载签名证书：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

请务必指定证书和关联密码的正确路径。

## 第 2 步：签署文件

使用 DigitalSignatureUtil 类对文档进行签名：

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

请务必指定源文档和签名文档的正确路径。

### 使用 Aspose.Words for .NET 签署文档的示例源代码

以下是使用 Aspose.Words for .NET 签署文档的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

通过执行以下步骤，您可以轻松使用 Aspose.Words for .NET 签署 Word 文档。



