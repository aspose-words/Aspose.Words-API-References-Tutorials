---
title: Yer İmlerine Erişim
linktitle: Yer İmlerine Erişim
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki yer imlerine nasıl erişeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/access-bookmarks/
---

Bu makalede, Aspose.Words for .NET kitaplığında Access Bookmarks işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir Word belgesindeki belirli yer imlerine erişim sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Belgeyi yükleme

 Yer imlerine erişmeye başlamadan önce Aspose.Words for .NET kullanarak bir Word belgesi yüklememiz gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` belge dosyası yolunu belirten nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## 2. Adım: Yer imlerine erişim

Belge yüklendikten sonra, belgedeki yer imlerine erişebiliriz. Yer imlerine erişmenin iki yolu vardır: dizine göre ve ada göre.

- Dizine göre erişim: Örneğimizde, belgenin ilk yer imine erişmek için 0 dizinini kullanıyoruz:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Ada göre erişim: Örneğimizde, belgedeki belirli bir yer imine erişmek için "MyBookmark3" adını kullanıyoruz:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Aspose.Words for .NET kullanan Access Bookmarks için örnek kaynak kodu

Aspose.Words for .NET kullanarak yer imlerine erişimi gösteren tam örnek kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Dizine göre:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// İsimle:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Access Bookmarks özelliğinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Dizin ve ad kullanarak bir belge yüklemek ve yer imlerine erişmek için adım adım bir kılavuz izledik.