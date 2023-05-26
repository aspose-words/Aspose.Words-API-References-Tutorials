---
title: Yeni Belge Oluştur
linktitle: Yeni Belge Oluştur
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak nasıl yeni bir Word belgesi oluşturacağınızı ve içerik ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/create-new-document/
---

Bu adım adım öğreticide, Aspose.Words for .NET kullanarak sıfırdan yeni bir Word belgesi oluşturmayı öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, DocumentBuilder sınıfını kullanarak yeni bir belge oluşturabilecek ve buna içerik ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun:

```csharp
Document doc = new Document();
```

## 2. Adım: Belgeye İçerik Ekleyin
Ardından, belgeye içerik eklemek için bir DocumentBuilder nesnesi kullanın. DocumentBuilder'ı yeni oluşturulan belgeyle başlatın:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## 3. Adım: Belgeyi Kaydedin
İstediğiniz içeriği ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Aspose.Words for .NET kullanarak Yeni Belge Oluşturmak için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yeni bir belge oluşturmak için eksiksiz kaynak kodu burada:

```csharp
Document doc = new Document();

// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Çözüm

Tebrikler! Aspose.Words for .NET kullanarak yeni bir Word belgesi oluşturmayı başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, artık yeni belgeleri program aracılığıyla oluşturabilir ve DocumentBuilder sınıfını kullanarak bunlara içerik ekleyebilirsiniz.

Artık Word belgelerini özel gereksinimlerinize göre güvenle oluşturabilir ve özelleştirebilirsiniz.

### Aspose.Words for .NET kullanarak Yeni Belge Oluşturmak için örnek kaynak kodu:

```csharp
Document doc = new Document();

// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

Belgeyi sisteminizde istediğiniz konuma kaydetmek için koddaki dosya yolunu ve adını ayarlamayı unutmayın.

