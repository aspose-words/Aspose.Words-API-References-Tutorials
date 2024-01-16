---
title: Word文件中的水平線格式
linktitle: Word文件中的水平線格式
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中設定水平線的格式。逐步指南。
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/horizontal-rule-format/
---
在這個綜合範例中，您將學習如何使用 Aspose.Words for .NET 在 Word 文件中設定水平線的格式。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠自訂水平線的對齊方式、寬度、高度、顏色和其他屬性。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：建立 DocumentBuilder 並插入水平線
首先，建立一個 DocumentBuilder 物件並使用 InsertHorizontalRule 方法插入水平線：

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## 第 2 步：存取水平線格式
接下來，存取 Shape 物件的 HorizontalRuleFormat 屬性以檢索格式選項：

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## 第 3 步：自訂格式選項
現在，您可以為水平線自訂各種格式選項。例如，您可以調整對齊方式、寬度、高度、顏色和陰影：

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## 步驟 4：儲存文檔
格式化水平線後，使用 Document 物件的 Save 方法將文件儲存到文件中：

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### 使用 Aspose.Words for .NET 的水平規則格式的範例原始程式碼
以下是使用 Aspose.Words for .NET 格式化水平線的完整原始碼：

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

請記住根據您的特定要求調整程式碼，並根據需要使用附加功能對其進行增強。

## 結論
恭喜！您已成功學習如何使用 Aspose.Words for .NET 在 Word 文件中設定水平線的格式。透過遵循逐步指南並利用提供的原始程式碼，您現在可以自訂水平線的外觀以增強文件的視覺佈局。

嘗試不同的格式選項，以獲得水平線所需的樣式和效果。

### Word文件中水平線格式的常見問題解答

#### Q：我可以為水平尺應用不同的顏色嗎？

答：當然！使用 Aspose.Words for .NET，您可以透過將 Color 屬性設定為所需的顏色值來輕鬆自訂水平線的顏色。這使您可以將水平線與文件的整體設計相匹配。

#### Q：橫尺的寬度和高度可以調整嗎？

答：是的，您可以完全控制水平線的寬度和高度。透過修改 WidthPercent 和 Height 屬性，您可以獲得水平線所需的尺寸。

#### Q：我可以更改文件中水平線的對齊方式嗎？

答：當然可以！ Aspose.Words for .NET 可讓您使用 Alignment 屬性指定水平線的對齊方式。您可以從各種選項中進行選擇，例如居中、左對齊、右對齊和對齊。

#### Q：我可以在水平線上套用陰影或背景顏色嗎？

答：是的，您可以在水平線中添加陰影或背景顏色。預設情況下，NoShade 屬性設為 true，但您可以將其設為 false 並使用適當的方法定義著色。

#### Q：我可以在單一文件中插入多條水平線嗎？

答：當然！您可以使用 Aspose.Words for .NET 在 Word 文件中插入多條水平線。只需根據需要重複教程中的步驟即可新增所需數量的水平線。