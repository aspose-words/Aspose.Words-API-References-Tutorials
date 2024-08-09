---
title: İzlenen Belgedeki Düğümü Taşı
linktitle: İzlenen Belgedeki Düğümü Taşı
second_title: Aspose.Words Belge İşleme API'si
description: Ayrıntılı, adım adım kılavuzumuzla Aspose.Words for .NET kullanarak izlenen bir Word belgesindeki düğümleri nasıl taşıyacağınızı öğrenin. Geliştiriciler için mükemmel.
type: docs
weight: 10
url: /tr/net/working-with-revisions/move-node-in-tracked-document/
---
## giriiş

Merhaba Aspose.Words tutkunları! Düzeltmeleri izlerken bir Word belgesindeki bir düğümü taşımanız gerekiyorsa doğru yerdesiniz. Bugün bunu Aspose.Words for .NET kullanarak nasıl başaracağımızı inceliyoruz. Yalnızca adım adım süreci öğrenmekle kalmayacak, aynı zamanda belge işlemlerinizi sorunsuz ve verimli hale getirmek için bazı ipuçları ve püf noktaları da öğreneceksiniz.

## Önkoşullar

Bazı kodlarla elimizi kirletmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

-  Aspose.Words for .NET: İndirin[Burada](https://releases.aspose.com/words/net/).
- .NET Ortamı: Uyumlu bir .NET geliştirme ortamı kurduğunuzdan emin olun.
- Temel C# Bilgisi: Bu eğitimde, C# hakkında temel bilgiye sahip olduğunuz varsayılmaktadır.

Herşeyi aldın mı? Harika! Şimdi içe aktarmamız gereken ad alanlarına geçelim.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmamız gerekiyor. Bunlar Aspose.Words ile çalışmak ve belge düğümlerini yönetmek için gereklidir.

```csharp
using Aspose.Words;
using System;
```

Peki, süreci yönetilebilir adımlara ayıralım. Her noktada neler olduğunu anlamanızı sağlamak için her adım ayrıntılı olarak açıklanacaktır.

## 1. Adım: Belgeyi Başlatın

 Başlamak için yeni bir belge başlatmamız ve bir`DocumentBuilder` bazı paragraflar eklemek için.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bazı paragraflar ekleme
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");

// İlk paragraf sayısını kontrol edin
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## 2. Adım: Düzeltmeleri İzlemeye Başlayın

Daha sonra revizyonları izlemeye başlamamız gerekiyor. Bu, belgede yapılan değişiklikleri görmemize olanak tanıdığı için çok önemlidir.

```csharp
// Revizyonları izlemeye başlayın
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## 3. Adım: Düğümleri Taşı

Şimdi görevimizin temel kısmı geliyor: bir düğümü bir konumdan diğerine taşımak. Üçüncü paragrafı taşıyıp ilk paragrafın önüne yerleştireceğiz.

```csharp
// Taşınacak düğümü ve bitiş aralığını tanımlayın
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];

// Düğümleri tanımlanan aralıkta taşıyın
while (node != endNode)
{
    Node nextNode = node.NextSibling;
    body.InsertBefore(node, referenceNode);
    node = nextNode;
}
```

## 4. Adım: Düzeltmeleri İzlemeyi Durdurun

Düğümleri taşıdıktan sonra revizyonları izlemeyi durdurmamız gerekir.

```csharp
// Revizyonları izlemeyi durdur
doc.StopTrackRevisions();
```

## Adım 5: Belgeyi Kaydedin

Son olarak değiştirdiğimiz belgemizi belirtilen dizine kaydedelim.

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");

// Son paragraf sayısının çıktısını alın
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak takip edilen bir belgedeki bir düğümü başarıyla taşıdınız. Bu güçlü kitaplık, Word belgelerini programlı olarak yönetmeyi kolaylaştırır. İster oluşturuyor, ister düzenliyor, ister değişiklikleri izliyor olun, Aspose.Words yanınızdadır. Öyleyse devam edin ve deneyin. Mutlu kodlama!

## SSS'ler

### Aspose.Words for .NET nedir?

Aspose.Words for .NET, Word belgeleriyle programlı olarak çalışmak için kullanılan bir sınıf kütüphanesidir. Geliştiricilerin .NET uygulamaları içinde Word belgeleri oluşturmasına, düzenlemesine, dönüştürmesine ve yazdırmasına olanak tanır.

### Aspose.Words'ü kullanarak bir Word belgesindeki revizyonları nasıl izlerim?

 Revizyonları izlemek için şunu kullanın:`StartTrackRevisions` konusundaki yöntem`Document` nesne. Bu, belgede yapılan değişiklikleri gösteren revizyon takibini etkinleştirecektir.

### Aspose.Words'te birden fazla düğümü taşıyabilir miyim?

Evet, birden fazla düğümü üzerlerinde yineleyerek ve aşağıdaki gibi yöntemleri kullanarak taşıyabilirsiniz:`InsertBefore` veya`InsertAfter` bunları istediğiniz yere yerleştirmek için.

### Aspose.Words'te revizyonları izlemeyi nasıl durdurabilirim?

 Kullanın`StopTrackRevisions` konusundaki yöntem`Document` revizyonları izlemeyi durdurmaya itiraz edin.

### Aspose.Words for .NET hakkında daha fazla belgeyi nerede bulabilirim?

 Ayrıntılı belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).