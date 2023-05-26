---
title: Onay Kutusu Form Alanı Ekle
linktitle: Onay Kutusu Form Alanı Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerine onay kutusu form alanlarının nasıl ekleneceğini öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-check-box-form-field/
---

Bu kapsamlı öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine nasıl onay kutusu form alanı ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, belgelerinize özelleştirilebilir özelliklere sahip onay kutusu form alanları ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Onay Kutusu Form Alanı Ekleyin
Ardından, bir onay kutusu form alanı eklemek için DocumentBuilder sınıfının InsertCheckBox yöntemini kullanın. Adı, kontrol edilen durumu, varsayılan durumu ve boyut parametrelerini bağımsız değişken olarak sağlayın:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## 3. Adım: Belgeyi Kaydedin
Onay kutusu form alanını ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Aspose.Words for .NET kullanarak Onay Kutusu Form Alanı Eklemek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak bir onay kutusu form alanı eklemek için eksiksiz kaynak kodu burada:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertCheckBox("CheckBox", true, true, 0);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
	
```

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine nasıl onay kutusu form alanı ekleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak, etkileşimli onay kutusu form alanlarıyla artık belgelerinizi geliştirebilirsiniz.
