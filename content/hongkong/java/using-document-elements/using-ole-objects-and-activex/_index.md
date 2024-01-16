---
title: 在 Aspose.Words for Java 中使用 OLE 物件和 ActiveX 控件
linktitle: 使用 OLE 物件和 ActiveX 控件
second_title: Aspose.Words Java 文件處理 API
description: 了解如何在 Aspose.Words for Java 中使用 OLE 物件和 ActiveX 控制項。輕鬆建立互動式文件。現在就開始吧！
type: docs
weight: 21
url: /zh-hant/java/using-document-elements/using-ole-objects-and-activex/
---
在本教學中，我們將探討如何在 Aspose.Words for Java 中使用 OLE（物件連結和嵌入）物件和 ActiveX 控制項。 OLE 物件和 ActiveX 控制項是功能強大的工具，可讓您透過嵌入或連結外部內容（例如電子表格、多媒體檔案或互動式控制項）來增強文件。請跟隨我們深入研究程式碼範例並學習如何有效地使用這些功能。

### 先決條件

在我們開始之前，請確保您具備以下先決條件：

1.  Aspose.Words for Java ：確保您的 Java 專案中安裝了 Aspose.Words 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/words/java/).

2. Java 開發環境：您的系統上應該設定有一個有效的 Java 開發環境。

### 插入 OLE 對象

我們首先將 OLE 物件插入到 Word 文件中。我們將建立一個簡單的 Word 文檔，然後插入一個表示網頁的 OLE 物件。

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

在此程式碼中，我們建立一個新文件並插入一個顯示 Aspose 網站的 OLE 物件。您可以將 URL 替換為所需的內容。

### 使用 OlePackage 插入 OLE 對象

接下來，讓我們探討如何使用 OlePackage 插入 OLE 物件。這允許您將外部文件作為 OLE 物件嵌入到文件中。

```java
@Test
public void insertOleObjectWithOlePackage() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    byte[] bs = FileUtils.readFileToByteArray(new File("Your Directory Path" + "Zip file.zip"));
    try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
    {
        Shape shape = builder.insertOleObject(stream, "Package", true, null);
        OlePackage olePackage = shape.getOleFormat().getOlePackage();
        olePackage.setFileName("filename.zip");
        olePackage.setDisplayName("displayname.zip");
        doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
    }
}
```

在此範例中，我們使用 OlePackage 插入 OLE 對象，讓您可以將外部檔案作為嵌入對象包含在內。

### 將 OLE 物件作為圖示插入

現在，讓我們看看如何插入 OLE 物件作為圖示。當您想要顯示代表嵌入文件的圖示時，這非常有用。

```java
@Test
public void insertOleObjectAsIcon() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObjectAsIcon("Your Directory Path" + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico", "My embedded file");
    doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
}
```

在此程式碼中，我們插入一個 OLE 物件作為圖標，為嵌入內容提供更具視覺吸引力的表示。

### 讀取 ActiveX 控制項屬性

現在，讓我們將注意力轉向 ActiveX 控制項。我們將學習如何讀取 Word 文件中 ActiveX 控制項的屬性。

```java
@Test
public void readActiveXControlProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "ActiveX controls.docx");
    String properties = "";
    for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
    {
        if (shape.getOleFormat() == null) break;
        OleControl oleControl = shape.getOleFormat().getOleControl();
        if (oleControl.isForms2OleControl())
        {
            Forms2OleControl checkBox = (Forms2OleControl) oleControl;
            properties = properties + "\nCaption: " + checkBox.getCaption();
            properties = properties + "\nValue: " + checkBox.getValue();
            properties = properties + "\nEnabled: " + checkBox.getEnabled();
            properties = properties + "\nType: " + checkBox.getType();
            if (checkBox.getChildNodes() != null)
            {
                properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
            }
            properties += "\n";
        }
    }
    properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
    System.out.println("\n" + properties);
}
```

在此程式碼中，我們迭代 Word 文件中的形狀、識別 ActiveX 控制項並檢索它們的屬性。

### 結論

恭喜！您已經學習如何在 Aspose.Words for Java 中使用 OLE 物件和 ActiveX 控制項。這些功能為創建動態和互動式文件開闢了無限可能。

### 常見問題解答

### Word 文件中 OLE 物件的用途是什麼？ 
   - OLE 物件可讓您在 Word 文件中嵌入或連結外部內容，例如文件或網頁。

### 我可以自訂文件中 OLE 物件的外觀嗎？ 
   - 是的，您可以自訂 OLE 物件的外觀，包括設定圖示和檔案名稱。

### 什麼是 ActiveX 控制項？它們如何增強我的文件？ 
   - ActiveX 控制項是可以為 Word 文件新增功能的互動式元素，例如表單控製或多媒體播放器。

### Aspose.Words for Java 適合企業級文件自動化嗎？ 
   - 是的，Aspose.Words for Java 是一個功能強大的函式庫，用於在 Java 應用程式中自動產生和操作文件。

### 在哪裡可以存取 Aspose.Words for Java？ 
   - 您可以從以下位置下載 Aspose.Words for Java：[這裡](https://releases.aspose.com/words/java/).

立即開始使用 Aspose.Words for Java，釋放文件自動化和自訂的全部潛力！
