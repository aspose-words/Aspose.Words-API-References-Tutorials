---
title: Düzeltmeleri Kabul Et
linktitle: Düzeltmeleri Kabul Et
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesine yönelik düzeltmeleri nasıl kabul edeceğinizi öğrenin
type: docs
weight: 10
url: /tr/net/working-with-revisions/accept-revisions/
---

Bu eğitimde, Aspose.Words for .NET'in Revizyonları Kabul Et özelliğini kullanarak bir Word belgesine revizyonları kabul etme konusunda size yol göstereceğiz. Kaynak kodunu anlamak ve belgedeki değişiklikleri kabul etmek için aşağıdaki adımları izleyin.

## 1. Adım: Belge İçeriğini Ekleme ve Düzenleme

Bu örnekte, bir belge oluşturuyor ve içerik ekliyoruz. Değişiklikleri ve revizyonları göstermek için birkaç paragraf kullanıyoruz. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//İlk paragrafa metin ekleyin, ardından iki paragraf daha ekleyin.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## 2. Adım: İncelemeleri takip edin ve inceleme ekleyin

Revizyon takibini etkinleştirip dokümana revizyon ekliyoruz. İşte nasıl:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Bu paragraf bir düzeltmedir ve karşılık gelen "IsInsertRevision" işaret ayarına sahip olacaktır.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## 3. Adım: Bir paragrafı silin ve düzeltmeleri yönetin

Bir paragrafı sileriz ve kaydedilen revizyonları kontrol ederiz. İşte nasıl:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Revizyonları takip ettiğimiz için, paragraf belgede hala var ve "IsDeleteRevision" bayrağı ayarlanmış olacak
// ve biz tüm incelemeleri kabul edene veya reddedene kadar Microsoft Word'de bir inceleme olarak görüntülenecektir.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## 4. Adım: Değişiklikleri Kabul Edin

Belgedeki tüm değişiklikleri kabul ediyoruz. İşte nasıl:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## 5. Adım: İncelemeleri izlemeyi durdurun

Belgede yapılan değişikliklerin artık düzeltme olarak görünmemesi için düzeltmeleri izlemeyi durduracağız. İşte nasıl:

```csharp
doc.StopTrackRevisions();
```
## 6. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Aspose.Words for .NET kullanan Revizyonları Kabul Et için örnek kaynak kodu

Aspose.Words for .NET kullanan bir belgedeki değişiklikleri kabul etmek için eksiksiz kaynak kodu burada:


```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//İlk paragrafa metin ekleyin, ardından iki paragraf daha ekleyin.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// Hiçbiri herhangi bir revizyon olarak kayıtlı olmayan üç paragrafımız var.
// Revizyonları takip ederken dokümana herhangi bir içerik ekler/çıkarırsak,
// belgede olduğu gibi görüntülenecek ve kabul edilebilir/reddedilebilir.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Bu paragraf bir revizyondur ve buna göre "IsInsertRevision" işaret ayarına sahip olacaktır.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Belgenin paragraf koleksiyonunu alın ve bir paragrafı kaldırın.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Revizyonları takip ettiğimiz için paragraf belgede hala var ve "IsDeleteRevision" ayarlı olacak
// ve biz tüm düzeltmeleri kabul edene veya reddedene kadar Microsoft Word'de bir düzeltme olarak görüntülenecektir.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Düzeltme silme paragrafı, değişiklikleri kabul ettiğimizde kaldırılır.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Revizyon takibinin durdurulması, bu metnin normal metin olarak görünmesini sağlar.
//Belge değiştirildiğinde düzeltmeler sayılmaz.
doc.StopTrackRevisions();

// Belgeyi kaydedin.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Çözüm

Bu öğreticide, Aspose.Words for .NET'in Revizyonları Kabul Et özelliğini kullanarak bir Word belgesindeki revizyonları nasıl kabul edeceğimizi öğrendik. Belge içeriğini ekleme ve düzenleme, düzeltmeleri izleme, düzeltilmiş bir paragrafı silme, tüm değişiklikleri kabul etme ve düzeltmeleri izlemeyi durdurma adımlarını izledik. Artık bu bilgiyi, Aspose.Words for .NET kullanarak kendi Word belgelerinizdeki revizyonları etkili bir şekilde yönetmek için uygulayabilirsiniz.

### SSS

#### S: Aspose.Words for .NET'te revizyon izlemeyi nasıl etkinleştiririm?

#### Çözüm 1:

 C: Aspose.Words for .NET'te revizyon takibini etkinleştirmek için`StartTrackRevisions` yöntemi`Document` nesnesini seçin ve yazar adını ve revizyon takibi için başlangıç tarihini belirtin.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Çözüm 2:

 C: Aşağıdakileri kullanarak revizyon izlemeyi de etkinleştirebilirsiniz.`Document` kabul eden yapıcı`trackRevisions` Ve`author` parametreler.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### S: Aspose.Words for .NET ile bir belgedeki tüm değişiklikler nasıl kabul edilir?

 C: Şunu kullanın:`AcceptAllRevisions` yöntemi`Document` belgede yapılan tüm değişiklikleri kabul etmek için itiraz edin.

```csharp
doc.AcceptAllRevisions();
```

#### S: Değiştirilmiş bir belgeyi kabul edilen düzeltmelerle nasıl kaydedebilirim?

 Kullan`Save` yöntemi`Document` değiştirilen belgeyi kabul edilen düzeltmelerle kaydetmeye itiraz edin. Doğru dosya yolunu sağladığınızdan emin olun.

```csharp
doc.Save("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te revizyonları izlemeyi nasıl durdurabilirim?

 C: Şunu kullanın:`StopTrackRevisions` yöntemi`Document` izleme revizyonlarını durdurmak için nesne.

```csharp
doc.StopTrackRevisions();
```

#### S: Aspose.Words for .NET ile bir belgedeki gözden geçirilmiş bir paragrafı nasıl silebilirim?

 Y: Bir belgedeki gözden geçirilmiş bir paragrafı kaldırmak için`Remove` paragraf toplama yöntemi.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```