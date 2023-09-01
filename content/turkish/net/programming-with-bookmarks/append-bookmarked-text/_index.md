---
title: Yer İşaretli Metni Word Belgesine Ekle
linktitle: Yer İşaretli Metni Word Belgesine Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesindeki yer iminden nasıl metin ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/append-bookmarked-text/
---

Bu makalede, Aspose.Words for .NET kütüphanesinde Yer İşaretli Metni Ekle fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir Word belgesinin belirli bir yer iminde bulunan metni başka bir belgeye eklemenizi sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## Adım 1: Yer İminden Paragraf Alma

 Yer imi metnini eklemeye başlamadan önce yer iminin başlangıcını ve sonunu içeren paragrafları almamız gerekir. Bu, şuraya erişilerek yapılabilir:`BookmarkStart` Ve`BookmarkEnd` yer iminin özellikleri:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Adım 2: Ana Paragrafları Kontrol Edin

Başlangıç ve bitiş paragraflarının geçerli üst öğelerinin olup olmadığını, yani gerçekten bir paragrafa ait olup olmadıklarını kontrol ederiz. Değilse, bir istisna oluştururuz:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Adım 3: Paragrafların Ana Öğelerini Kontrol Edin

Başlangıç ve bitiş paragraflarının aynı ebeveyne sahip olup olmadığını kontrol ederiz. Değilse, bu, paragrafların aynı bölümde veya belgede yer almadığı anlamına gelir ve bir istisna atıyoruz:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## 4. Adım: Paragrafları kopyalayın

Başlangıç paragrafından bitiş paragrafına kadar düğümler (paragraflar) arasında yineleniriz. Her düğüm için bir kopya oluşturup bunu hedef belgenin bağlamına aktarıyoruz:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Aspose.Words for .NET kullanarak Yer İşaretli Metni Ekleme için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir yer iminden metin eklemeyi gösteren tam örnek kaynak kodunu burada bulabilirsiniz:

```csharp

	// Bu, yer iminin başlangıcını içeren paragraftır.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Bu, yer iminin sonunu içeren paragraftır.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Kendimizi oldukça basit bir senaryoyla sınırlayalım.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Tüm paragrafları başlangıç paragrafından bitiş paragrafına kadar (ve dahil) kopyalamak istiyoruz,
	// dolayısıyla duracağımız düğüm son paragraftan sonraki düğümdür.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//Bu, mevcut düğümün bir kopyasını oluşturur ve onu bağlamda içe aktarır (geçerli kılar)
		// hedef belgenin. İçe aktarma, stilleri ve liste tanımlayıcılarını doğru şekilde ayarlamak anlamına gelir.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Yer İşaretli Metni Ekle işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir yer iminden paragraf alma, üst öğeleri doğrulama ve paragrafları başka bir belgeye kopyalama konusunda adım adım bir kılavuz izledik.

### Word belgesine yer imli metin eklemeyle ilgili SSS

#### S1: Aspose.Words for .NET'te "Yer işaretleriyle metin ekle" özelliğini kullanmanın önkoşulları nelerdir?

C: Aspose.Words for .NET'te "Yer işaretleriyle metin ekle" işlevini kullanmak için temel C# dili bilgisine sahip olmanız gerekir. Ayrıca Aspose.Words kütüphanesinin kurulu olduğu bir .NET geliştirme ortamına da ihtiyacınız var.

#### S2: Bir Word belgesinde yer işaretinin başlangıcını ve sonunu içeren paragraflar nasıl alınır?

C: Bir Word belgesindeki yer iminin başlangıcını ve sonunu içeren paragraflara ulaşmak için`BookmarkStart` Ve`BookmarkEnd` yer iminin özellikleri. İşte örnek bir kod:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### S3: Başlangıç ve bitiş paragraflarının geçerli üst öğeleri yoksa ne olur?

C: Başlangıç ve bitiş paragraflarının geçerli üst öğeleri yoksa, yani bunlar gerçekten paragraf değilse bir istisna oluşturulacaktır. Bu durum şu anda yönetilemez.
