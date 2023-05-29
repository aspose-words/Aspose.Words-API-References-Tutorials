---
title: Açılan Kutu Form Alanı Ekle
linktitle: Açılan Kutu Form Alanı Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerine açılan kutu form alanlarını nasıl ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-combo-box-form-field/
---

Bu kapsamlı örnekte, Aspose.Words for .NET kullanarak bir Word belgesine birleşik giriş kutusu form alanını nasıl ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, belgelerinize özelleştirilebilir özelliklere sahip birleşik giriş kutusu form alanları ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Açılan Kutu Öğelerini Tanımlayın
Ardından, birleşik giriş kutusu form alanı için bir dizi öğe tanımlayın:

```csharp
string[] items = { "One", "Two", "Three" };
```

## 3. Adım: Açılan Kutu Form Alanı Ekleyin
Birleşik giriş kutusu form alanı eklemek için DocumentBuilder sınıfının InsertComboBox yöntemini kullanın. Adı, öğe dizisini ve seçilen dizini parametre olarak sağlayın:

```csharp
builder.InsertComboBox("DropDown", items, 0);
```

## 4. Adım: Belgeyi Kaydedin
Birleşik giriş kutusu form alanını ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

### Aspose.Words for .NET kullanarak Birleşik Giriş Kutusu Form Alanı Eklemek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak açılan kutu form alanı eklemek için eksiksiz kaynak kodu burada:

```csharp
string[] items = { "One", "Two", "Three" };

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertComboBox("DropDown", items, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine açılan kutu form alanını nasıl ekleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak, artık belgelerinizi etkileşimli açılan kutu form alanlarıyla geliştirebilirsiniz.
