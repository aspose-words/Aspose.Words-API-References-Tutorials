---
title: 在 Aspose.Words for Java 中使用列表
linktitle: 使用清單
second_title: Aspose.Words Java 文件處理 API
description: 透過此逐步教程，學習如何在 Aspose.Words for Java 中使用清單。有效地組織和格式化您的文件。
type: docs
weight: 18
url: /zh-hant/java/using-document-elements/using-lists/
---

在這個綜合教程中，我們將探討如何有效地使用 Aspose.Words for Java 中的列表，這是一個強大的 API，用於以程式設計方式處理 Microsoft Word 文件。清單對於建立和組織文件中的內容至關重要。我們將介紹使用清單的兩個關鍵方面：在每個部分重新啟動清單和指定清單層級。讓我們深入了解吧！

## Aspose.Words for Java 簡介

在開始使用清單之前，讓我們先熟悉一下 Aspose.Words for Java。該 API 為開發人員提供了在 Java 環境中建立、修改和操作 Word 文件的工具。它是一種多功能解決方案，適用於從簡單的文件生成到複雜的格式設定和內容管理等任務。

### 設定您的環境

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for Java。你可以下載它[這裡](https://releases.aspose.com/words/java/). 

## 在每個部分重新啟動列表

在許多情況下，您可能需要在文件的每個部分重新啟動清單。這對於創建具有多個部分的結構化文件（例如報告、手冊或學術論文）非常有用。

以下是有關如何使用 Aspose.Words for Java 實現此目的的逐步指南：

### 初始化您的文件： 
首先建立一個新的文檔物件。

```java
Document doc = new Document();
```

### 新增編號清單： 
將編號清單新增至您的文件。我們將使用預設的編號樣式。

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### 配置列表設定： 
\啟用清單在每個部分重新啟動。

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### 文檔生成器設定： 
建立一個 DocumentBuilder 以將內容新增到文件中。

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### 新增列表項目： 
使用循環將清單項目新增至文件。我們將在第 15 項之後插入分節符。

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### 儲存您的文件： 
使用所需選項儲存文件。

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

透過執行這些步驟，您可以建立包含在每個部分重新開始的清單的文檔，從而保持清晰且有組織的內容結構。

## 指定列表級別

Aspose.Words for Java 允許您指定清單級別，當您在文件中需要不同的清單格式時，這特別有用。讓我們探討一下如何做到這一點：

### 初始化您的文件： 
建立一個新的文檔物件。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### 建立編號清單： 
套用 Microsoft Word 中的編號清單範本。

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### 指定清單等級： 
迭代不同的列表層級並添加內容。

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### 建立項目符號清單： 
現在，讓我們建立一個項目符號清單。

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### 指定項目符號清單層級： 
與編號清單類似，指定等級並新增內容。

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### 停止清單格式： 
若要停止清單格式化，請將清單設為空白。

```java
builder.getListFormat().setList(null);
```

### 儲存您的文件： 
儲存文檔。

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

透過執行這些步驟，您可以建立具有自訂清單層級的文檔，從而允許您控製文檔中清單的格式。

## 完整的原始碼
```java
	string outPath = "Your Output Directory";
 public void restartListAtEachSection() throws Exception
    {
        Document doc = new Document();
        doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
        List list = doc.getLists().get(0);
        list.isRestartAtEachSection(true);
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().setList(list);
        for (int i = 1; i < 45; i++)
        {
            builder.writeln(MessageFormat.format("List Item {0}", i));
            if (i == 15)
                builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        }
        //只有當合規性高於 OoxmlComplianceCore.Ecma376 時才會寫入 IsRestartAtEachSection。
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        //根據 Microsoft Word 清單範本之一建立編號列表
        //並將其應用於文件生成器的當前段落。
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        //此列表中有九個級別，讓我們全部嘗試一下。
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        //基於 Microsoft Word 清單範本之一建立項目符號列表
        //並將其應用於文件生成器的當前段落。
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        //這是停止清單格式化的一種方法。
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        //根據模板建立清單。
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        //要重複使用第一個列表，我們需要透過建立原始列表格式的副本來重新開始編號。
        List list2 = doc.getLists().addCopy(list1);
        //我們可以以任何方式修改新列表，包括設定新的起始編號。
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## 結論

恭喜！您已經了解如何在 Aspose.Words for Java 中有效地使用清單。清單對於組織和呈現文件中的內容至關重要。無論您需要在每個部分重新啟動清單還是指定清單級別，Aspose.Words for Java 都能提供您建立具有專業外觀的文件所需的工具。

現在，您可以自信地使用這些功能來增強文件生成和格式化任務。如果您有任何疑問或需要進一步協助，請隨時聯繫[Aspose 社群論壇](https://forum.aspose.com/)為了支持。

## 常見問題解答

### 如何安裝 Aspose.Words for Java？
您可以從以下位置下載 Aspose.Words for Java：[這裡](https://releases.aspose.com/words/java/)並按照文件中的安裝說明進行操作。

### 我可以自訂清單的編號格式嗎？
是的，Aspose.Words for Java 提供了廣泛的選項來自訂清單編號格式。具體可以參考API文件。

### Aspose.Words for Java 是否與最新的 Word 文件標準相容？
是的，您可以設定 Aspose.Words for Java 以符合各種 Word 文件標準，包括 ISO 29500。

### 我可以使用 Aspose.Words for Java 產生包含表格和圖像的複雜文件嗎？
絕對地！ Aspose.Words for Java 支援進階文件格式，包括表格、圖片等。檢查文檔中的範例。

### 在哪裡可以獲得 Aspose.Words for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
