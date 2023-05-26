---
title: Yer İşareti Sonuna Taşı
linktitle: Yer İşareti Sonuna Taşı
second_title: Aspose.Words for .NET API Referansı
description: Bu adım adım kılavuz ile Word belgelerinde bir yer iminin sonuna gitmek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-bookmark-end/
---

Bu örnekte, Aspose.Words for .NET'in Yer İşareti Sonuna Taşı özelliğini inceleyeceğiz. Aspose.Words, geliştiricilerin Word belgelerini program aracılığıyla oluşturmasına, değiştirmesine ve dönüştürmesine olanak sağlayan güçlü bir belge işleme kitaplığıdır. Yer İmi Sonuna Taşı özelliği, bir belgedeki belirli bir yer iminin sonuna gitmemizi ve ondan sonra içerik eklememizi sağlar.

## ortamın ayarlanması

Uygulama ayrıntılarına girmeden önce, Aspose.Words for .NET ile çalışmak için gerekli ortama sahip olduğumuzdan emin olalım. Aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığının çalışan bir kurulumu
- C# programlama dili hakkında temel bilgi
- .NET geliştirme ortamına erişim

## Aspose.Words for .NET'in Yer İşareti Sonuna Taşı özelliğini anlama

Yer İşareti Sonuna Taşı özelliği, Aspose.Words for .NET'i kullanarak bir Word belgesi içindeki bir yer işaretinin sonuna gitmenizi sağlar. Bu özellik, belgenizdeki belirli bir yer iminden sonra programlı olarak içerik eklemek istediğinizde kullanışlıdır.

## Kaynak kodunu adım adım açıklama

Aspose.Words for .NET'te Yer İşareti Sonuna Taşı özelliğinin nasıl kullanılacağını anlamak için sağlanan kaynak kodunu adım adım inceleyelim.

## 1. Adım: Belge ve belge oluşturucuyu başlatma

 İlk olarak, başlatmamız gerekiyor`Document` Ve`DocumentBuilder` nesneler:

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Yer imi sonuna gitme

 Bir yer iminin sonuna gitmek için`MoveToBookmark` yöntemi`DocumentBuilder` sınıf:

```csharp
builder.MoveToBookmark("MyBookmark1", false, true);
```

 bu`MoveToBookmark` yöntem üç parametre alır:
- Yer imi adı: Taşımak istediğiniz yer işaretinin adını girin.
-  IsBookmarkStart: olarak ayarlayın`false` yer iminin sonuna gitmek için
-  IsBookmarkEnd: olarak ayarlayın`true` yer imi sonuna gitmek istediğinizi belirtmek için

## 3. Adım: Yer iminin sonuna içerik ekleme

Yer imi sonuna geldiğinizde, tarafından sağlanan çeşitli yöntemleri kullanarak içerik ekleyebilirsiniz.`DocumentBuilder` sınıf. Bu örnekte,`Writeln` bir metin satırı yazma yöntemi:

```csharp
builder.Writeln("This is a bookmark.");
```

 bu`Writeln` yöntem, belirtilen metni yeni bir paragraf olarak metnin geçerli konumuna ekler.`DocumentBuilder`.

### Aspose.Words for .NET kullanarak Yer İşareti Sonuna Taşı için örnek kaynak kodu

```csharp

	Document doc = new Document(MyDir + "Bookmarks.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToBookmark("MyBookmark1", false, true);
	builder.Writeln("This is a bookmark.");
	
```

## Çözüm

Aspose.Words for .NET'in Yer İşareti Sonuna Taşı özelliğini inceledik. Bir yer iminin sonuna gitmeyi ve sağlanan kaynak kodunu kullanarak programlı olarak içerik eklemeyi öğrendik. Bu özellik, Aspose.Words for .NET kullanarak Word belgelerinin işlenmesinde esneklik sağlar.

