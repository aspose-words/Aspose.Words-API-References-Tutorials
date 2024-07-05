---
title: 将俄语设置为默认编辑语言
linktitle: 将俄语设置为默认编辑语言
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将俄语设置为文档的默认编辑语言的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

在本教程中，我们将引导您完成 C# 源代码，使用 Aspose.Words for .NET 将俄语设置为默认编辑语言。此功能允许您在加载文档时设置默认语言。

## 步骤 1：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 步骤 2：加载文档

在此步骤中，我们将加载要将俄语设置为默认编辑语言的 Word 文档。使用以下代码加载文档：

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

代替`"YOUR DOCUMENTS DIRECTORY"`与文档所在目录的实际路径一致。

## 步骤 3：检查默认语言

上传文档后，我们将检查默认语言是否已正确设置为俄语。使用以下代码获取默认语言 ID：

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

代码检查语言ID是否与俄语匹配。根据结果显示相应的消息。

### 使用 Aspose.Words for .NET 将俄语设置为默认编辑语言的示例源代码

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

确保在`dataDir`多变的。

现在，您已经学会了如何使用 Aspose.Words for .NET 将俄语设置为文档的默认编辑语言。按照步骤指南