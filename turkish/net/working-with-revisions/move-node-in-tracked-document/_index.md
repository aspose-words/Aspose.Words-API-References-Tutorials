---
title: Düğümü İzlenen Belgede Taşı
linktitle: Düğümü İzlenen Belgede Taşı
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile izlenen bir belgedeki düğümleri taşıyın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/move-node-in-tracked-document/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak izlenen bir Word belgesindeki bir düğümü nasıl taşıyacağınız konusunda size yol göstereceğiz. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi oluşturma

İlk adım, yeni bir belge oluşturmak ve paragraflar eklemektir.

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

Belgede revizyon takibini etkinleştireceğiz.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## 3. Adım: Bir düğümü taşıyın

Revizyon oluştururken bir düğümü (paragrafı) bir konumdan diğerine taşıyacağız.

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

Belgedeki düzeltmeleri izlemeyi durduracağız.

```csharp
doc.StopTrackRevisions();
```

## 5. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Aspose.Words for .NET kullanarak İzlenen Belgede Düğümü Taşı için örnek kaynak kodu

Aspose.Words for .NET kullanarak izlenen bir belgede bir düğümü taşımak için tam kaynak kodu burada:


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

// Düzeltmeleri izlemeye başlayın.
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

// Revizyonları izleme sürecini durdurun.
doc.StopTrackRevisions();

// Taşınma aralığında 3 ek paragraf vardır.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

