---
title: 加入日語作為編輯語言
linktitle: 加入日語作為編輯語言
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 新增日文作為編輯語言的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

在本教學中，我們將逐步帶您了解並實作使用 Aspose.Words for .NET 新增日文作為編輯語言的功能。此功能可讓您在載入文件時設定語言首選項，並新增日文作為編輯語言。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：載入文檔

在此步驟中，我們將載入不包含預設編輯語言且要新增日文的 Word 文件。使用以下程式碼載入文件：

```csharp
LoadOptions loadOptions = new LoadOptions();

//設定載入文件時將使用的語言首選項。
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## 步驟 3：檢查預設語言

載入文件後，我們將檢查預設編輯語言是否已正確設定為日文。使用以下程式碼取得遠東語言ID：

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

代碼檢查遠東語言 ID 是否與日語相符。根據結果，顯示相應的訊息。

### 使用 Aspose.Words for .NET 新增日文作為編輯語言的範例原始碼

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	//設定載入文件時將使用的語言首選項。
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

