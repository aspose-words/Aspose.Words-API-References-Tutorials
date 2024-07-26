---
title: Düzeltmeleri Kabul Et
linktitle: Düzeltmeleri Kabul Et
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesindeki revizyonları nasıl kabul edeceğinizi öğrenin
type: docs
weight: 10
url: /tr/net/working-with-revisions/accept-revisions/
---

Bu eğitimde, Aspose.Words for .NET'in Revizyonları Kabul Et özelliğini kullanarak bir Word belgesindeki revizyonları kabul etme konusunda size yol göstereceğiz. Kaynak kodunu anlamak ve belgede yapılan değişiklikleri kabul etmek için aşağıdaki adımları izleyin.

## 1. Adım: Belge İçeriğini Ekleme ve Düzenleme

Bu örnekte bir belge oluşturuyoruz ve içerik ekliyoruz. Değişiklikleri ve revizyonları göstermek için birkaç paragraf kullanıyoruz. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// İlk paragrafa metin ekleyin, ardından iki paragraf daha ekleyin.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## 2. Adım: İncelemeleri izleyin ve inceleme ekleyin

Revizyon takibini etkinleştirip dokümana revizyon ekliyoruz. İşte nasıl:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Bu paragraf bir revizyondur ve karşılık gelen "IsInsertRevision" bayrağını içerecektir.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## 3. Adım: Bir paragrafı silin ve düzeltmeleri yönetin

Bir paragrafı sileriz ve kayıtlı revizyonları kontrol ederiz. İşte nasıl:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Revizyonları takip ettiğimiz için paragraf hala belgede mevcut ve "IsDeleteRevision" bayrağı ayarlanmış olacak
// ve biz tüm incelemeleri kabul edene veya reddedene kadar Microsoft Word'de inceleme olarak görüntülenecektir.
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

## 5. Adım: İncelemeleri izlemeyi bırakın

Belgedeki değişikliklerin artık revizyon olarak görünmemesi için revizyonları izlemeyi bırakacağız. İşte nasıl:

```csharp
doc.StopTrackRevisions();
```
## Adım 6: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi kullanarak belgeyi istediğiniz konuma kaydedin.`Save`yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Aspose.Words for .NET kullanarak Düzeltmeleri Kabul Etme için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir belgedeki değişiklikleri kabul etmek için gereken kaynak kodun tamamı burada:


```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// İlk paragrafa metin ekleyin, ardından iki paragraf daha ekleyin.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Hiçbiri herhangi bir revizyon türü olarak kayıtlı olmayan üç paragrafımız var
// Revizyonları takip ederken dokümana herhangi bir içerik ekler/kaldırırsak,
// belgede bu şekilde görüntülenecek ve kabul/reddedilebilecektir.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Bu paragraf bir revizyondur ve uygun "IsInsertRevision" bayrağına sahip olacaktır.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Belgenin paragraf koleksiyonunu alın ve bir paragrafı kaldırın.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Revizyonları takip ettiğimiz için paragraf hala belgede mevcut ve "IsDeleteRevision" ayarına sahip olacak
// ve biz tüm revizyonları kabul edene veya reddedene kadar Microsoft Word'de revizyon olarak görüntülenecektir.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Değişiklikleri kabul ettiğimizde revizyon paragrafını sil kaldırılır.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Revizyonların takibinin durdurulması bu metnin normal metin olarak görünmesini sağlar.
// Belge değiştirildiğinde revizyonlar sayılmaz.
doc.StopTrackRevisions();

// Belgeyi kaydedin.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Çözüm

Bu eğitimde Aspose.Words for .NET'in Revizyonları Kabul Et özelliğini kullanarak bir Word belgesindeki revizyonları nasıl kabul edeceğimizi öğrendik. Belge içeriğini ekleme ve düzenleme, revizyonları izleme, revize edilen paragrafı silme, tüm değişiklikleri kabul etme ve revizyonları izlemeyi durdurma adımlarını izledik. Artık Aspose.Words for .NET'i kullanarak bu bilgiyi kendi Word belgelerinizdeki revizyonları etkili bir şekilde yönetmek için uygulayabilirsiniz.

### SSS

#### S: Aspose.Words for .NET'te revizyon takibini nasıl etkinleştiririm?

#### Çözüm 1:

 C: Aspose.Words for .NET'te revizyon izlemeyi etkinleştirmek için`StartTrackRevisions` yöntemi`Document` nesneyi seçin ve revizyon takibi için yazar adını ve başlangıç tarihini belirtin.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Çözüm 2:

 C: Ayrıca revizyon takibini aşağıdaki komutu kullanarak da etkinleştirebilirsiniz:`Document` kabul eden yapıcı`trackRevisions`Ve`author` parametreler.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### S: Aspose.Words for .NET ile bir belgedeki tüm değişiklikler nasıl kabul edilir?

 C: Kullan`AcceptAllRevisions` yöntemi`Document` belgede yapılan tüm değişiklikleri kabul etmeye itiraz edin.

```csharp
doc.AcceptAllRevisions();
```

#### S: Değiştirilen bir belgeyi kabul edilen düzeltmelerle nasıl kaydedebilirim?

 Kullan`Save` yöntemi`Document` Değiştirilen belgeyi kabul edilen revizyonlarla kaydetmeye itiraz edin. Doğru dosya yolunu sağladığınızdan emin olun.

```csharp
doc.Save("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te revizyonları izlemeyi nasıl durdurabilirim?

 C: Kullan`StopTrackRevisions` yöntemi`Document` İzleme revizyonlarını durdurmaya itiraz edin.

```csharp
doc.StopTrackRevisions();
```

#### S: Aspose.Words for .NET ile bir belgedeki revize edilmiş bir paragrafı nasıl silebilirim?

 C: Bir belgedeki gözden geçirilmiş bir paragrafı kaldırmak için`Remove` Paragraf toplama yöntemi.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```