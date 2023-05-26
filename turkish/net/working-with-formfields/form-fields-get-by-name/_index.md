---
title: Form Alanları Ada Göre Alınır
linktitle: Form Alanları Ada Göre Alınır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinde form alanlarını ada göre nasıl alacağınızı ve değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-formfields/form-fields-get-by-name/
---

Bu adım adım eğitimde, bir Word belgesinden form alanlarını ada göre almak için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` form alanlarını içeren kaynak belgenizin yolunu sağlayarak itiraz edin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## 2. Adım: Form Alanlarını Alma

 Ardından, şuraya erişin:`FormFields` mülkiyeti`Range` tüm form alanlarını almak için belgedeki nesne:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Form alanlarını dizine veya ada göre alabilirsiniz. Bu örnekte, her iki yöntemi de kullanarak bir form alanı alıyoruz:

```csharp
FormField formField1 = documentFormFields[3]; // Dizine göre alma
FormField formField2 = documentFormFields["Text2"]; // İsme göre alma
```

## 3. Adım: Form Alanı Özelliklerini Değiştirme

 Form alanlarını aldıktan sonra, özelliklerini gerektiği gibi değiştirebilirsiniz. Bu örnekte, yazı tipi boyutunu değiştiriyoruz.`formField1` 20'ye kadar ve yazı tipi rengi`formField2` kırmızıya:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## 4. Adım: Belgeyi Kaydetme

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Bu kadar! Aspose.Words for .NET kullanarak bir Word belgesinde form alanlarını ada göre başarıyla aldınız ve özelliklerini değiştirdiniz.

### Aspose.Words for .NET kullanan Form Fields Get By Name için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.
