---
title: Word Belgesinde Paragrafa Kenarlık ve Gölgelendirme Uygulayın
linktitle: Word Belgesinde Paragrafa Kenarlık ve Gölgelendirme Uygulayın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile word belgesindeki bir paragrafa kenarlık ve gölgelendirmeyi nasıl uygulayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
Bu eğitimde size Aspose.Words for .NET'in işlevselliğini kullanarak word belgesindeki bir paragrafa kenarlık ve gölgelendirmenin nasıl uygulanacağını göstereceğiz. Kaynak kodunu anlamak ve biçimlendirme değişikliklerini uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi oluşturma ve yapılandırma

Başlamak için yeni bir belge ve ilişkili bir DocumentBuilder nesnesi oluşturun. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Sınır yapılandırması

Şimdi her bir kenar için kenarlık stilini belirterek paragraf kenarlıklarını yapılandıralım. İşte nasıl:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Adım 3: Dolgu Kurulumu

Şimdi dokuyu ve dolgu renklerini belirterek paragraf dolgusunu yapılandıracağız. İşte nasıl:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## 4. Adım: İçerik ekleyin

Paragrafa bazı biçimlendirilmiş içerik ekleyeceğiz. İşte nasıl:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi kullanarak belgeyi istediğiniz konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Aspose.Words for .NET kullanarak Paragrafa Kenarlık ve Gölgelendirme Uygulamak için örnek kaynak kodu

Aspose.Words for .NET ile Paragrafa Kenarlık ve gölgelendirme uygulama özelliğinin tam kaynak kodunu burada bulabilirsiniz:

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

 Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki bir paragrafa kenarlık ve gölgelendirmenin nasıl uygulanacağını öğrendik. Paragrafın yapılandırılmasıyla`Borders` Ve`Shading` özellikleri sayesinde paragrafın kenarlık stilini, çizgi rengini ve dolgu rengini ayarlayabildik. Aspose.Words for .NET, paragrafların görünümünü özelleştirmek ve belgelerinizin görsel sunumunu geliştirmek için güçlü biçimlendirme yetenekleri sağlar.

### SSS'ler

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki bir paragrafa kenarlıkları ve gölgelendirmeyi nasıl uygularım?

C: Aspose.Words for .NET kullanarak bir Word belgesindeki bir paragrafa kenarlık ve gölgelendirme uygulamak için şu adımları izleyin:
1.  Yeni bir belge oluşturun ve`DocumentBuilder` nesne.
2.  Şuraya erişerek paragraf kenarlıklarını yapılandırın:`Borders` mülkiyeti`ParagraphFormat` ve her iki taraf için kenarlık stilini ayarlama.
3. Şuraya erişerek paragraf dolgusunu yapılandırın:`Shading` mülkiyeti`ParagraphFormat` doku ve dolgu renklerini belirtme.
4.  kullanarak paragrafa içerik ekleyin.`Write` yöntemi`DocumentBuilder`.
5.  kullanarak belgeyi kaydedin.`Save` yöntem.

#### S: Paragrafın her iki tarafı için kenarlık stilini nasıl ayarlarım?

 C: Paragrafın her iki tarafının kenarlık stilini ayarlamak için`Borders` mülkiyeti`ParagraphFormat` ve ayarlayın`LineStyle` her biri için mülk`BorderType` (Örneğin.,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Gibi farklı çizgi stillerini belirtebilirsiniz.`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, vesaire.

#### S: Paragraf gölgelendirmesinin dokusunu ve dolgu renklerini nasıl belirlerim?

 C: Paragraf gölgelendirmesinin dokusunu ve dolgu renklerini belirtmek için`Shading` mülkiyeti`ParagraphFormat` ve ayarlayın`Texture` özelliği istenen doku indeksine (örn.`TextureIndex.TextureDiagonalCross` ). Ayrıca`BackgroundPatternColor` Ve`ForegroundPatternColor` özelliklerini kullanarak istenilen renklere`System.Drawing.Color` sınıf.