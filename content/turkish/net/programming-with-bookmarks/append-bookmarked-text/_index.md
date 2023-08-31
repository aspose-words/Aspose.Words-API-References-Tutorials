---
title: Yer İşaretli Metni Word Belgesine Ekle
linktitle: Yer İşaretli Metni Word Belgesine Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki bir yer iminden nasıl metin ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/append-bookmarked-text/
---

Bu makalede, Aspose.Words for .NET kitaplığında Append Bookmarked Text işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir Word belgesinin belirli bir yer iminde bulunan metni başka bir belgeye eklemenizi sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yer İşaretinden Paragrafları Alma

 Yer imi metnini eklemeye başlamadan önce yer imi başlangıç ve bitişini içeren paragrafları almamız gerekiyor. Bu, şu adrese erişerek yapılabilir:`BookmarkStart` Ve`BookmarkEnd` yer iminin özellikleri:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## 2. Adım: Ana Paragrafları Kontrol Edin

Başlangıç ve bitiş paragraflarının geçerli ebeveynleri olup olmadığını, yani gerçekten bir paragrafa ait olup olmadıklarını kontrol ederiz. Değilse, bir istisna oluştururuz:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## 3. Adım: Paragrafların Üst Öğelerini Kontrol Edin

Başlangıç ve bitiş paragraflarının aynı ebeveyne sahip olup olmadığını kontrol ederiz. Değilse, bu, paragrafların aynı bölümde veya belgede yer almadığı anlamına gelir ve bir istisna atıyoruz:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## 4. Adım: Paragrafları kopyalayın

Başlangıç paragrafından bitiş paragrafına kadar düğümler (paragraflar) boyunca yineliyoruz. Her düğüm için bir kopya oluşturur ve bunu hedef belgenin bağlamına aktarırız:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Aspose.Words for .NET kullanarak Bookmarked Text Append için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir yer iminden metin eklemeyi gösteren tam örnek kaynak kodu burada:

```csharp

	// Bu, yer iminin başlangıcını içeren paragraftır.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Bu, yer iminin sonunu içeren paragraftır.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Kendimizi oldukça basit bir senaryo ile sınırlayın.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Başlangıç paragrafından bitiş paragrafına kadar (ve dahil) tüm paragrafları kopyalamak istiyoruz,
	// bu nedenle durduğumuz düğüm, son paragraftan sonradır.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		// Bu, geçerli düğümün bir kopyasını oluşturur ve onu bağlamda içe aktarır (geçerli kılar)
		// hedef belgenin İçe aktarma, stilleri ve liste tanımlayıcılarını doğru şekilde ayarlamak anlamına gelir.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Append Bookmarked Text işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir yer iminden paragrafları almak, ebeveynleri doğrulamak ve paragrafları başka bir belgeye kopyalamak için adım adım bir kılavuz izledik.

### Word belgesinde yer imi eklenmiş metin eklemeyle ilgili SSS

#### S1: Aspose.Words for .NET'te "Yer işaretli metin ekle" özelliğini kullanmanın ön koşulları nelerdir?

C: Aspose.Words for .NET'te "Yer işaretli metin ekle" işlevini kullanmak için temel C# dili bilgisine sahip olmanız gerekir. Ayrıca Aspose.Words kütüphanesinin kurulu olduğu bir .NET geliştirme ortamına ihtiyacınız var.

#### S2: Bir Word belgesinde yer iminin başlangıcını ve sonunu içeren paragraflar nasıl elde edilir?

 C: Bir Word belgesindeki bir yer iminin başlangıcını ve sonunu içeren paragrafları almak için,`BookmarkStart` Ve`BookmarkEnd` yer iminin özellikleri. İşte örnek bir kod:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### S3: Başlangıç ve bitiş paragraflarının geçerli ebeveynleri yoksa ne olur?

C: Başlangıç ve bitiş paragraflarının geçerli ebeveynleri yoksa, yani gerçekten paragraf değillerse, bir istisna atılır. Bu durum şu anda yönetilemez.
