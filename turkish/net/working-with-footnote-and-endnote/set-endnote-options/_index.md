---
title: Son Not Seçeneklerini Ayarla
linktitle: Son Not Seçeneklerini Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinde son not seçeneklerini nasıl ayarlayacağınızı öğrenin. Örnek kaynak koduyla adım adım öğretici.
type: docs
weight: 10
url: /tr/net/working-with-footnote-and-endnote/set-endnote-options/
---

Bu adım adım öğreticide, bir Word belgesinde son not seçeneklerini ayarlamak için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` kaynak belgenizin yolunu sağlayarak itiraz edin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## 2. Adım: DocumentBuilder Nesnesini Başlatma

 Ardından,`DocumentBuilder` belge üzerinde işlem gerçekleştirmek için nesne:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Metin ve Son Not Ekleme

 Kullan`Write` yöntemi`DocumentBuilder` belgeye metin eklemek için nesne ve`InsertFootnote` son not ekleme yöntemi:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## 4. Adım: Son Not Seçeneklerini Ayarlama

 Erişmek`EndnoteOptions` Son not seçeneklerini değiştirmek için belgenin özelliği. Bu örnekte, yeniden başlatma kuralını her sayfada yeniden başlayacak ve konumu bölümün sonuna ayarlayacağız:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## 5. Adım: Belgeyi Kaydetme

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Bu kadar! Aspose.Words for .NET kullanarak bir Word belgesinde son not seçeneklerini başarıyla ayarladınız.

### Aspose.Words for .NET kullanarak Set Endnote Options için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.

### SSS

#### S: Aspose.Words'te son notları nasıl biçimlendirebilirim?

 C: Aspose.Words'te son notlara stil vermek için`EndnoteOptions` sınıf ve`SeparatorNoteTextStyle` mülk. Bu özelliği kullanarak son notlar için yazı tipi stilini, boyutunu, rengini vb. belirtebilirsiniz.

#### S: Bir belgedeki son notların numaralandırılmasını özelleştirmek mümkün müdür?

 C: Evet, bir belgedeki son notların numaralandırılmasını özelleştirmek mümkündür. kullanabilirsiniz`RestartRule` Ve`NumberStyle` özellikleri`EndnoteOptions` belirli yeniden başlatma kurallarını ve numaralandırma stillerini tanımlamak için sınıf.

#### S: Son notları bir belgede nasıl konumlandırabilirim?

 C: Bir belgedeki son notları konumlandırmak için`Position` mülkiyeti`EndnoteOptions` sınıf. Son notların her sayfanın altına mı, her bölümün sonuna mı yoksa belgenin sonuna mı yerleştirileceğini belirleyebilirsiniz.

#### S: Son not numaralandırma formatını özelleştirebilir miyim?

 C: Evet, Aspose.Words'te son not numaralandırma formatını özelleştirebilirsiniz. Kullan`NumberFormat` mülkiyeti`EndnoteOptions` Arap rakamları, Romen rakamları, harfler vb. gibi istenen formatı ayarlamak için sınıf.

#### S: Bir belgenin bölümleri arasında son not numaralandırmaya devam etmek mümkün müdür?

 C: Evet, bir belgenin bölümleri arasında son not numaralandırmaya devam etmek mümkündür. Kullan`RestartRule` mülkiyeti`EndnoteOptions` sınıflandırın ve ayarlayın`RestartContinuous` numaralandırmanın bölümler arasında devam etmesini sağlamak için.