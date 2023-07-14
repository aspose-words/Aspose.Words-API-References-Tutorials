---
title: Asya Paragraf Aralığını ve Girintilerini Değiştirin
linktitle: Asya Paragraf Aralığını ve Girintilerini Değiştirin
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile Asya paragraf aralığını ve girintileri nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

Bu eğitimde, Aspose.Words for .NET'i kullanarak bir Asya paragrafındaki boşlukları ve girintileri nasıl değiştireceğiniz konusunda size yol göstereceğiz. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için belgelerinizin dizini belirtin ve Asya tipografisini içeren belgeyi bir Document nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 2. Adım: Paragraf aralığını ve girintileri değiştirme

Şimdi Asya belgesinin ilk paragrafındaki boşlukları ve girintileri değiştireceğiz. İşte nasıl:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // ParagraphFormat.LeftIndent'i güncelleyin
format.CharacterUnitRightIndent = 10; // ParagraphFormat.RightIndent'i güncelleyin
format.CharacterUnitFirstLineIndent = 20; // ParagraphFormat.FirstLineIndent'i Güncelle
format.LineUnitBefore = 5; // ParagraphFormat.SpaceBefore'u güncelleyin
format.LineUnitAfter = 10; // ParagraphFormat.SpaceAfter'ı güncelleyin
```

## 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Aspose.Words for .NET kullanarak Asya Paragraf Aralığını ve Girintilerini Değiştirmek için örnek kaynak kodu

Aspose.Words for .NET ile Asya Paragraf Aralığını ve Girintileri Düzenle özelliğinin tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent güncellenecek
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent güncellenecek
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent güncellenecek
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore güncellenecek
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter güncellenecek

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Bu kodla, Aspose.Words for .NET'i kullanarak bir Asya paragrafının boşluklarını ve girintilerini değiştirebileceksiniz.

