---
title: Yer İşaretlerini Gizle'yi Göster
linktitle: Yer İşaretlerini Gizle'yi Göster
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir belgede belirli bir yer imini nasıl göstereceğinizi veya gizleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/show-hide-bookmarks/
---

Bu makalede, Aspose.Words for .NET kitaplığında Show Hide Bookmarks işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgedeki belirli bir yer imini göstermenizi veya gizlemenizi sağlar.

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