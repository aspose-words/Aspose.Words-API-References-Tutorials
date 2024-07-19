---
title: Css Sınıf Adı Öneki Ekle
linktitle: Css Sınıf Adı Öneki Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgeyi HTML'ye dönüştürürken CSS sınıfı adı öneki eklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

Bu eğitimde, Aspose.Words for .NET ile CSS sınıfı adı öneki eklemek için C# kaynak kodunu adım adım anlatacağız. Bu özellik, bir belgeyi HTML'ye dönüştürürken oluşturulan CSS sınıfı adlarına özel bir önek eklemenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda HTML'ye dönüştürmek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
//Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: HTML kaydetme seçeneklerini ayarlayın

Şimdi CSS stil sayfası türü ve CSS sınıfı adı öneki dahil olmak üzere HTML kaydetme seçeneklerini ayarlayalım. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Bu kod bir örneğini oluşturur`HtmlSaveOptions` ve setler`CssStyleSheetType` ile`CssStyleSheetType.External` harici bir CSS stil sayfası oluşturmak ve`CssClassNamePrefix` ile`"pfx_"` önek için`"pfx_"` CSS sınıfını adlandırmak için.

## Adım 4: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce tanımladığımız HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Bu kod, belgeyi HTML'ye dönüştürür ve CSS sınıfı adı öneki eklenmiş bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Css Sınıf Adı Öneki Ekleme için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeyi HTML'ye dönüştürürken CSS sınıfı adı önekini nasıl ekleyeceğinizi öğrendiniz. Bu eğitimde sağlanan adım adım kılavuz adımını izleyerek, dönüştürülen HTML belgelerinizdeki CSS sınıfı adlarını özelleştirebilirsiniz.