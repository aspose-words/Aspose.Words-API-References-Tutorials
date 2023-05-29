---
title: Yatay Kural Ekle
linktitle: Yatay Kural Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerine yatay kuralları nasıl ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-horizontal-rule/
---

Bu kapsamlı örnekte, Aspose.Words for .NET kullanarak bir Word belgesine nasıl yatay bir kural ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, görsel ayırma ve düzenleme için belgelerinize yatay kurallar ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Bir Yatay Kural Ekleyin
Ardından, açıklayıcı bir metin eklemek için DocumentBuilder sınıfının Writeln yöntemini kullanın ve ardından yatay bir kural ekleyin:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## 3. Adım: Belgeyi Kaydedin
Yatay kuralı ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Aspose.Words for .NET kullanarak Yatay Kural Ekleme için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yatay bir kural eklemek için eksiksiz kaynak kodu burada:
Yatay kurallar, bölümleri bölmek, görsel aralar oluşturmak veya önemli bilgileri vurgulamak gibi çeşitli senaryolar için kullanışlıdır.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine yatay bir kuralın nasıl ekleneceğini başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, artık belgelerinizi yatay kurallar kullanarak görsel olarak ayırabilir ve düzenleyebilirsiniz.

