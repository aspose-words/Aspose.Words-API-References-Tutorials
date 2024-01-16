---
title: 連字符回調
linktitle: 連字符回調
second_title: Aspose.Words 文件處理 API
description: 了解如何在 Aspose.Words for .NET 中使用連字符回調來處理單字連字符。
type: docs
weight: 10
url: /zh-hant/net/working-with-hyphenation/hyphenation-callback/
---

在本逐步教學中，我們將向您展示如何使用 Aspose.Words for .NET 中的連字號回呼功能。我們將解釋提供的 C# 原始程式碼並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET。如果您還沒有安裝該庫，請從以下位置下載並安裝該庫：[Aspose.Releases]https://releases.aspose.com/words/net/。

## 第 1 步：儲存連字提醒

首先，我們將使用自訂的連字回呼函數來註冊`CustomHyphenationCallback`班級。這將使我們能夠根據自己的規則處理單字連字符：

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

確保您已實施`CustomHyphenationCallback`根據您的具體需求進行課程。

## 第 2 步：載入文件並套用連字符

接下來，從指定目錄載入文件並使用 Aspose.Words 連接單字：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## 第 3 步：處理遺失字典錯誤

如果連字符字典遺失，我們將捕獲相應的異常並顯示錯誤訊息：

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## 步驟 4： 清理並停用連字提醒

最後，為了保持整潔並關閉連字提醒，請執行以下步驟：

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

這將在完成處理後清理並停用連字提醒。

所以 ！您已成功在 Aspose.Words for .NET 中使用連字號回呼。

### 使用 Aspose.Words for .NET 進行連字符回呼的範例原始碼

```csharp
try
{
	 //註冊連字符回調。
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

請隨意在您自己的專案中使用此程式碼並對其進行修改以滿足您的特定需求。

### 常見問題解答

#### Q：Aspose.Words 中的音節提醒是什麼？

答：Aspose.Words 中的音節提醒功能可讓您自訂文件中單字的音節排列方式。透過使用音節提醒，您可以指定單字音節的自訂規則，這對於特定語言或預設音節無法產生所需結果的特定場景非常有用。

#### Q：如何在Aspose.Words中設定音節提醒？

答：要在 Aspose.Words 中定義連字符回調，您需要建立一個類別來實現`HyphenationCallback`接口並實現`HandleWord()`方法。對於音節化過程中遇到的每個單字都會呼叫此方法。您可以對其應用自訂音節規則並返回音節單字。然後您可以使用以下方法綁定連字號回調`Document.HyphenationCallback`您的文檔的屬性。

#### Q：在 Aspose.Words 中使用音節提醒有什麼好處？

答：在 Aspose.Words 中使用音節提醒的好處是能夠自訂文件中單字的音節排列方式。這使您可以更好地控制音節，特別是對於預設音節無法給出所需結果的特定語言或場景。您可以根據您的需求對每個單字應用特定的規則以獲得精確的音節。

#### Q：在哪些常見場景中使用音節提醒會有所幫助？

答：使用音節增強器在多種情況下很有用，例如：
- 具有特定音節規則的特定語言中單字的音節。
- 首字母縮寫或技術詞彙的個人化音節規則的應用。
- 依風格偏好或印刷標準調整音節。

#### Q：如何在 Aspose.Words 中使用音節提醒來測試自訂音節？

答：要在 Aspose.Words 中使用音節提醒來測試自訂音節，您可以建立一個測試文檔，其中包含要套用自訂音節規則的單字。然後您可以設定自訂音節回調，調用`Document.Range.Replace()`方法來替換文件中的單字，並使用`Hyphenate()`的方法`Hyphenation`類別來取得單字的音節。然後，您可以根據需要設定音節單字的格式，例如在音節之間新增連字符。