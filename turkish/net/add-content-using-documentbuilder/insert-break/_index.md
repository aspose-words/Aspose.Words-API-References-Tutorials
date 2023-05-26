---
title: Mola Ekle
linktitle: Mola Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerine nasıl sayfa sonları ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-break/
---

Bu kapsamlı örnekte, Aspose.Words for .NET'te InsertBreak yöntemini kullanarak bir Word belgesine nasıl sayfa sonları ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, belgenizdeki sayfa sonlarını kontrol edebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: İçerik ve Sayfa Sonları Ekleyin
Ardından, belgeye içerik eklemek için DocumentBuilder sınıfının Writeln yöntemini kullanın. Sayfa sonu eklemek için, BreakType.PageBreak parametresiyle InsertBreak yöntemini kullanın:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## 3. Adım: Belgeyi Kaydedin
İçeriği ve sayfa sonlarını ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Aspose.Words for .NET kullanan Insert Break için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak sayfa sonları eklemek için eksiksiz kaynak kodu burada:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("This is page 1.");
	builder.InsertBreak(BreakType.PageBreak);

	builder.Writeln("This is page 2.");
	builder.InsertBreak(BreakType.PageBreak);

	builder.Writeln("This is page 3.");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
			
```

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.


## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine sayfa sonları eklemeyi başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak, istenen konumlara sayfa sonları ekleyerek artık belgenizin sayfalandırmasını ve düzenini kontrol edebilirsiniz.
