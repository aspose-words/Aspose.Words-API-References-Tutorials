---
title: Hücre İçi Düzen
linktitle: Hücre İçi Düzen
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir Word belgesinde bir tablo hücresindeki bir şeklin yerleşimini nasıl yapacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/layout-in-cell/
---

Bu eğitimde, Aspose.Words for .NET kullanılarak bir Word belgesinde bir tablo hücresi içindeki bir şeklin nasıl düzenleneceği açıklanmaktadır. Şekil özelliklerini ayarlayarak ve düzen seçeneklerini kullanarak şeklin hücre içindeki konumunu ve görünümünü kontrol edebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmaya itiraz edin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 3: Tabloyu Oluşturun
 Kullan`StartTable`, `EndTable`, `InsertCell` , Ve`Write` yöntemleri`DocumentBuilder`bir tablo oluşturmak için nesne. İstenilen satır yüksekliğini ve yükseklik kuralını kullanarak ayarlayın.`RowFormat` özellikler.

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

## Adım 4: Şekli Oluşturun ve Biçimlendirin
 Oluşturmak`Shape` Filigranı tanımlamak için nesneyi seçin ve özelliklerini yapılandırın. kullanarak bir hücrenin içine yerleştirilecek şekli ayarlayın.`IsLayoutInCell` mülk.

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
 Aşağıdaki gibi özellikleri ayarlayarak filigran şeklinin görünümünü ve metnini özelleştirin:`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`, vesaire.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Adım 6: Şekli Belgeye Ekleme
 kullanarak filigran şeklini belgeye ekleyin.`InsertNode` yöntemi`DocumentBuilder` nesne. kullanarak şekli konumlandırın.`MoveTo` belgedeki son çalıştırmadan sonra yerleştirme yöntemini kullanın.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Adım 7: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.LayoutInCell.docx" olarak kaydediyoruz.

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
		IsLayoutInCell = true, // Şekli bir hücreye yerleştirilecekse tablo hücresinin dışında görüntüleyin.
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

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgesindeki bir tablo hücresindeki şekli başarıyla yerleştirdiniz.