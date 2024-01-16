---
title: Word 文件中的首選控制項類型
linktitle: Word 文件中的首選控制項類型
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 載入 HTML 文件時在 Word 文件中指定首選控制項類型的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-htmlloadoptions/preferred-control-type/
---
本文提供了有關如何將首選控制項類型功能與 Aspose.Words for .NET 結合使用的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學課程結束時，您將能夠了解如何在載入 HTML 文件時指定首選控制項類型。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 第 1 步：定義 HTML 程式碼

首先，您需要定義要作為文件載入的 HTML 程式碼。在這個例子中，我們定義了一個`html`包含帶有選項的選擇器的 HTML 程式碼的變數。

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## 第 2 步：設定 HTML 載入選項

接下來，我們創建一個`HtmlLoadOptions`對象並設定`PreferredControlType`財產給`HtmlControlType.StructuredDocumentTag`。這告訴 Aspose.Words 在載入時使用 StructuredDocumentTags 來表示 HTML。

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## 步驟 3：載入並儲存文檔

我們使用`Document`類，使用先前定義的載入選項從記憶體流載入 HTML 程式碼。然後我們將文檔保存在指定目錄中`.docx`文件格式。

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### 使用 Aspose.Words for .NET 的首選控制項類型的範例原始程式碼

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

就這樣 ！使用 Aspose.Words for .NET 載入 HTML 文件時，您已成功指定首選控制項類型。

## 結論

透過遵循本逐步指南，您已經了解如何在載入 HTML 文件時使用 Aspose.Words for .NET 中的「首選控制項類型」功能來指定所需的控制項類型。設定`PreferredControlType`財產給`HtmlControlType.StructuredDocumentTag`允許 Aspose.Words 使用 StructuredDocumentTags (SDT) 更好地表示和處理 HTML 內容。您也可以探索其他控制類型以滿足您的特定要求。使用此功能有助於確保使用 Aspose.Words 在 C# 應用程式中準確、有效率地處理 HTML 文件。

### Word 文件中首選控制項類型的常見問題解答

#### Q：Aspose.Words for .NET 中的「首選控制項類型」功能是什麼？

答：「首選控制項類型」功能可讓您在載入 HTML 文件時指定表示 HTML 元素的首選控制項類型。它有助於選擇適當的控制類型，以便更好地表示和處理 HTML 內容。

#### Q：如何設定載入 HTML 文件時首選的控制項類型？

 A：要設定首選控制項類型，您需要建立一個`HtmlLoadOptions`對象並設定其`PreferredControlType`屬性到想要的`HtmlControlType`。在提供的範例中，`HtmlControlType.StructuredDocumentTag`用來。

#### Q：使用 StructuredDocumentTags (SDT) 作為首選控制類型有何意義？

答：StructuredDocumentTags (SDT) 是基於 XML 的元素，可用來表示 Word 文件中的複雜內容和控制項。使用 SDT 作為首選控制項類型可以提供更好的相容性和 HTML 內容的表示。

#### Q：如何確保 Aspose.Words 在載入 HTML 文件時使用首選控制項類型？

答：透過設定`PreferredControlType`財產給`HtmlControlType.StructuredDocumentTag`，如範例原始程式碼所示，Aspose.Words在載入文件時將使用SDT來表示HTML元素。

#### Q：我可以使用其他控制類型作為首選嗎？

答：是的，除了`HtmlControlType.StructuredDocumentTag`，Aspose.Words for .NET 支援其他控制項類型，例如`HtmlControlType.ContentControl`和`HtmlControlType.CustomXmlMarkup`.