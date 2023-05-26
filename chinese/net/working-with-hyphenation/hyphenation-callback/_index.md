---
title: 断字回调
linktitle: 断字回调
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中使用断字回调来处理单词断字。
type: docs
weight: 10
url: /zh/net/working-with-hyphenation/hyphenation-callback/
---

在这个循序渐进的教程中，我们将向您展示如何在 Aspose.Words for .NET 中使用断字回调功能。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实施它。

要开始，请确保您已在开发环境中安装并配置了 Aspose.Words for .NET。如果您还没有，请从官方网站下载并安装该库。

## 第 1 步：保存断字提醒

首先，我们将使用自定义注册断字回调`CustomHyphenationCallback`班级。这将允许我们根据自己的规则处理单词断字：

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

确保你已经实施了`CustomHyphenationCallback`根据您的具体需要分类。

## 第 2 步：加载文档并应用断字

接下来，从指定目录加载文档并使用 Aspose.Words 将单词连字符：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## 第 3 步：处理丢失的字典错误

如果缺少断字字典，我们将捕获相应的异常并显示一条错误消息：

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## 第 4 步：清理和禁用断字提醒

最后，为了清洁和关闭断字提醒，请执行以下步骤：

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

这会在完成处理后清理并禁用断字提醒。

所以 ！您已在 Aspose.Words for .NET 中成功使用断字回调。

### 使用 Aspose.Words for .NET 的断字回调示例源代码

```csharp
try
{
	 //注册断字回调。
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

随意在您自己的项目中使用此代码并修改它以满足您的特定需求。