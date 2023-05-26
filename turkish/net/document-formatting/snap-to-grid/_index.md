---
title: Kılavuza Yapış
linktitle: Kılavuza Yapış
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Grid'e Yapış özelliğinin C# kaynak kodunu açıklayan adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/document-formatting/snap-to-grid/
---

Bu öğreticide, Aspose.Words for .NET ile Kılavuza Yapış özelliğini nasıl kullanacağınız konusunda size yol göstereceğiz. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi oluşturma ve yapılandırma

Başlamak için yeni bir belge ve ilişkili bir DocumentBuilder nesnesi oluşturun. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Izgara Hizalaması

Şimdi ızgara hizalamasını belirli bir paragrafa ve paragrafta kullanılan yazı tipine uygulayacağız. İşte nasıl:

```csharp
// Paragraf için ızgara hizalamasını etkinleştir
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// Paragrafta metin yaz
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// Paragrafta kullanılan yazı tipi için ızgara hizalamasını etkinleştir
par.Runs[0].Font.SnapToGrid = true;
```

## 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### Aspose.Words for .NET kullanan Grid'e Yapış için örnek kaynak kodu

Aspose.Words for .NET ile Izgaraya Sığdır özelliğinin tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Asya karakterlerini yazarken düzeni optimize edin.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

Bu kodla, Aspose.Words for .NET kullanarak metninizi ızgaraya hizalayabilecek ve belgenizin görünümünü optimize edebileceksiniz.

