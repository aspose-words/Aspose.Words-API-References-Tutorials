---
title: Sayfa Yapısını ve Bölüm Biçimlendirmesini Ayarlayın
linktitle: Sayfa Yapısını ve Bölüm Biçimlendirmesini Ayarlayın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgenin düzenini ve bölüm biçimlendirmesini ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

Bu eğitimde, Aspose.Words for .NET ile mizanpaj ve bölüm biçimlendirmesi ayarlamak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, sayfa yönünü, kenar boşluklarını ve kağıt boyutunu ayarlamanızı sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi oluşturma

Bu adımda yeni bir belge oluşturacağız. Belgeyi oluşturmak ve oluşturucuyu başlatmak için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

## 3. Adım: Düzeni ayarlama ve belgeyi kaydetme

Şimdi belge düzenini yapılandıralım. Yönü, kenar boşluklarını ve kağıt boyutunu ayarlamak için aşağıdaki kodu kullanın:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Bu kod, sayfa yönünü yatay, sol kenar boşluğunu 50 ve kağıt boyutunu 10x14 olarak ayarlayacaktır.

### Aspose.Words for .NET kullanarak Sayfa Yapısını Ayarlama ve Bölüm Biçimlendirme için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

Belgeyi kaydetmek istediğiniz dizine giden doğru yolu belirttiğinizden emin olun.`dataDir` değişken.

Aspose.Words for .NET kullanarak bir belgenin düzenini ve bölüm biçimlendirmesini nasıl yapılandıracağınızı artık öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek, kendi belgelerinizin düzenini ve biçimlendirmesini kolayca özelleştirebilirsiniz.