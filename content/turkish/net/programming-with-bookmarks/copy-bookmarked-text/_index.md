---
title: Yer İşaretli Metni Word Belgesine Kopyala
linktitle: Yer İşaretli Metni Word Belgesine Kopyala
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak word belgesindeki yer imi metnini başka bir belgeye nasıl kopyalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/copy-bookmarked-text/
---

Bu makalede, Aspose.Words for .NET kütüphanesinde Yer İşaretli Metni Kopyala fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belirli bir yer iminin içeriğini kaynak belgeden başka bir belgeye kopyalamanıza olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## Adım 1: Kaynak Belgeyi Yükleme

 Yer imi metnini kopyalamadan önce kaynak belgeyi bir`Document` dosya yolunu kullanan nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## 2. Adım: Kaynak yer işaretini alma

 biz kullanıyoruz`Bookmarks` kopyalamak istediğimiz belirli yer imini almak için kaynak belge aralığının özelliği:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## 3. Adım: Hedef belgeyi oluşturma

Yer imi içeriğini kopyalamak için hedef belge görevi görecek yeni bir belge oluşturuyoruz:

```csharp
Document dstDoc = new Document();
```

## Adım 4: Kopyalama Konumunu Belirleme

Kopyalanan metni eklemek istediğimiz konumu belirtiyoruz. Örneğimizde metni, hedef belgenin son bölümünün gövdesinin sonuna ekliyoruz:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## 5. Adım: Yer imi metnini içe aktarın ve kopyalayın

 Bir kullanıyoruz`NodeImporter`Yer imi metnini kaynak belgeden hedef belgeye aktarmak ve kopyalamak için kullanılan nesne:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Aspose.Words for .NET kullanarak Yer İşaretli Metni Kopyalamak için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir yer iminden metin kopyalamayı gösteren örnek kaynak kodunun tamamını burada bulabilirsiniz:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Bu, içeriğini kopyalamak istediğimiz yer imidir.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Bu belgeye ekleme yapacağız.
	Document dstDoc = new Document();

	// Diyelim ki son bölümün gövdesinin sonuna ekleneceğiz.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Tek bir bağlam olmadan birden çok kez içe aktarırsanız, birçok stilin oluşturulmasına neden olur.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Çözüm

Bu makalede, Aspose.Words for .NET'ten Yer İşaretli Metni Kopyala fonksiyonunun nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir yer iminin içeriğini kaynak belgeden başka bir belgeye kopyalamak için adım adım bir kılavuz izledik.

### Yer imlerine eklenen metni word belgesine kopyalamaya ilişkin SSS

#### S: Aspose.Words for .NET'te "Metni yer imleriyle kopyala" özelliğini kullanmak için gereksinimler nelerdir?

C: Aspose.Words for .NET'teki "Metni yer işaretleriyle kopyala" özelliğini kullanmak için temel C# dili bilgisine sahip olmanız gerekir. Ayrıca Aspose.Words kütüphanesinin kurulu olduğu bir .NET geliştirme ortamına da ihtiyacınız var.

#### S: Kaynak belgeyi Aspose.Words for .NET'e nasıl yüklerim?

 C: Aspose.Words for .NET'e kaynak belge yüklemek için`Document` belgenin dosya yolunu belirterek sınıf. İşte örnek bir kod:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### S: Aspose.Words for .NET kullanarak kaynak belgedeki belirli bir yer iminin içeriğine nasıl ulaşılır?

 C: Aspose.Words for .NET'i kullanarak kaynak belgedeki belirli bir yer iminin içeriğini almak için şuraya erişebilirsiniz:`Bookmarks` kaynak belge aralığının özelliğini kullanın ve belirli bir yer imini almak için yer imi adını kullanın. İşte örnek bir kod:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### S: Aspose.Words for .NET kullanılarak hedef belgedeki yer imi metni kopyasının konumu nasıl belirlenir?

C: Aspose.Words for .NET kullanarak kopyalanan yer imi metnini hedef belgede nereye eklemek istediğinizi belirtmek için hedef belgenin son bölümünün gövdesine gidebilirsiniz. Şunu kullanabilirsiniz:`LastSection` son bölüme erişim özelliği ve`Body` o bölümün gövdesine erişme özelliği. İşte örnek bir kod:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### S: Aspose.Words for .NET kullanılarak yer imi metni kaynak belgeden hedef belgeye nasıl aktarılır ve kopyalanır?

 C: Yer imi metnini Aspose.Words for .NET kullanarak kaynak belgeden hedef belgeye aktarmak ve kopyalamak için şu komutu kullanabilirsiniz:`NodeImporter` Kaynak belgeyi, hedef belgeyi ve saklanacak biçimlendirme modunu belirten sınıf. Daha sonra şunu kullanabilirsiniz:`AppendBookmarkedText` Yer imi metnini hedef belgeye ekleme yöntemini kullanın. İşte örnek bir kod:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### S: Aspose.Words for .NET kullanarak yer imi metnini kopyaladıktan sonra hedef belge nasıl kaydedilir?

C: Aspose.Words for .NET'i kullanarak bir yer iminden metin kopyaladıktan sonra hedef belgeyi kaydetmek için,`Save` yöntemi`Document` Hedef dosya yolunu belirten nesne. İşte örnek bir kod:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```