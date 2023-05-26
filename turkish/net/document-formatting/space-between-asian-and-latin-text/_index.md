---
title: Asya ve Latin Metinleri Arasındaki Boşluk
linktitle: Asya ve Latin Metinleri Arasındaki Boşluk
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belgenizdeki Asya ve Latin metinleri arasındaki boşluğu otomatik olarak nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/space-between-asian-and-latin-text/
---

Bu öğreticide, size Aspose.Words for .NET ile Asya ve Latin metinleri arasındaki Boşluk özelliğini nasıl kullanacağınızı göstereceğiz. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi oluşturma ve yapılandırma

Başlamak için yeni bir belge ve ilişkili bir DocumentBuilder nesnesi oluşturun. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Asya ve Latin metinleri arasındaki boşluğu ayarlama

Şimdi ParagraphFormat nesnesinin özelliklerini kullanarak Asya ve Latin metinleri arasındaki boşluğu yapılandıracağız. İşte nasıl:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Aspose.Words for .NET kullanan Asya ve Latin Metin Arasındaki Boşluk için örnek kaynak kodu

Aspose.Words for .NET ile Asya ve Latin Metin Arasındaki Boşluk özelliğinin tam kaynak kodu burada:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

Bu kodla, Aspose.Words for .NET'i kullanarak belgenizdeki Asya ve Latin metinleri arasındaki boşluğu otomatik olarak ayarlayabileceksiniz.



