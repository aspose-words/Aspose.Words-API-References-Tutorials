---
title: Hücre Düzeni
linktitle: Hücre Düzeni
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablo hücresi içinde bir şekli nasıl düzenleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/layout-in-cell/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesindeki tablo hücresi içindeki bir şeklin nasıl düzenleneceğini açıklar. Şekil özelliklerini ayarlayarak ve düzen seçeneklerini kullanarak, şeklin hücre içindeki konumunu ve görünümünü kontrol edebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Tabloyu Oluşturun
 Kullan`StartTable`, `EndTable`, `InsertCell` , Ve`Write` yöntemleri`DocumentBuilder` bir tablo oluşturmak için nesne. kullanarak istediğiniz satır yüksekliğini ve yükseklik kuralını ayarlayın.`RowFormat` özellikler.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## 4. Adım: Şekli Oluşturun ve Biçimlendirin
 Oluşturmak`Shape` filigranı tanımlamak için nesneyi seçin ve özelliklerini yapılandırın. kullanarak bir hücrenin içine yerleştirilecek şekli ayarlayın.`IsLayoutInCell` mülk.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Adım 5: Şekli Özelleştirin
 gibi özellikleri ayarlayarak filigran şeklinin görünümünü ve metnini özelleştirin.`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`vesaire.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Adım 6: Şekli Belgeye Ekleyin
 kullanarak filigran şeklini belgeye ekleyin.`InsertNode` yöntemi`DocumentBuilder` nesne. kullanarak şekli konumlandırın.`MoveTo` belgedeki son çalıştırmadan sonra yerleştirme yöntemi.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## 7. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.LayoutInCell.docx" olarak kaydediyoruz.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### Aspose.Words for .NET kullanan Layout In Cell için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // Bir hücreye yerleştirilecekse şekli tablo hücresinin dışında görüntüleyin.
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesindeki bir tablo hücresinin içine başarıyla bir şekil yerleştirdiniz.