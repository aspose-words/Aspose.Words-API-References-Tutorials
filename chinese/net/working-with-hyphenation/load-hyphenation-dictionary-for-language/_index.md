---
title: 为语言加载断字词典
linktitle: 为语言加载断字词典
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中加载特定语言的断字词典。
type: docs
weight: 10
url: /zh/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

在这个循序渐进的教程中，我们将向您展示如何将特定语言的断字词典加载到 Aspose.Words for .NET 中。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实施它。

要开始，请确保您已在开发环境中安装并配置了 Aspose.Words for .NET。如果您还没有，请从官方网站下载并安装该库。

## 第 1 步：装入文档

首先，从指定目录加载文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 第 2 步：加载断字字典

接下来，打开断字字典文件的流并将其保存为所需的语言。在此示例中，我们加载了瑞士德语 (de-CH) 的字典：

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

确保您的数据目录中有适当的字典文件。

## 第 3 步：保存修改后的文档

最后，保存修改后的文件：

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

所以 ！您已经成功地在 Aspose.Words for .NET 中加载了特定语言的断字字典。

### 使用 Aspose.Words for .NET 为语言加载断字字典的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

随意在您自己的项目中使用此代码并修改它以满足您的特定需求。