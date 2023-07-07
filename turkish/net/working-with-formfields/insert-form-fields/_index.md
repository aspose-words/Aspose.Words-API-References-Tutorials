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

 Ardından, açılır form alanı için seçenekleri belirtin ve bunu kullanarak belgeye ekleyin.`InsertComboBox` yöntemi`DocumentBuilder` nesne. Bu örnekte, "DropDown" adlı üç seçenekli bir açılır form alanı ekliyoruz: "Bir", "İki" ve "Üç":

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

### SSS

#### S: Aspose.Words'te bir metin tipi form alanını nasıl ekleyebilirim?

 A: Aspose.Words'te bir metin tipi form alanı eklemek için`FormField` sınıflandırın ve ayarlayın`Type` mülkiyet`FormFieldType.Text`. Ad, etiket ve seçenekler gibi diğer özellikleri de özelleştirebilirsiniz.

#### S: Bir belgede onay kutusu tipi bir form alanı oluşturmak mümkün mü?

 C: Evet, bir Aspose.Words belgesinde onay kutusu tipi bir form alanı oluşturmak mümkündür. kullanabilirsiniz`FormField` sınıflandırın ve ayarlayın`Type` mülkiyet`FormFieldType.CheckBox` bir onay kutusu oluşturmak için. Ardından, onay kutusunun özelliklerini gerektiği gibi özelleştirebilirsiniz.

#### S: Bir belgeye açılır tipte bir form alanını nasıl ekleyebilirim?

 C: Bir Aspose.Words belgesine açılır tipte bir form alanı eklemek için`FormField` sınıflandırın ve ayarlayın`Type` mülkiyet`FormFieldType.DropDown` . Daha sonra aşağı açılır seçenekleri kullanarak ayarlayabilirsiniz.`DropDownItems` mülk.

#### S: Aspose.Words'te bir form alanı için varsayılan bir değer belirleyebilir miyim?

C: Evet, Aspose.Words'te bir form alanı için varsayılan bir değer ayarlayabilirsiniz. Kullan`FormField.Result` form alanının başlangıç değerini belirtmek için özellik.

#### S: Aspose.Words'te form alanlarına girilen verileri nasıl alabilirim?

 C: Aspose.Words'te form alanlarına girilen verileri almak için`FormField.Result` kullanıcı tarafından girilen değeri içeren özellik. Belgenizdeki her form alanı için bu özelliğe erişebilirsiniz.