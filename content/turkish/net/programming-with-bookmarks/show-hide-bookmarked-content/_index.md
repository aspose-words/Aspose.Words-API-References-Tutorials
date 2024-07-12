---
title: Word Belgesinde Yer İşaretli İçeriği Gizle'yi Göster
linktitle: Word Belgesinde Yer İşaretli İçeriği Gizle'yi Göster
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı adım adım kılavuzla Aspose.Words for .NET kullanarak Word belgelerinde yer imlerine eklenmiş içeriği dinamik olarak nasıl göstereceğinizi veya gizleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## giriiş

Selam! Belirli koşullara bağlı olarak bir Word belgesindeki belirli içeriğin görünürlüğünü hiç kontrol etmek istediniz mi? Aspose.Words for .NET ile, yer imlerine eklenmiş içeriği yalnızca birkaç satır kodla dinamik olarak gösterebilir veya gizleyebilirsiniz. Bu eğitimde, kodun her bir bölümünü anladığınızdan emin olmak için size süreç boyunca adım adım yol göstereceğim. Sonunda, Word belgelerindeki yer işaretlerini değiştirme konusunda uzman olacaksınız. Başlayalım!

## Önkoşullar

Eğiticiye dalmadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1. Temel C# Bilgisi: C# sözdizimi ve kavramları konusunda rahat olmalısınız.
2.  Aspose.Words for .NET: İndirin[Burada](https://releases.aspose.com/words/net/) . Satın almaya hazır değilseniz, bir tane ile başlayabilirsiniz.[ücretsiz deneme](https://releases.aspose.com/).
3. Visual Studio: En yeni sürümlerden herhangi biri çalışacaktır ancak en son sürümün kullanılması önerilir.
4. .NET Framework: Makinenizde kurulu olduğundan emin olun.

başlamaya hazır mısın? Harika! Gerekli ad alanlarını içe aktararak başlayalım.

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET'i kullanmak için gerekli ad alanlarını içe aktarmamız gerekir. Bu adım, kullanacağımız tüm sınıflara ve yöntemlere erişebilmemizi sağlar.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Bu ad alanları, Word belgeleriyle çalışmak ve içeriklerini değiştirmek için çok önemlidir.

## Adım 1: Belgeyi Ayarlama

Öncelikle yeni bir Word belgesi ve belge oluşturucu oluşturalım. Belge oluşturucu, belge içindeki içeriği kolayca eklememize ve değiştirmemize yardımcı olur.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Bu adımda yeni bir belge ve belge oluşturucuyu başlatıyoruz. Bu, daha sonraki işlemler için ortamımızı hazırlar.

## 2. Adım: Yer İmlerine Eklenen İçerik Ekleme

Daha sonra belgeye biraz içerik ekleyeceğiz ve çevresinde bir yer işareti oluşturacağız. Bu yer imi, içeriği tanımlamamıza ve değiştirmemize yardımcı olacaktır.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Burada, yer imlerine eklenen içeriğin öncesine ve sonrasına bir miktar metin ekliyoruz.`StartBookmark`Ve`EndBookmark` yöntemler yer iminin sınırlarını tanımlar.

## 3. Adım: Koşullu Alan Ekleme

Yer imlerine eklenen içeriğin görünürlüğünü kontrol etmek için koşullu bir alan kullanacağız. Bu alan bir koşulu kontrol edecek ve içeriği buna göre görüntüleyecek veya gizleyecektir.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

Bu adımda yer iminin değerini kontrol eden bir IF alanı ekliyoruz. Değer "true" ise "Görünür" olarak görüntülenir; aksi takdirde "Gizli" ifadesi görüntülenir.

## Adım 4: Düğümleri Yeniden Düzenleme

Daha sonra, koşullu mantığın yer imlerine eklenen içeriğe doğru şekilde uygulanmasını sağlamak için düğümleri yeniden düzenlememiz gerekir.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Burada, koşulun yer imlerine eklenen içeriği uygun şekilde kapsadığından emin olmak için düğümleri hareket ettiririz.

## Adım 5: Adres Mektup Birleştirmeyi Yürütme

Son olarak, yer işaretinin değerini ayarlamak ve içeriğin gösterilmesi mi yoksa gizlenmesi mi gerektiğine karar vermek için adres-mektup birleştirme işlemi gerçekleştireceğiz.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Bu adım, yer imi değerini "true" olarak ayarlar, bu da içeriğin durumumuza göre görünür olmasını sağlar.

## Adım 6: Belgeyi Kaydetme

Tüm manipülasyonlardan sonra son adım, değiştirilen belgeyi kaydetmektir.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Burada değişiklikleri belirtmek için belgeyi açıklayıcı bir dosya adıyla kaydediyoruz.

## Çözüm

 Ve bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesinde yer imlerine eklenmiş içeriği nasıl göstereceğinizi veya gizleyeceğinizi başarıyla öğrendiniz. Bu eğitimde belge oluşturma, yer işaretleri ekleme, koşullu alanlar ekleme, düğümleri yeniden düzenleme ve adres-mektup birleştirme yürütme konuları ele alındı. Aspose.Words çok sayıda özellik sunar; bu nedenle, keşfetmekten çekinmeyin.[API belgeleri](https://reference.aspose.com/words/net/) daha gelişmiş yetenekler için.

## SSS

### 1. Aspose.Words for .NET nedir?

Aspose.Words for .NET, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır. Belge otomasyonu görevleri için yaygın olarak kullanılır.

### 2. Aspose.Words for .NET'i ücretsiz kullanabilir miyim?

 Aspose.Words for .NET'i kullanarak deneyebilirsiniz.[ücretsiz deneme](https://releases.aspose.com/). Uzun süreli kullanım için lisans satın almanız gerekir.

### 3. Bir yer iminin diğer özelliklerini nasıl değiştirebilirim?

 Aspose.Words, bir yer iminin metni ve konumu gibi çeşitli özelliklerini değiştirmenize olanak tanır. Bakın[API belgeleri](https://reference.aspose.com/words/net/) ayrıntılı talimatlar için.

### 4. Aspose.Words for .NET desteğini nasıl alabilirim?

adresini ziyaret ederek destek alabilirsiniz.[Aspose destek forumu](https://forum.aspose.com/c/words/8).

### 5. Aspose.Words for .NET ile diğer içerik türlerini değiştirebilir miyim?

Evet, Aspose.Words for .NET; metin, görseller, tablolar ve daha fazlası dahil olmak üzere çeşitli içerik işleme türlerini destekler.