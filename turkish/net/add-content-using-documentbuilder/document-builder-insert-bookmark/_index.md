---
title: Belge Oluşturucu Yer İşareti Ekle
linktitle: Belge Oluşturucu Yer İşareti Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te DocumentBuilder'ı kullanarak Word belgelerine nasıl yer imleri ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

Bu kapsamlı örnekte, Aspose.Words for .NET'te DocumentBuilder sınıfını kullanarak bir Word belgesine nasıl yer imleri ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, belgelerinizde yer imleri oluşturabilecek ve yönetebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Bir Yer İşareti Ekleyin
Ardından, belgeye bir yer işareti eklemek için DocumentBuilder sınıfının StartBookmark ve EndBookmark yöntemlerini kullanın. Yer imi için parametre olarak benzersiz bir ad girin:

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## 3. Adım: Belgeyi Kaydedin
Yer imini ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### Aspose.Words for .NET kullanarak DocumentBuilder Insert Bookmark için Örnek Kaynak Kodu
Aspose.Words for .NET'te DocumentBuilder sınıfını kullanarak bir yer imi eklemek için eksiksiz kaynak kodu burada:

```csharp
   
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("FineBookmark");
	builder.Writeln("This is just a fine bookmark.");
	builder.EndBookmark("FineBookmark");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
	 
```

## Çözüm
Tebrikler! Aspose.Words for .NET'te DocumentBuilder sınıfını kullanarak bir Word belgesine nasıl yer imleri ekleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak artık belgelerinizde yer imleri oluşturabilir ve yönetebilirsiniz.

Yer imleri, büyük belgelerde gezinmek, belirli bölümlere başvurmak veya yer imi eklenmiş alanlardaki içeriği programlı olarak değiştirmek gibi çeşitli senaryolar için kullanışlıdır.

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.

