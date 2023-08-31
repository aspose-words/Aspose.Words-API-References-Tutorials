---
title: Meta Dosyalarını Emf veya Wmf'ye Dönüştür
linktitle: Meta Dosyalarını Emf veya Wmf'ye Dönüştür
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgeyi HTML'ye dönüştürürken meta dosyalarını EMF veya WMF formatlarına dönüştürmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

Bu eğitimde, Aspose.Words for .NET ile meta dosyalarını EMF veya WMF formatına dönüştürmek için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgeyi HTML'ye dönüştürürken meta dosyası biçimindeki görüntüleri EMF veya WMF gibi daha uyumlu biçimlere dönüştürmenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeye bir resim ekleme

Bu adımda, dönüştürülecek belgeye bir resim ekleyeceğiz. Bir HTML etiketi kullanarak bir veri kaynağından resim eklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Bu kod, örneğini oluşturur`Document` Ve`DocumentBuilder` belgeyi oluşturmak için. bir ekler`<img>` base64 kodlu görüntü ile belgeye etiketleyin.

## 3. Adım: HTML kaydetme seçeneklerini ayarlayın

Şimdi, resimler için kullanılacak meta dosyası formatı da dahil olmak üzere HTML kaydetme seçeneklerini ayarlayacağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Bu kod, örneğini oluşturur`HtmlSaveOptions` ve ayarlar`MetafileFormat` ile`HtmlMetafileFormat.EmfOrWmf` HTML'ye dönüştürülürken meta dosyalarının EMF veya WMF biçimine dönüştürülmesi gerektiğini belirtmek için.

## 4. Adım: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce tanımlanan HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Bu kod, belgeyi HTML'ye dönüştürür ve ayarlanan kaydetme seçeneklerine bağlı olarak, dönüştürülen meta dosyalarıyla EMF veya WMF biçiminde bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Meta Dosyalarını Emf veya Wmf'ye Dönüştürmek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 içindeki belgeler dizinine giden doğru yolu belirttiğinizden emin olun.`dataDir` değişken.

Artık bir belgeyi Aspose.Words for .NET kullanarak HTML'ye dönüştürürken meta dosyalarını EMF veya WMF formatlarına nasıl dönüştüreceğinizi öğrendiniz. Bu öğreticide sağlanan adım adım kılavuzu izleyerek, dönüştürülen HTML belgelerinizdeki meta dosyalarını kolayca yönetebilirsiniz.