---
title: 加载语言的连字词典
linktitle: 加载语言的连字词典
second_title: Aspose.Words 文档处理 API
description: 了解如何在 Aspose.Words for .NET 中加载特定语言的连字词典。
type: docs
weight: 10
url: /zh/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

在本分步教程中，我们将向您展示如何将特定语言的连字词典加载到 Aspose.Words for .NET 中。我们将解释提供的 C# 源代码并向您展示如何在您自己的项目中实现它。

首先，请确保已在开发环境中安装并配置了 Aspose.Words for .NET。如果尚未安装，请从以下位置下载并安装该库[Aspose.发布]https://releases.aspose.com/words/net/。

## 步骤 1：加载文档

首先，从指定目录加载您的文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 第 2 步：加载连字词典

接下来，打开连字词典文件流并将其保存为所需语言。在此示例中，我们加载瑞士德语 (de-CH) 词典：

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

确保您的数据目录中有适当的字典文件。

## 步骤3：保存修改后的文档

最后保存修改后的文档：

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

所以！您已成功在 Aspose.Words for .NET 中加载了特定语言的连字词典。

### 使用 Aspose.Words for .NET 加载语言连字词典的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

请随意在您自己的项目中使用此代码并进行修改以满足您的特定需求。

### 常见问题解答

#### 问：如何在 Aspose.Words 中加载特定语言的音节词典？

答：要在 Aspose.Words 中加载特定语言的音节词典，您可以使用`Hyphenation`类和`LoadDictionary()`方法。创建`Hyphenation`类并调用`LoadDictionary()`方法指定所需语言的音节词典文件的路径。这会将音节词典加载到 Aspose.Words 中。

#### 问：哪里可以找到不同语言的音节词典文件？

答：您可以在各种在线资源上找到不同语言的音节化词典文件。这些文件通常为 XML 或 TEX 格式。您可以在专门用于语言学项目或源代码存储库的网站上找到不同语言的开源音节化词典。

#### 问：如何将加载的音节词典应用到 Aspose.Words 中的文档？

答：要将加载的音节化词典应用于 Aspose.Words 中的文档，您需要遍历文档中的单词并使用`Hyphenate()`方法`Hyphenation`类来获取单词的音节。然后，您可以根据需要格式化音节化的单词，例如在音节之间添加连字符。

#### 问：Aspose.Words 支持哪些语言的音节划分？

答：Aspose.Words 支持多种语言的音节划分，包括英语、法语、西班牙语、德语、意大利语、荷兰语、俄语、葡萄牙语、瑞典语、挪威语、丹麦语、芬兰语、波兰语、捷克语等。请查看 Aspose.Words 文档，了解支持音节划分的语言的完整列表。