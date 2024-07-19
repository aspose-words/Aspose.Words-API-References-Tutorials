---
title: Son Not Seçeneklerini Ayarlayın
linktitle: Son Not Seçeneklerini Ayarlayın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde son not seçeneklerini nasıl ayarlayacağınızı öğrenin. Örnek kaynak koduyla adım adım eğitim.
type: docs
weight: 10
url: /tr/net/working-with-footnote-and-endnote/set-endnote-options/
---

Bu adım adım eğitimde, bir Word belgesinde son not seçeneklerini ayarlamak için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve kurulu olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin.[Aspose.Releases]https://releases.aspose.com/words/net/.

## Adım 1: Belge Nesnesini Başlatma

 İlk olarak, başlat`Document` kaynak belgenizin yolunu sağlayarak nesneyi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Adım 2: DocumentBuilder Nesnesini Başlatma

 Daha sonra, başlat`DocumentBuilder` belge üzerinde işlem gerçekleştirecek nesne:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Metin ve Son Not Ekleme

 Kullan`Write` yöntemi`DocumentBuilder` belgeye metin eklemek için nesne ve`InsertFootnote` son not ekleme yöntemi:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Adım 4: Son Not Seçeneklerini Ayarlama

 Erişmek`EndnoteOptions`Son not seçeneklerini değiştirmek için belgenin özelliği. Bu örnekte, yeniden başlatma kuralını her sayfada yeniden başlayacak ve konumu bölümün sonuna ayarlayacak şekilde ayarladık:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Adım 5: Belgeyi Kaydetme

Son olarak değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesinde son not seçeneklerini başarıyla ayarladınız.

### Aspose.Words for .NET kullanarak Son Not Seçeneklerini Ayarlama için örnek kaynak kodu

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

Bu kodu kendi projelerinizde kullanmaktan ve özel gereksinimlerinize göre değiştirmekten çekinmeyin.

### SSS'ler

#### S: Aspose.Words'te son notları nasıl stillendirebilirim?

 C: Aspose.Words'te son notlara stil vermek için`EndnoteOptions` sınıf ve`SeparatorNoteTextStyle` mülk. Bu özelliği kullanarak son notlar için yazı tipi stili, boyutu, rengi vb. belirtebilirsiniz.

#### S: Bir belgedeki son notların numaralandırmasını özelleştirmek mümkün müdür?

 C: Evet, bir belgedeki son notların numaralandırmasını özelleştirmek mümkündür. Şunu kullanabilirsiniz:`RestartRule`Ve`NumberStyle` özellikleri`EndnoteOptions` Belirli yeniden başlatma kurallarını ve numaralandırma stillerini tanımlamak için sınıf.

#### S: Son notları bir belgede nasıl konumlandırabilirim?

C: Son notları bir belgeye yerleştirmek için`Position` mülkiyeti`EndnoteOptions` sınıf. Son notların her sayfanın altına mı, her bölümün sonuna mı yoksa belgenin sonuna mı yerleştirileceğini belirtebilirsiniz.

#### S: Son not numaralandırma biçimini özelleştirebilir miyim?

 C: Evet, Aspose.Words'te son not numaralandırma formatını özelleştirebilirsiniz. Kullan`NumberFormat` mülkiyeti`EndnoteOptions` Arap rakamları, Romen rakamları, harfler vb. gibi istenen formatı ayarlamak için sınıf.

#### S: Bir belgenin bölümleri arasında son not numaralandırmaya devam etmek mümkün müdür?

 C: Evet, bir belgenin bölümleri arasında son not numaralandırmaya devam etmek mümkündür. Kullan`RestartRule` mülkiyeti`EndnoteOptions` sınıfa girin ve buna ayarlayın`RestartContinuous` numaralandırmanın bölümler arasında devam etmesine izin vermek için.