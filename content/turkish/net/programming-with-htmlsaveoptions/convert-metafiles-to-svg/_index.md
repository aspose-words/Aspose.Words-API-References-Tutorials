---
title: Meta Dosyalarını Svg'ye Dönüştür
linktitle: Meta Dosyalarını Svg'ye Dönüştür
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgeyi HTML'ye dönüştürürken meta dosyalarını SVG formatına dönüştürmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

Bu eğitimde, Aspose.Words for .NET ile meta dosyalarını SVG formatına dönüştürmek için C# kaynak kodunu anlatacağız. Bu özellik, bir belgeyi HTML'ye dönüştürürken meta dosyalarını SVG formatına dönüştürmenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## 2. Adım: Belgeye bir SVG resmi ekleme

Bu adımda dönüştürülecek belgeye bir SVG resmi ekleyeceğiz. HTML etiketi kullanarak bir SVG resmi eklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Bu kod bir örneğini oluşturur`Document`Ve`DocumentBuilder` belgeyi oluşturmak için. Bir ekler`<svg>` içeren etiket`<polygon>` SVG görüntüsünün şeklini ve stilini tanımlayan niteliklere sahip öğe.

## 3. Adım: HTML kaydetme seçeneklerini ayarlayın

Şimdi meta dosyalarının SVG formatına dönüştürülmesi gerektiğini belirterek HTML kaydetme seçeneklerini ayarlayacağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Bu kod bir örneğini oluşturur`HtmlSaveOptions` ve setler`MetafileFormat` ile`HtmlMetafileFormat.Svg` HTML'ye dönüştürürken meta dosyalarının SVG formatına dönüştürülmesi gerektiğini belirtmek için.

## Adım 4: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce tanımladığımız HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Bu kod, belgeyi HTML'ye dönüştürür ve meta dosyaların SVG'ye dönüştürüldüğü bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Meta Dosyalarını Svg'ye Dönüştürme için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
