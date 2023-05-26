---
title: Form Alanları Ekle
linktitle: Form Alanları Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak açılır form alanlarını Word belgelerine nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-formfields/insert-form-fields/
---

Bu adım adım öğreticide, Aspose.Words for .NET kullanarak form alanlarını, özellikle bir açılır form alanını bir Word belgesine nasıl ekleyeceğiniz konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Document ve DocumentBuilder Nesnelerini Başlatma

 İlk olarak,`Document` Ve`DocumentBuilder` nesneler:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Açılır Form Alanı Ekleme

 Ardından, açılır form alanı için seçenekleri belirtin ve bunu kullanarak belgeye ekleyin.`InsertComboBox` yöntemi`DocumentBuilder`nesne. Bu örnekte, "DropDown" adlı üç seçenekli bir açılır form alanı ekliyoruz: "Bir", "İki" ve "Üç":

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## 3. Adım: Belgeyi Kaydetme

Son olarak, belgeyi kaydedin:

```csharp
doc.Save("OutputDocument.docx");
```

Bu kadar! Aspose.Words for .NET kullanarak bir açılır form alanını bir Word belgesine başarıyla eklediniz.

### Aspose.Words for .NET kullanarak Form Alanları Ekleme için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.