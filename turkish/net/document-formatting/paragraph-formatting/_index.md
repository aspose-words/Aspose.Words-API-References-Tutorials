---
title: Paragraf Biçimlendirme
linktitle: Paragraf Biçimlendirme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile paragraflarınıza nasıl özel biçimlendirme uygulayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/paragraph-formatting/
---

Bu öğreticide, Aspose.Words for .NET ile paragraf biçimlendirme özelliğini nasıl kullanacağınız konusunda size yol göstereceğiz. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi oluşturma ve yapılandırma

Başlamak için yeni bir belge ve ilişkili bir DocumentBuilder nesnesi oluşturun. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Paragrafı biçimlendirme

Şimdi, DocumentBuilder nesnesinin ParagraphFormat nesnesinde bulunan özellikleri kullanarak paragrafa biçimlendirmeyi uygulayacağız. İşte nasıl:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat. LeftIndent = 50;
paragraphFormat. RightIndent = 50;
paragraphFormat. SpaceAfter = 25;
```

## 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
builder.Writeln(
	"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
builder.Writeln(
	"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
```

### Aspose.Words for .NET kullanarak Paragraf Biçimlendirme için örnek kaynak kodu

Aspose.Words for .NET ile paragraf biçimlendirme özelliğinin tam kaynak kodu burada:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.Alignment = ParagraphAlignment.Center;
	paragraphFormat.LeftIndent = 50;
	paragraphFormat.RightIndent = 50;
	paragraphFormat.SpaceAfter = 25;

	builder.Writeln(
		"I'm a very nice formatted paragraph. I'm intended to demonstrate how the left and right indents affect word wrapping.");
	builder.Writeln(
		"I'm another nice formatted paragraph. I'm intended to demonstrate how the space after paragraph looks like.");

	doc.Save(dataDir + "DocumentFormatting.ParagraphFormatting.docx");
	
```

Bu kodla, Aspose.Words for .NET kullanarak paragraflarınıza farklı biçimlendirmeler uygulayabileceksiniz.

