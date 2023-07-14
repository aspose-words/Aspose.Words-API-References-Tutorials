---
title: Word Belgesinde Yer İşaretlerini Gizle'yi Göster
linktitle: Word Belgesinde Yer İşaretlerini Gizle'yi Göster
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak word belgesinde belirli bir yer imini nasıl göstereceğinizi veya gizleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/show-hide-bookmarks/
---

Bu makalede, Aspose.Words for .NET kitaplığında Show Hide Bookmarks işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, kelime belgesinde belirli bir yer imini göstermenizi veya gizlemenizi sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Belgeyi yükleme

 biz kullanıyoruz`Document` varolan belgeyi bir dosyadan yüklemek için sınıf:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## 2. Adım: Belirli bir yer işaretini gösterin veya gizleyin

 biz kullanıyoruz`ShowHideBookmarkedContent` belgedeki belirli bir yer imini gösterme veya gizleme işlevi. Bu işlev, yer iminin gösterilip gösterilmeyeceğini belirtmek için belgeyi, yer iminin adını ve bir boolean parametre olarak alır:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## 3. Adım: Değiştirilen belgeyi kaydetme

 biz kullanıyoruz`Save` değiştirilen belgeyi bir dosyaya kaydetme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Aspose.Words for .NET kullanarak Show Hide Bookmarks için örnek kaynak kodu

Aspose.Words for .NET kullanarak belirli bir yer işaretini göstermeyi veya gizlemeyi gösteren tam örnek kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Show Hide Bookmarks özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belgede belirli bir yer imini göstermek veya gizlemek için adım adım bir kılavuz izledik.

### Word belgesinde yer işaretlerini gösterme ve gizleme hakkında SSS

#### S: Aynı belgede birden çok yer işaretini gösterebilir veya gizleyebilir miyim?

C: Evet, işlemek istediğiniz her yer imi için 2. ve 3. adımları tekrarlayarak aynı belgede birden çok yer işaretini gösterebilir veya gizleyebilirsiniz.

#### S: Sağlanan kod, .doc veya .docm gibi diğer Word belgesi biçimleriyle çalışıyor mu?

C: Evet, sağlanan kod, .doc ve .docm gibi Aspose.Words tarafından desteklenen çeşitli Word belgesi biçimleriyle çalışır. Belgeyi yüklerken ve kaydederken doğru dosya adını ve yolu kullandığınızdan emin olun.

#### S: Gizli bir yer imini tekrar nasıl gösterebilirim?

 C: Gizli bir yer imini tekrar göstermek için aynısını kullanmanız gerekir.`ShowHideBookmarkedContent` değeri geçen işlev`true`yer iminin gösterilip gösterilmeyeceğini belirten boolean parametresi için.

#### S: Belgedeki birleştirme alanı değerlerine dayalı olarak yer imlerini göstermek veya gizlemek için koşulları kullanabilir miyim?

 C: Evet, bir yer iminin gösterilmesi veya gizlenmesi gerektiğini belirlemek için koşulları kullanabilir ve alan değerlerini birleştirebilirsiniz. kodunu özelleştirebilirsiniz.`ShowHideBookmarkedContent` uygun koşulları ve değerleri dikkate alma işlevi.

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki yer imini nasıl silebilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesindeki yer imini kaldırmak için`RemoveBookmarks` yöntemi`Document`sınıf. İşte örnek bir kod:

```csharp
doc.RemoveBookmarks("BookmarkName");
```