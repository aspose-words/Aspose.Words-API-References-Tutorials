---
title: Word Belgesinde Yer İşaretlerini Gizle'yi Göster
linktitle: Word Belgesinde Yer İşaretlerini Gizle'yi Göster
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak word belgesinde belirli bir yer imini nasıl göstereceğinizi veya gizleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/show-hide-bookmarks/
---

Bu makalede, Aspose.Words for .NET kütüphanesinde Show Hide Bookmarks fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, word belgesinde belirli bir yer imini göstermenize veya gizlemenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Belgeyi yükleme

 biz kullanıyoruz`Document` Mevcut belgeyi bir dosyadan yüklemek için sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## 2. Adım: Belirli bir yer işaretini gösterin veya gizleyin

 biz kullanıyoruz`ShowHideBookmarkedContent`Belgedeki belirli bir yer imini gösterme veya gizleme işlevi. Bu işlev, belgeyi, yer iminin adını ve yer iminin gösterilip gösterilmeyeceğini veya gizleneceğini belirten bir boole parametresini alır:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## 3. Adım: Değiştirilen belgeyi kaydetme

 biz kullanıyoruz`Save` Değiştirilen belgeyi bir dosyaya kaydetme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Aspose.Words for .NET kullanarak Show Hide Bookmarks için örnek kaynak kodu

Aspose.Words for .NET kullanarak belirli bir yer iminin gösterilmesini veya gizlenmesini gösteren örnek kaynak kodunun tamamını burada bulabilirsiniz:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Show Hide Bookmarks özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belgedeki belirli bir yer imini göstermek veya gizlemek için adım adım bir kılavuz izledik.

### Word belgesinde yer imlerini gizlemeyi göstermeyle ilgili SSS

#### S: Aynı belgede birden fazla yer imini gösterebilir veya gizleyebilir miyim?

C: Evet, işlemek istediğiniz her yer imi için 2. ve 3. adımları tekrarlayarak aynı belgede birden fazla yer imini gösterebilir veya gizleyebilirsiniz.

#### S: Sağlanan kod .doc veya .docm gibi diğer Word belge biçimleriyle çalışıyor mu?

C: Evet, verilen kod Aspose.Words tarafından desteklenen .doc ve .docm gibi çeşitli Word belge formatlarıyla çalışır. Belgeyi yüklerken ve kaydederken doğru dosya adını ve yolunu kullandığınızdan emin olun.

#### S: Gizli bir yer imini tekrar nasıl gösterebilirim?

 C: Gizli bir yer imini tekrar göstermek için aynısını kullanmanız gerekir.`ShowHideBookmarkedContent` değeri ileten fonksiyon`true` yer iminin gösterilip gösterilmeyeceğini belirten boolean parametresi için.

#### S: Belgedeki birleştirme alanı değerlerine göre yer işaretlerini göstermek veya gizlemek için koşulları kullanabilir miyim?

 C: Evet, bir yer işaretinin gösterilmesi mi yoksa gizlenmesi mi gerektiğini belirlemek için koşulları kullanabilir ve alan değerlerini birleştirebilirsiniz. kodunu özelleştirebilirsiniz.`ShowHideBookmarkedContent` uygun koşulları ve değerleri dikkate alacak şekilde çalışır.

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki yer işaretini nasıl silebilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesindeki yer işaretini kaldırmak için şu komutu kullanabilirsiniz:`RemoveBookmarks` yöntemi`Document` sınıf. İşte örnek bir kod:

```csharp
doc.RemoveBookmarks("BookmarkName");
```