---
title: Word Belgesinde Yer İşaretli İçeriği Gizle'yi Göster
linktitle: Word Belgesinde Yer İşaretli İçeriği Gizle'yi Göster
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak word belgesindeki yer imi içeriğini nasıl göstereceğinizi veya gizleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

Bu makalede, Aspose.Words for .NET kütüphanesinde Yer İşaretli İçeriği Gizle Göster fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, verileri birleştirirken belirli bir koşula göre word belgesindeki bir yer işaretinin içeriğini göstermenize veya gizlemenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yer işaretini alma

 biz kullanıyoruz`Bookmarks` İçeriği göstermek veya gizlemek istediğimiz belirli yer imini almak için belge aralığının özelliği:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## 2. Adım: Birleştirme alanlarını ekleme

 Bir belge oluşturucu kullanıyoruz`DocumentBuilder` gerekli birleştirme alanlarını eklemek için. Bu birleştirme alanları, yer imi içeriğinin değerine bağlı olarak yer imi içeriğini göstermek veya gizlemek için bir koşul belirleyecektir.`showHide` değişken:

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

Yer iminin içeriğinde dolaşıyoruz ve görünecek şekilde hareket ettiriyoruz

yer iminden önce gelir. Bu, belirtilen koşula göre içeriğin gösterilmesini veya gizlenmesini kontrol edecektir:

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

Yer imi içeriğinin geri kalanını, yer iminin son düğümünü ekleme noktası olarak kullanarak yer iminden sonra taşırız:

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

 biz kullanıyoruz`Execute` belgenin yöntemi`s `Posta birleştirme` object to execute the merge using the bookmark name and the value of the `showHide` değişkeni:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Aspose.Words for .NET kullanarak Yer İşaretli İçeriği Gösterme ve Gizleme için örnek kaynak kodu

Aspose.Words for .NET kullanarak yer imi içeriğini göstermeyi veya gizlemeyi gösteren Kaynak kodunun tam örneği:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD yer imi}" = "true" "" ""}
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

Bu makalede, Aspose.Words for .NET'in Yer İşaretli İçeriği Göster Göster Gizle özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Verileri birleştirirken belirli bir duruma göre yer işaretinin içeriğini göstermek veya gizlemek için adım adım bir kılavuz izledik.

### Word belgesinde yer imlerine eklenen içeriği gizlemeyi gösteren SSS'ler

#### S: Aynı koşulu, aynı belgedeki birden fazla yer imi için kullanabilir miyim?

C: Evet, aynı koşulu aynı belgedeki birden fazla yer imi için kullanabilirsiniz. Yer imi adını ve isteğe bağlı olarak yer imi değerini ayarlayarak her yer imi için 2-5 arasındaki adımları tekrarlayın.`showhide` gerektiği gibi değişken.

#### S: Yer imi içeriğini göstermek veya gizlemek için nasıl daha fazla koşul ekleyebilirim?

 C: Daha fazla koşul eklemek için aşağıdaki gibi mantıksal operatörleri kullanabilirsiniz:`AND` Ve`OR` 2. adımdaki birleştirme alanlarını ekleme kodunda. Ek koşullar eklemek için aşağıdaki koddaki koşulu düzenleyin:

```csharp
builder. Write("\" = \"true\" ");
```

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki yer işaretini nasıl silebilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesindeki yer işaretini kaldırmak için şu komutu kullanabilirsiniz:`Remove` gelen yöntem`Bookmarks` belge aralığının toplanması. Belirli bir yer imini silmek için örnek kod:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### S: Aspose.Words kütüphanesi ücretsiz mi?

 C: Aspose.Words kütüphanesi ticari bir kütüphanedir ve projelerinizde kullanmak için geçerli bir lisans gerektirir. Kontrol edebilirsin[Aspose.Words for .NET API referansları](https://reference.aspose.com/words/net/) Lisanslama seçenekleri ve fiyatlandırma hakkında daha fazla bilgi edinmek için.

#### S: .NET'te Word belgeleriyle Kelime İşleme için kullanılabilen başka kitaplıklar var mı?

C: Evet, .NET'te Word belgeleriyle Kelime İşleme için Open XML SDK ve GemBox.Document gibi başka kitaplıklar da mevcuttur. Özel ihtiyaçlarınıza ve tercihlerinize göre Aspose.Words'e alternatif olarak bu kütüphaneleri inceleyebilirsiniz.