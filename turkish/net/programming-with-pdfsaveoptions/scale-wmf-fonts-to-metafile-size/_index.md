---
title: Wmf Yazı Tiplerini Meta Dosyası Boyutuna Göre Ölçeklendirin
linktitle: Wmf Yazı Tiplerini Meta Dosyası Boyutuna Göre Ölçeklendirin
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile PDF'ye dönüştürürken WMF yazı tipi boyutunu ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Bu makale, Aspose.Words for .NET ile WMF Yazı Tipi Ölçeklemeyi Meta Dosyası Boyutuna Göre Ölçeklendirme özelliğinin nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, PDF'ye dönüştürürken WMF yazı tipi ölçeklendirmeyi nasıl etkinleştireceğinizi veya devre dışı bırakacağınızı anlayabileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Ardından, işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte, belgenin "text.docx ile WMF" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## 3. Adım: Meta dosyası oluşturma seçeneklerini yapılandırın

 WMF yazı tipini meta dosyası boyutuna ölçeklendirmeyi etkinleştirmek veya devre dışı bırakmak için,`MetafileRenderingOptions` nesne. Bu örnekte, ayarlayarak yazı tipi ölçeklemeyi devre dışı bırakıyoruz.`ScaleWmfFontsToMetafileSize` mülkiyet`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## 4. Adım: Meta dosyası oluşturma seçenekleriyle PDF olarak kaydetme seçeneklerini yapılandırın

Son olarak, daha önce yapılandırılan meta dosyası oluşturma seçeneklerini kullanarak PDF'ye kaydet seçeneklerini yapılandırabiliriz.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## 5. Adım: Belgeyi Meta Dosya Oluşturma Seçenekleriyle PDF Olarak Kaydedin

Önceden yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF biçiminde kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Bu kadar ! Dönüştürürken WMF yazı tipini meta dosyası boyutuna ölçeklendirmeyi başarıyla etkinleştirdiniz veya devre dışı bıraktınız

Aspose.Words for .NET kullanan bir PDF belgesi.

### Aspose.Words for .NET ile WMF yazı tiplerini meta dosyası boyutuna ölçeklendirmek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Aspose.Words bazı meta dosyası kayıtlarını vektör grafiklerine doğru şekilde işleyemezse
	// ardından Aspose.Words bu meta dosyasını bir bitmap'e dönüştürür.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```
