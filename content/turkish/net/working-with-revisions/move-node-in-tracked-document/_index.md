---
title: İzlenen Belgedeki Düğümü Taşı
linktitle: İzlenen Belgedeki Düğümü Taşı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile izlenen bir belgedeki düğümleri taşıyın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/move-node-in-tracked-document/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak izlenen bir Word belgesinde bir düğümün nasıl taşınacağı konusunda size yol göstereceğiz. Size kaynak kodunun tamamını sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi oluşturma

İlk adım yeni bir belge oluşturmak ve paragraflar eklemektir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## 2. Adım: Düzeltmeleri izleyin

Dokümanda revizyon takibini aktif hale getireceğiz.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## 3. Adım: Bir düğümü taşıyın

Revizyonları oluştururken bir düğümü (paragrafı) bir konumdan diğerine taşıyacağız.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## 4. Adım: İncelemeleri İzlemeyi Durdurun

Belgedeki revizyonları izlemeyi bırakacağız.

```csharp
doc.StopTrackRevisions();
```

## Adım 5: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi kullanarak belgeyi istediğiniz konuma kaydedin.`Save`yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Aspose.Words for .NET kullanarak İzlenen Belgede Düğümü Taşıma için örnek kaynak kodu

Aspose.Words for .NET kullanarak izlenen bir belgedeki bir düğümü taşımak için tam kaynak kodu:


```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Revizyonları izlemeye başlayın.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Bir düğümü bir konumdan diğerine taşırken revizyonlar oluşturun.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Revizyonları takip etme sürecini durdurun.
doc.StopTrackRevisions();

// Geçiş aralığında 3 ek paragraf daha vardır.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak izlenen bir Word belgesindeki bir düğümün nasıl taşınacağını öğrendik. Belge oluşturma, revizyon takibini etkinleştirme, düğümü taşıma ve revizyon takibini durdurma adımlarını takip ederek bu manipülasyonu başarıyla gerçekleştirebildik. Aspose.Words for .NET, Word belgeleriyle Kelime İşleme için güçlü bir araçtır ve revizyonları yönetmek için gelişmiş özellikler sunar. Artık bu bilgiyi Aspose.Words for .NET kullanarak revizyonları takip ederken kendi Word belgelerinizdeki düğümleri taşımak için kullanabilirsiniz.

### SSS'ler

#### S: Bir Aspose.Words for .NET belgesinde revizyon takibini nasıl etkinleştirebilirim?

 C: Bir Aspose.Words for .NET belgesinde revizyon takibini etkinleştirmek için`StartTrackRevisions` yöntemi`Document` nesne. Bu yöntemde revizyon yazarının adı ve revizyon takibinin başlangıç tarihi parametre olarak alınır.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### S: İzlenen bir belgedeki bir düğümü revizyon oluşturmadan nasıl taşıyabilirim?

 C: İzlenen bir belgedeki bir düğümü revizyon oluşturmadan taşımak istiyorsanız,`Remove` Ve`InsertAfter` veya`InsertBefore` yöntemleri`Node` nesne. Örneğin, bir paragrafı başka bir paragraftan sonra taşımak için aşağıdaki kodu kullanabilirsiniz:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### S: Aspose.Words for .NET belgesinde revizyon izlemeyi nasıl durdurabilirim?

 C: Aspose.Words for .NET belgesindeki revizyonları izlemeyi durdurmak için`StopTrackRevisions` yöntemi`Document` nesne.

```csharp
doc.StopTrackRevisions();
```