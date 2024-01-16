---
title: 將俄語設定為預設編輯語言
linktitle: 將俄語設定為預設編輯語言
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 將俄語設定為文件的預設編輯語言的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以使用 Aspose.Words for .NET 將俄語設定為預設編輯語言。此功能可讓您設定載入文件時的預設語言。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入要將俄語設定為預設編輯語言的 Word 文件。使用以下程式碼載入文件：

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

代替`"YOUR DOCUMENTS DIRECTORY"`與文件所在目錄的實際路徑。

## 步驟 3：檢查預設語言

上傳文件後，我們將檢查預設語言是否已正確設定為俄語。使用以下程式碼取得預設語言 ID：

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

此代碼檢查語言 ID 是否與俄語相符。根據結果，顯示相應的訊息。

### 使用 Aspose.Words for .NET 將俄語設定為預設編輯語言的範例原始碼

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

請務必在中指定正確的文件路徑`dataDir`多變的。

現在您已經了解如何使用 Aspose.Words for .NET 將俄語設定為文件的預設編輯語言。請依照步驟指南進行操作