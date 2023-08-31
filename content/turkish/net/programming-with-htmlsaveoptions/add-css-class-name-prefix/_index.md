---
title: Css Sınıf Adı Öneki Ekle
linktitle: Css Sınıf Adı Öneki Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgeyi HTML'ye dönüştürürken bir CSS sınıf adı öneki eklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

Bu eğitimde, Aspose.Words for .NET ile bir CSS sınıfı adı ön eki eklemek için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgeyi HTML'ye dönüştürürken oluşturulan CSS sınıfı adlarına özel bir önek eklemenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda HTML'ye dönüştürmek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: HTML kaydetme seçeneklerini ayarlayın

Şimdi, CSS stil sayfası türü ve CSS sınıf adı öneki dahil olmak üzere HTML kaydetme seçeneklerini ayarlayalım. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Bu kod, örneğini oluşturur`HtmlSaveOptions` ve ayarlar`CssStyleSheetType` ile`CssStyleSheetType.External`harici bir CSS stil sayfası oluşturmak için ve`CssClassNamePrefix` ile`"pfx_"` önek için`"pfx_"` CSS sınıfını adlandırmak için.

## 4. Adım: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce tanımlanan HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Bu kod, belgeyi HTML'ye dönüştürür ve CSS sınıf adı öneki eklenmiş bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Add Css Class Name Prefix için örnek kaynak kodu

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

 bölümünde doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık bir belgeyi Aspose.Words for .NET kullanarak HTML'ye dönüştürürken bir CSS sınıfı adı öneki eklemeyi öğrendiniz. Bu eğitimde sağlanan adım adım kılavuz adımını izleyerek, dönüştürülen HTML belgelerinizdeki CSS sınıfı adlarını özelleştirebilirsiniz.