---
title: Göster Yer İşaretli İçeriği Gizle
linktitle: Göster Yer İşaretli İçeriği Gizle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak yer imi içeriğinin nasıl gösterileceğini veya gizleneceğini öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

Bu makalede, Aspose.Words for .NET kitaplığında Show Hide Bookmarked Content işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, verileri birleştirirken belirli bir koşula dayalı olarak bir yer iminin içeriğini göstermenize veya gizlemenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yer imini alma

 biz kullanıyoruz`Bookmarks` İçeriği göstermek veya gizlemek istediğimiz belirli yer işaretini almak için belge aralığının özelliği:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## 2. Adım: Birleştirme alanlarını ekleme

 Bir belge oluşturucu kullanıyoruz`DocumentBuilder` gerekli birleştirme alanlarını eklemek için. Bu birleştirme alanları, değerine bağlı olarak yer imi içeriğini göstermek veya gizlemek için bir koşul ayarlar.`showHide` değişken:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## 3. Adım: Yer imi içeriğini taşıma

Yer iminin içeriğinde dolaşıyoruz ve görünmesi için hareket ettiriyoruz

yer iminden önce. Bu, belirtilen koşula göre içeriğin gösterilmesini veya gizlenmesini kontrol eder:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## 4. Adım: Yer imi içeriğinin geri kalanını taşıma

Yer işaretinin son düğümünü ekleme noktası olarak kullanarak, yer işareti içeriğinin geri kalanını yer işaretinden sonra taşırız:

```csharp
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

## Adım 5: Birleştirmenin gerçekleştirilmesi

 biz kullanıyoruz`Execute` belge yöntemi`s `Posta birleştirme` object to execute the merge using the bookmark name and the value of the `showHide` değişkeni:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Aspose.Words for .NET kullanarak Yer İşaretli İçeriği Gizle Göster için örnek kaynak kodu

Aspose.Words for .NET kullanarak yer imi içeriğinin gösterilmesini veya gizlenmesini gösteren Kaynak kodunun tam örneği burada:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD bookmark}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Show Hide Bookmarked Content özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Verileri birleştirirken belirli bir koşula bağlı olarak bir yer iminin içeriğini göstermek veya gizlemek için adım adım bir kılavuz izledik.