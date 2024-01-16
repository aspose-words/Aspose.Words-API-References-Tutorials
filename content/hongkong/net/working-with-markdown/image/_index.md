---
title: 影像
linktitle: 影像
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 逐步指南插入和自訂映像。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/image/
---

在此範例中，我們將解釋如何透過 Aspose.Words for .NET 使用圖像功能。圖片可讓您將插圖和圖形插入文件中。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：插入影像

我們可以使用插入圖像`Shape`類別並指定圖像的類型，在這裡`ShapeType.Image`。我們還將圖像的環繞類型設定為`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## 步驟3：影像定制

我們透過指定其完整路徑來自訂圖像，例如`"/attachment/1456/pic001.png"`，並為圖像添加標題。

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### 使用 Aspose.Words for .NET 的圖片範例原始碼

```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

//插入影像。
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

恭喜！現在您已經了解如何使用 Aspose.Words for .NET 的圖片功能。


### 常見問題解答

#### Q：如何將本機檔案中的影像插入 Aspose.Words 中？

答：要將本機檔案中的圖片插入到 Aspose.Words 中，您可以使用`Shape`類和`InsertImage`方法。

#### Q：我可以在 Aspose.Words 中插入來自 URL 的圖像嗎？

答：是的，您可以在 Aspose.Words 中插入來自 URL 的圖像。您可以使用相同的`InsertImage`方法並指定圖像 URL 而不是本機檔案路徑。

#### Q：如何在 Aspose.Words 中調整圖片大小？

答：要在 Aspose.Words 中調整圖片大小，您可以使用`Width`和`Height`的屬性`Shape`目的。

#### Q：我可以在 Aspose.Words 中對影像套用濾鏡嗎？

答：是的，您可以在 Aspose.Words 中對影像套用濾鏡。例如，您可以使用下列命令將模糊濾鏡套用至影像`ApplyGaussianBlur`的方法`Shape`目的。

#### Q：如何在 Aspose.Words 中將一張圖片替換為另一張圖片？

答：要在 Aspose.Words 中將一張圖像替換為另一張圖像，您可以使用`Replace`的方法`Shape`班級。該方法將`Shape`要替換的圖像的物件和`Shape`新圖像的物件。