---
title: Word Belgesinde Paragrafa Kenarlıklar ve Gölgelendirme Uygulayın
linktitle: Word Belgesinde Paragrafa Kenarlıklar ve Gölgelendirme Uygulayın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile word belgesindeki bir paragrafa kenarlık ve gölgeleme uygulamayı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
Bu eğitimde, Aspose.Words for .NET'in işlevselliğini kullanarak word belgesindeki bir paragrafa nasıl kenarlık ve gölgeleme uygulayacağınızı göstereceğiz. Kaynak kodunu anlamak ve biçimlendirme değişikliklerini uygulamak için aşağıdaki adımları izleyin.

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

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki bir paragrafa kenarlık ve gölgeleme uygulamayı öğrendik. Paragrafı yapılandırarak`Borders` Ve`Shading` özellikler, paragraf için kenarlık stilini, çizgi rengini ve dolgu rengini ayarlayabildik. Aspose.Words for .NET, paragrafların görünümünü özelleştirmek ve belgelerinizin görsel sunumunu geliştirmek için güçlü biçimlendirme yetenekleri sağlar.

### SSS

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki bir paragrafa kenarlıkları ve gölgelendirmeyi nasıl uygularım?

C: Aspose.Words for .NET kullanarak bir Word belgesindeki bir paragrafa kenarlıklar ve gölgeleme uygulamak için şu adımları izleyin:
1.  Yeni bir belge oluşturun ve`DocumentBuilder` nesne.
2.  erişerek paragraf kenarlıklarını yapılandırın.`Borders` mülkiyeti`ParagraphFormat` ve her bir taraf için kenarlık stilini ayarlama.
3.  erişerek paragraf dolgusunu yapılandırın.`Shading` mülkiyeti`ParagraphFormat` ve doku ve dolgu renklerini belirleme.
4.  kullanarak paragrafa içerik ekleyin.`Write` yöntemi`DocumentBuilder`.
5.  kullanarak belgeyi kaydedin.`Save` yöntem.

#### S: Paragrafın her bir tarafı için kenarlık stilini nasıl ayarlarım?

 C: Paragrafın her bir tarafı için kenarlık stilini ayarlamak üzere`Borders` mülkiyeti`ParagraphFormat` ve ayarla`LineStyle` her biri için mülk`BorderType` (Örneğin,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). gibi farklı çizgi stilleri belirleyebilirsiniz.`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, vesaire.

#### S: Paragraf gölgelendirmesi için doku ve dolgu renklerini nasıl belirlerim?

 A: Paragraf gölgelendirmesi için doku ve dolgu renklerini belirtmek üzere`Shading` mülkiyeti`ParagraphFormat` ve ayarla`Texture` özelliğini istenen bir doku indeksine (örn.`TextureIndex.TextureDiagonalCross` ). Ayrıca ayarlayabilirsiniz`BackgroundPatternColor` Ve`ForegroundPatternColor` özellikleri kullanarak istenen renklere`System.Drawing.Color` sınıf.