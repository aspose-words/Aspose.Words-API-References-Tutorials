---
title: 添加日语作为编辑语言
linktitle: 添加日语作为编辑语言
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 添加日语作为编辑语言的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

在本教程中，我们将逐步带您了解并实现使用 Aspose.Words for .NET 添加日语作为编辑语言的功能。此功能允许您在加载文档时设置语言首选项，并添加日语作为编辑语言。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：加载文档

在此步骤中，我们将加载不包含默认编辑语言且要添加日语的 Word 文档。使用以下代码加载文档：

```csharp
LoadOptions loadOptions = new LoadOptions();

//设置加载文档时将使用的语言首选项。
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## 步骤 3：检查默认语言

加载文档后，我们将检查默认编辑语言是否已正确设置为日语。使用以下代码获取远东语言ID：

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

该代码检查远东语言 ID 是否与日语匹配。根据结果，显示相应的消息。

### 使用 Aspose.Words for .NET 添加日语作为编辑语言的示例源代码

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	//设置加载文档时将使用的语言首选项。
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

