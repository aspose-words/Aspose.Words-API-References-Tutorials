---
title: Meta Dosyalarını Svg'ye Dönüştür
linktitle: Meta Dosyalarını Svg'ye Dönüştür
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgeyi HTML'ye dönüştürürken meta dosyalarını SVG formatına dönüştürmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

Bu eğitimde, Aspose.Words for .NET ile meta dosyalarını SVG formatına dönüştürmek için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgeyi HTML'ye dönüştürürken meta dosyalarını SVG formatına dönüştürmenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeye bir SVG görüntüsü ekleme

Bu adımda, dönüştürülecek belgeye bir SVG görüntüsü ekleyeceğiz. Bir HTML etiketi kullanarak bir SVG resmi eklemek için aşağıdaki kodu kullanın:

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

 Bu kod, örneğini oluşturur`Document` Ve`DocumentBuilder` belgeyi oluşturmak için. bir ekler`<svg>` içeren etiket`<polygon>` SVG görüntüsünün şeklini ve stilini tanımlayan niteliklere sahip öğe.

## 3. Adım: HTML kaydetme seçeneklerini ayarlayın

Şimdi meta dosyaların SVG biçimine dönüştürülmesi gerektiğini belirterek HTML kaydetme seçeneklerini ayarlayacağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Bu kod, örneğini oluşturur`HtmlSaveOptions` ve ayarlar`MetafileFormat` ile`HtmlMetafileFormat.Svg` meta dosyalarının HTML'ye dönüştürülürken SVG biçimine dönüştürülmesi gerektiğini belirtmek için.

## 4. Adım: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce tanımlanan HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Bu kod, belgeyi HTML'ye dönüştürür ve meta dosyalarının SVG'ye dönüştürüldüğü bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Meta Dosyalarını Svg'ye Dönüştürmek için örnek kaynak kodu

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
