---
title: Paragrafa Kenarlıklar ve Gölgelendirme Uygula
linktitle: Paragrafa Kenarlıklar ve Gölgelendirme Uygula
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir paragrafa kenarlık ve gölgeleme uygulamayı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/apply-borders-and-shading-to-paragraph/
---

Bu öğreticide, size Aspose.Words for .NET'in işlevselliğini kullanarak bir paragrafa nasıl kenarlık ve gölgeleme uygulayacağınızı göstereceğiz. Kaynak kodunu anlamak ve biçimlendirme değişikliklerini uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi oluşturma ve yapılandırma

Başlamak için yeni bir belge ve ilişkili bir DocumentBuilder nesnesi oluşturun. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Sınır yapılandırması

Şimdi her taraf için kenarlık stilini belirleyerek paragraf kenarlıklarını yapılandıralım. İşte nasıl:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## 3. Adım: Dolgu Kurulumu

Şimdi doku ve dolgu renklerini belirterek paragraf dolgusunu yapılandıracağız. İşte nasıl:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## 4. Adım: İçerik ekleyin

Paragrafa biçimlendirilmiş bazı içerikler ekleyeceğiz. İşte nasıl:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Aspose.Words for .NET kullanarak Paragrafa Kenarlıklar ve Gölgelendirme Uygula için örnek kaynak kodu

Aspose.Words for .NET ile Apply Borders ve Shading to Paragraph özelliğinin tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```
