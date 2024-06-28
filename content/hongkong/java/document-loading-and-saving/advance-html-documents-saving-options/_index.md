---
title: 使用 Aspose.Words Java 進階 HTML 文件儲存選項
linktitle: 儲存 HTML 文件
second_title: Aspose.Words Java 文件處理 API
description: 在本教程中，我們介紹了 Aspose.Words for Java 的各種進階 HTML 文件保存選項。這些選項使您能夠創建高品質的 HTML。
type: docs
weight: 16
url: /zh-hant/java/document-loading-and-saving/advance-html-documents-saving-options/
---

在本教學中，我們將探索 Aspose.Words for Java 提供的進階 HTML 文件保存選項。 Aspose.Words 是一個強大的 Java API，用於處理 Word 文檔，它提供了廣泛的文檔操作和轉換功能。

## 一、簡介
Aspose.Words for Java 可讓您以程式設計方式處理 Word 文件。在本教學中，我們將重點介紹進階 HTML 文件保存選項，這些選項可讓您控制將 Word 文件轉換為 HTML 的方式。

## 2. 匯出往返訊息
這`exportRoundtripInformation`方法可讓您將 Word 文件匯出為 HTML，同時保留往返資訊。當您想要將 HTML 轉換回 Word 格式而不遺失任何文件特定的詳細資訊時，此資訊非常有用。

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. 將字體匯出為 Base64
隨著`exportFontsAsBase64`方法，您可以將文件中使用的字體匯出為 HTML 中的 Base64 編碼資料。這可確保 HTML 表示形式保留與原始 Word 文件相同的字體樣式。

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. 出口資源
這`exportResources`方法可讓您指定 CSS 樣式表的類型並匯出字體資源。您也可以在 HTML 中設定資源資料夾和資源別名。

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. 將圖元檔轉換為 EMF 或 WMF
這`convertMetafilesToEmfOrWmf`方法可讓您將文件中的圖元檔案轉換為 EMF 或 WMF 格式，確保 HTML 中的相容性和平滑渲染。

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    //為簡潔起見，未顯示程式碼片段。
}
```

## 6. 將圖元檔轉換為 SVG
使用`convertMetafilesToSvg`將圖元檔案轉換為 SVG 格式的方法。此格式非常適合在 HTML 文件中顯示向量圖形。

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    //為簡潔起見，未顯示程式碼片段。
}
```

## 7.新增CSS類別名稱前綴
隨著`addCssClassNamePrefix`方法，您可以在匯出的 HTML 中為 CSS 類別名稱加上前綴。這有助於防止與現有樣式發生衝突。

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. 匯出 MHTML 資源的 CID URL
這`exportCidUrlsForMhtmlResources`以 MHTML 格式儲存文件時使用此方法。它允許導出資源的 Content-ID URL。

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    //為簡潔起見，未顯示程式碼片段。
}
```

## 9. 解析字體名稱
這`resolveFontNames`方法有助於在以 HTML 格式儲存文件時解析字體名稱，確保跨不同平台的一致渲染。

```java
@Test
public void resolveFontNames() throws Exception {
    //為簡潔起見，未顯示程式碼片段。
}
```

## 10.將文字輸入表單欄位匯出為文字
這`exportTextInputFormFieldAsText`方法將表單欄位匯出為 HTML 中的純文本，使它們易於閱讀和編輯。

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    //為簡潔起見，未顯示程式碼片段。
}
```

## 11. 結論
在本教程中，我們探索了 Aspose.Words for Java 提供的高級 HTML 文件保存選項。這些選項可讓您對轉換過程進行細粒度的控制，從而允許您建立與原始 Word 文件非常相似的 HTML 文件。

## 12.常見問題解答
以下是有關使用 Aspose.Words for Java 和 HTML 文件保存選項的一些常見問題：

### 問題 1：如何使用 Aspose.Words for Java 將 HTML 轉換回 Word 格式？
要將 HTML 轉換回 Word 格式，您可以使用 Aspose.Words API 的`load`方法載入 HTML 文檔，然後將其儲存為 Word 格式。

### Q2：匯出為 HTML 時可以自訂 CSS 樣式嗎？
是的，您可以透過修改 HTML 中使用的樣式表或使用`addCssClassNamePrefix`方法為 CSS 類別名稱加上前綴。

### Q3：有沒有辦法優化網頁顯示的 HTML 輸出？
是的，您可以透過設定將字體匯出為 Base64 以及將圖元檔案轉換為 SVG 等選項來優化 Web 顯示的 HTML 輸出。

### Q4：將複雜的Word文件轉換為HTML時有限制嗎？
雖然 Aspose.Words for Java 提供了強大的轉換功能，但具有複雜佈局的複雜 Word 文件可能需要額外的後處理才能實現所需的 HTML 輸出。
