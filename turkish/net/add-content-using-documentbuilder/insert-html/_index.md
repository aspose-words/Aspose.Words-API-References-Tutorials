---
title: Html ekle
linktitle: Html ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak HTML içeriğini Word belgelerine nasıl ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-html/
---

Bu kapsamlı öğreticide, Aspose.Words for .NET kullanarak HTML içeriğini bir Word belgesine nasıl ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, Word belgelerinize HTML öğeleri, biçimlendirme ve stiller ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: HTML İçeriğini Ekleyin
Ardından, belgeye HTML içeriği eklemek için DocumentBuilder sınıfının InsertHtml yöntemini kullanın. HTML dizesine HTML etiketleri, nitelikler ve stil ekleyebilirsiniz:

```csharp
builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");
```

## 3. Adım: Belgeyi Kaydedin
HTML içeriğini ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

## Aspose.Words for .NET kullanarak HTML Eklemek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak bir Word belgesine HTML içeriği eklemek için eksiksiz kaynak kodu burada:
Bu özellik, orijinal biçimlendirmeyi ve düzeni korurken Word belgelerinize dahil etmek istediğiniz mevcut HTML içeriğiniz olduğunda özellikle kullanışlıdır.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHtml(
		"<P align='right'>Paragraph right</P>" +
		"<b>Implicit paragraph left</b>" +
		"<div align='center'>Div center</div>" +
		"<h1 align='left'>Heading 1 left.</h1>");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
	
```

Kodu, özel HTML içeriğinize ve gereksinimlerinize göre ayarlamayı unutmayın. HTML'nizin iyi biçimlendirildiğinden ve Aspose.Words for .NET ile uyumlu olduğundan emin olun.

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak HTML içeriğini bir Word belgesine nasıl ekleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak, artık HTML öğelerini, biçimlendirmeyi ve stilleri Word belgelerinize dahil edebilirsiniz.


