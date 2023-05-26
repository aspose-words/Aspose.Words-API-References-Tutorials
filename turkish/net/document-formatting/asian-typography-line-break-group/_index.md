---
title: Asya Tipografi Satır Sonu Grubu
linktitle: Asya Tipografi Satır Sonu Grubu
second_title: Aspose.Words for .NET API Referansı
description: Asya Tipografisi satır sonu grubunu Aspose.Words for .NET ile nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/asian-typography-line-break-group/
---

Bu eğitimde, size Asya Tipografisi satır sonu grup özelliğinin Aspose.Words for .NET ile nasıl kullanılacağını göstereceğiz. Kaynak kodunu anlamak ve biçimlendirme değişikliklerini uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için belgelerinizin dizini belirtin ve Asya tipografisini içeren belgeyi bir Document nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 2. Adım: Asya Tipografi Kurulumu

Şimdi belgenin ilk paragrafı için Asya tipografi ayarlarını yapılandıracağız. İşte nasıl:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Aspose.Words for .NET kullanan Asya Tipografi Satır Kesme Grubu için örnek kaynak kodu

İşte Aspose.Words for .NET ile Asya Tipografisi Satır Sonu Grubu özelliğinin tam kaynak kodu:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Bu kodla, Aspose.Words for .NET kullanarak Asya Tipografisi satır sonu grubunu uygulayabileceksiniz.

