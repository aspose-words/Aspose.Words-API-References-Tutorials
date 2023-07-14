---
title: Paragraf Stili Uygula
linktitle: Paragraf Stili Uygula
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir paragraf stilini nasıl uygulayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/apply-paragraph-style/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir paragraf stilini nasıl uygulayacağınızı size göstereceğiz. Kaynak kodunu anlamak ve paragraf stilini uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi oluşturma ve yapılandırma

Başlamak için yeni bir belge ve ilişkili bir DocumentBuilder nesnesi oluşturun. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Paragraf stilini yapılandırma

Şimdi yerleşik stil tanımlayıcıyı kullanarak paragraf stilini yapılandıracağız. İşte nasıl:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## 3. Adım: İçerik ekleyin

Paragrafa içerik ekleyeceğiz. İşte nasıl:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Aspose.Words for .NET kullanarak Paragraf Stili Uygula için örnek kaynak kodu

Aspose.Words for .NET ile Paragraf Stili Uygula özelliğinin tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

Bu kodla, Aspose.Words for .NET kullanarak bir paragraf stili uygulayabileceksiniz.

