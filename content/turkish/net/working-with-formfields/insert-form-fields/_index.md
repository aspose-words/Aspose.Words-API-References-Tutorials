---
title: Form Alanları Ekle
linktitle: Form Alanları Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak açılır form alanlarını Word belgelerine nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-formfields/insert-form-fields/
---

Bu adım adım eğitimde, Aspose.Words for .NET kullanarak form alanlarını, özellikle açılır form alanını bir Word belgesine nasıl ekleyeceğiniz konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve kurulu olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin.[Aspose.Releases]https://releases.aspose.com/words/net/.

## Adım 1: Document ve DocumentBuilder Nesnelerini Başlatma

 İlk olarak, başlat`Document` Ve`DocumentBuilder` nesneler:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Açılır Form Alanı Ekleme

 Daha sonra açılır form alanı için seçenekleri belirleyin ve bunu kullanarak belgeye ekleyin.`InsertComboBox` yöntemi`DocumentBuilder` nesne. Bu örnekte, "Açılır" adında üç seçeneğe sahip bir açılır form alanı ekliyoruz: "Bir", "İki" ve "Üç":

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## Adım 3: Belgeyi Kaydetme

Son olarak belgeyi kaydedin:

```csharp
doc.Save("OutputDocument.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesine başarıyla bir açılır form alanı eklediniz.

### Aspose.Words for .NET kullanarak Form Alanları Ekleme için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Bu kodu kendi projelerinizde kullanmaktan ve özel gereksinimlerinize göre değiştirmekten çekinmeyin.

### SSS'ler

#### S: Aspose.Words'e metin tipi form alanını nasıl ekleyebilirim?

 C: Aspose.Words'e metin tipinde bir form alanı eklemek için`FormField` sınıfını seçin ve ayarlayın`Type`mülkiyet`FormFieldType.Text`. Ad, etiket ve seçenekler gibi diğer özellikleri de özelleştirebilirsiniz.

#### S: Bir belgede onay kutusu tipinde bir form alanı oluşturmak mümkün mü?

 C: Evet, Aspose.Words belgesinde onay kutusu tipinde bir form alanı oluşturmak mümkündür. Şunu kullanabilirsiniz:`FormField` sınıfını seçin ve ayarlayın`Type`mülkiyet`FormFieldType.CheckBox` Bir onay kutusu oluşturmak için. Daha sonra onay kutusunun özelliklerini gerektiği gibi özelleştirebilirsiniz.

#### S: Bir belgeye açılır tipte bir form alanını nasıl ekleyebilirim?

 C: Aspose.Words belgesine açılır tipte bir form alanı eklemek için`FormField` sınıfını seçin ve ayarlayın`Type`mülkiyet`FormFieldType.DropDown` . Daha sonra açılır menü seçeneklerini kullanarak ayarlayabilirsiniz.`DropDownItems` mülk.

#### S: Aspose.Words'te bir form alanı için varsayılan bir değer ayarlayabilir miyim?

C: Evet, Aspose.Words'te bir form alanı için varsayılan bir değer belirleyebilirsiniz. Kullan`FormField.Result` form alanının başlangıç değerini belirtme özelliği.

#### S: Aspose.Words'teki form alanlarına girilen verileri nasıl alabilirim?

 C: Aspose.Words'teki form alanlarına girilen verileri almak için`FormField.Result` Kullanıcı tarafından girilen değeri içeren özellik. Bu özelliğe belgenizdeki her form alanı için erişebilirsiniz.