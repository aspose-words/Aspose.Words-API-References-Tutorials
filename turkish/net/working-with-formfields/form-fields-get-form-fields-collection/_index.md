---
title: Form Alanları Form Alanları Koleksiyonunu Alın
linktitle: Form Alanları Form Alanları Koleksiyonunu Alın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerindeki form alanları koleksiyonunu nasıl alacağınızı ve değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-formfields/form-fields-get-form-fields-collection/
---

Bu adım adım öğreticide, bir Word belgesinden form alanları koleksiyonunu almak için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` form alanlarını içeren kaynak belgenizin yolunu sağlayarak itiraz edin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");
```

## 2. Adım: Form Alanları Koleksiyonunu Alma

 Ardından, şuraya erişin:`FormFields` mülkiyeti`Range` form alanları koleksiyonunu almak için belgedeki nesne:

```csharp
FormFieldCollection formFields = doc.Range.FormFields;
```

 Artık Word belgesindeki form alanları koleksiyonuna sahipsiniz.`formFields` değişken.

## 3. Adım: Form Alanlarına Erişme ve Bu Alanları Değiştirme

Form alanları koleksiyonunu yineleyebilir ve her form alanında değerleri alma veya ayarlama, biçimlendirmeyi değiştirme veya bilgi çıkarma gibi çeşitli işlemler gerçekleştirebilirsiniz.

```csharp
foreach (FormField formField in formFields)
{
    // Her form alanına erişin ve değiştirin
    // ...
}
```

## 4. Adım: Belgeyi Kaydetme

Son olarak, gerekirse değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Bu kadar! Aspose.Words for .NET kullanarak bir Word belgesinden form alanları koleksiyonunu başarıyla aldınız.

### Form Alanları için örnek kaynak kodu Aspose.Words for .NET kullanarak Form Alanları Koleksiyonunu Alın

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection formFields = doc.Range.FormFields;

// Form alanlarına gerektiği gibi erişin ve değiştirin
// ...

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.