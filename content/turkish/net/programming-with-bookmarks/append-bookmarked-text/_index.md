---
title: Yer İşaretli Metni Word Belgesine Ekle
linktitle: Yer İşaretli Metni Word Belgesine Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET kullanarak yer imli metni bir Word belgesine nasıl ekleyeceğinizi öğrenin. Geliştiriciler için mükemmel.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/append-bookmarked-text/
---
## giriiş

Selam! Hiç bir Word belgesinin yer imlerine eklenmiş bir bölümünden metin eklemeyi denediniz mi ve bunu zor buldunuz mu? Şanslısın! Bu eğitim Aspose.Words for .NET'i kullanarak süreç boyunca size yol gösterecektir. Kolayca takip edebilmeniz için bunu basit adımlara ayıracağız. Haydi hemen dalalım ve yer imlerine eklenen metnin bir profesyonel gibi eklenmesini sağlayalım!

## Önkoşullar

Başlamadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

-  Aspose.Words for .NET: Yüklediğinizden emin olun. Değilse, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio gibi herhangi bir .NET geliştirme ortamı.
- Temel C# Bilgisi: Temel C# programlama kavramlarını anlamak yardımcı olacaktır.
- Yer İşaretli Word Belgesi: Metin eklemek için kullanacağımız, yer imleri ayarlanmış bir Word belgesi.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu, ihtiyacımız olan tüm araçların parmaklarımızın ucunda olmasını sağlayacaktır.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

Örneği ayrıntılı adımlara ayıralım.

## Adım 1: Belgeyi Yükleyin ve Değişkenleri Başlatın

Pekala, Word belgemizi yükleyerek ve ihtiyaç duyacağımız değişkenleri başlatarak başlayalım.

```csharp
// Kaynak ve hedef belgeleri yükleyin.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Belge içe aktarıcısını başlatın.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Kaynak belgedeki yer işaretini bulun.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Adım 2: Başlangıç ve Bitiş Paragraflarını Belirleyin

Şimdi yer iminin başladığı ve bittiği paragrafları bulalım. Metni bu sınırlar içinde ele almamız gerektiğinden bu çok önemlidir.

```csharp
// Bu, yer iminin başlangıcını içeren paragraftır.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// Bu, yer iminin sonunu içeren paragraftır.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## 3. Adım: Paragraf Üst Öğelerini Doğrulayın

Başlangıç ve bitiş paragraflarının aynı ebeveyne sahip olduğundan emin olmalıyız. Bu, işleri basit tutmak için basit bir senaryodur.

```csharp
// Kendimizi oldukça basit bir senaryoyla sınırlayalım.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## Adım 4: Durdurulacak Düğümü Belirleyin

Daha sonra metin kopyalamayı durduracağımız düğümü belirlememiz gerekiyor. Bu, bitiş paragrafından hemen sonraki düğüm olacaktır.

```csharp
// Tüm paragrafları başlangıç paragrafından bitiş paragrafına kadar (ve dahil) kopyalamak istiyoruz,
// dolayısıyla duracağımız düğüm son paragraftan sonraki düğümdür.
Node endNode = endPara.NextSibling;
```

## 5. Adım: Yer İşaretli Metni Hedef Belgeye Ekleme

Son olarak, başlangıç paragrafından bitiş paragrafından sonraki düğüme kadar düğümler arasında döngü yapalım ve bunları hedef belgeye ekleyelim.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Bu, mevcut düğümün bir kopyasını oluşturur ve onu bağlamda içe aktarır (geçerli kılar)
    // hedef belgenin. İçe aktarma, stilleri ve liste tanımlayıcılarını doğru şekilde ayarlamak anlamına gelir.
    Node newNode = importer.ImportNode(curNode, true);

    // İçe aktarılan düğümü hedef belgeye ekleyin.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Hedef belgeyi eklenen metinle birlikte kaydedin.
dstDoc.Save("appended_document.docx");
```

## Çözüm

İşte buyur! Aspose.Words for .NET'i kullanarak bir Word belgesindeki yer imlerine eklenmiş bir bölümdeki metni başarıyla eklediniz. Bu güçlü araç, belge üzerinde değişiklik yapmayı çocuk oyuncağı haline getiriyor ve artık elinizde bir numara daha var. Mutlu kodlama!

## SSS'ler

### Tek seferde birden fazla yer iminden metin ekleyebilir miyim?
Evet, her yer imi için işlemi tekrarlayabilir ve metni buna göre ekleyebilirsiniz.

### Başlangıç ve bitiş paragraflarının üst öğeleri farklıysa ne olur?
Mevcut örnek, aynı ebeveyne sahip olduklarını varsaymaktadır. Farklı ebeveynler için daha karmaşık bir işlem gereklidir.

### Eklenen metnin orijinal formatını koruyabilir miyim?
 Kesinlikle!`ImportFormatMode.KeepSourceFormatting` orijinal formatın korunmasını sağlar.

### Hedef belgedeki belirli bir konuma metin eklemek mümkün müdür?
Evet, hedef belgede istediğiniz düğüme giderek metni herhangi bir konuma ekleyebilirsiniz.

### Bir yer imindeki metni yeni bir bölüme eklemem gerekirse ne olur?
Hedef belgede yeni bir bölüm oluşturabilir ve metni buraya ekleyebilirsiniz.