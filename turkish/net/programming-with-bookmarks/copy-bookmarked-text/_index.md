---
title: Yer İşaretli Metni Word Belgesinde Kopyala
linktitle: Yer İşaretli Metni Word Belgesinde Kopyala
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak word belgesindeki yer imi metnini başka bir belgeye nasıl kopyalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/copy-bookmarked-text/
---

Bu makalede, Aspose.Words for .NET kitaplığında Yer İşaretli Metni Kopyala işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belirli bir yer iminin içeriğini bir kaynak belgeden başka bir belgeye kopyalamanıza olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Kaynak Belgeyi Yükleme

 Yer imi metnini kopyalamadan önce, kaynak belgeyi bir`Document` dosya yolunu kullanarak nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## 2. Adım: Kaynak yer imini alma

 biz kullanıyoruz`Bookmarks` kopyalamak istediğimiz belirli yer işaretini almak için kaynak belge aralığının özelliği:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## 3. Adım: Hedef belgeyi oluşturma

Yer imi içeriğini kopyalamak için hedef belge görevi görecek yeni bir belge oluşturuyoruz:

```csharp
Document dstDoc = new Document();
```

## 4. Adım: Kopyalama Konumunun Belirlenmesi

Kopyalanan metni eklemek istediğimiz konumu belirtiyoruz. Örneğimizde, metni hedef belgenin son bölümünün gövdesinin sonuna ekliyoruz:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## 5. Adım: Yer imi metnini içe aktarın ve kopyalayın

 biz bir`NodeImporter` yer imi metnini kaynak belgeden hedef belgeye içe aktarmak ve kopyalamak için nesne:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Aspose.Words for .NET kullanarak Yer İşaretli Metni Kopyalamak için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir yer iminden metin kopyalamayı gösteren tam örnek kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Bu, içeriğini kopyalamak istediğimiz yer imidir.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Bu belgeye eklemeler yapacağız.
	Document dstDoc = new Document();

	//Diyelim ki son bölümün gövdesinin sonuna ekleyeceğiz.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Tek bir bağlam olmadan birden çok kez içe aktarırsanız, birçok stil oluşturulur.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Çözüm

Bu makalede, Aspose.Words for .NET'ten Yer İşaretli Metni Kopyala işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir yer iminin içeriğini bir kaynak belgeden başka bir belgeye kopyalamak için adım adım bir kılavuz izledik.

### Word belgesinde yer imi eklenmiş metni kopyalamak için SSS

#### S: Aspose.Words for .NET'te "Metni yer imleriyle kopyala" özelliğini kullanmak için gereksinimler nelerdir?

C: Aspose.Words for .NET'teki "Metni yer imleriyle birlikte kopyala" özelliğini kullanmak için temel C# dili bilgisine sahip olmanız gerekir. Ayrıca Aspose.Words kütüphanesinin kurulu olduğu bir .NET geliştirme ortamına ihtiyacınız var.

#### S: Bir kaynak belgeyi Aspose.Words for .NET'e nasıl yüklerim?

 C: Aspose.Words for .NET'e bir kaynak belge yüklemek için`Document`Belgenin dosya yolunu belirterek sınıf. İşte örnek bir kod:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### S: Aspose.Words for .NET kullanarak bir kaynak belgedeki belirli bir yer iminin içeriği nasıl elde edilir?

 C: Aspose.Words for .NET kullanarak bir kaynak belgedeki belirli bir yer iminin içeriğini almak için şuraya erişebilirsiniz:`Bookmarks` kaynak belge aralığının özelliğini kullanın ve belirli yer imini almak için yer imi adını kullanın. İşte örnek bir kod:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### S: Aspose.Words for .NET kullanarak bir hedef belgedeki yer imi metin kopyasının konumu nasıl belirlenir?

 C: Aspose.Words for .NET kullanarak bir hedef belgede kopyalanan yer imi metnini nereye eklemek istediğinizi belirtmek için hedef belgenin son bölümünün gövdesine gidebilirsiniz. kullanabilirsiniz`LastSection` son bölüme erişmek için özellik ve`Body` o bölümün gövdesine erişmek için özellik. İşte örnek bir kod:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### S: Yer imi metni kaynak belgeden hedef belgeye Aspose.Words for .NET kullanılarak nasıl aktarılır ve kopyalanır?

Y: Aspose.Words for .NET kullanarak yer imi metnini kaynak belgeden hedef belgeye içe aktarmak ve kopyalamak için`NodeImporter` saklanacak kaynak belgeyi, hedef belgeyi ve biçimlendirme modunu belirten sınıf. Sonra kullanabilirsiniz`AppendBookmarkedText` yer imi metnini hedef belgeye ekleme yöntemi. İşte örnek bir kod:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### S: Yer imi metnini Aspose.Words for .NET kullanarak kopyaladıktan sonra bir hedef belge nasıl kaydedilir?

 Y: Aspose.Words for .NET kullanarak bir yer iminden metin kopyaladıktan sonra bir hedef belgeyi kaydetmek için`Save` yöntemi`Document` hedef dosya yolunu belirten nesne. İşte örnek bir kod:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```