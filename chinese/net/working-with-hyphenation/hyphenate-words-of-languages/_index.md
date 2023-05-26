---
title: 连字语言词
linktitle: 连字语言词
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 为 Word 文档中不同语言的单词连字符。
type: docs
weight: 10
url: /zh/net/working-with-hyphenation/hyphenate-words-of-languages/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 为 Word 文档中的不同语言的单词连字符。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实施它。

要开始，请确保您已在开发环境中安装并配置了 Aspose.Words for .NET。如果您还没有，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，初始化`Document`通过指定包含不同语言文本的源文档的路径来对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 第 2 步：保存断字词典

接下来，保存要处理的不同语言的断字词典。在这个例子中，我们注册了美国英语和瑞士德语的词典：

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

确保您的数据目录中有适当的字典文件。

## 第 3 步：通过断字处理单词

现在您可以使用断字功能来处理不同语言的单词。您可以使用不同的方法`Document`或者`DocumentBuilder`取决于您的具体需求。

```csharp
//示例：使用 DocumentBuilder 的 Hyphenate 方法
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## 第 4 步：保存文档

最后，保存修改后的文件：

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

所以 ！您已经使用 Aspose.Words for .NET 在 Word 文档中以不同的语言对单词进行连字，从而成功地处理了单词。

### 使用 Aspose.Words for .NET 的单词断字示例源代码

	```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "German text.docx");

	Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
	Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

	doc.Save(dataDir + "TreatmentByCesure.pdf");
	```

随意在您自己的项目中使用此代码并修改它以满足您的特定需求。
