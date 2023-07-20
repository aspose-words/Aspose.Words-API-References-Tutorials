---
title: Form Alanları Ada Göre Alınır
linktitle: Form Alanları Ada Göre Alınır
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerinde form alanlarını ada göre nasıl alacağınızı ve değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-formfields/form-fields-get-by-name/
---

Bu adım adım eğitimde, bir Word belgesinden form alanlarını ada göre almak için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı adresinden indirip yükleyin.[Aspose.Releases]https://releases.aspose.com/words/net/.

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
FormField formField1 = documentFormFields[3]; //Dizine göre alma
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

### SSS

#### S: Aspose.Words'te ada göre bir form alanını nasıl edinebilirim?

 C: Aspose.Words'te ada göre bir form alanı elde etmek için`Document.Range.FormFields[name]` yöntem. Bu yöntem, belirtilen ada karşılık gelen form alanını döndürür.

#### S: Belirtilen ada sahip form alanı belgede yoksa ne olur?

 A: Belirtilen ada sahip form alanı belgede yoksa,`Document.Range.FormFields[name]` yöntem geri dönecek`null`Form alanının bulunmadığı durumları işlemek için bu sonucu kontrol edebilirsiniz.

#### S: Bulunan bir form alanının özelliklerini nasıl değiştirebilirim?

C: Ada göre bir form alanı aldığınızda, bunları düzenlemek için bireysel özelliklerine erişebilirsiniz. Örneğin, alanın değerini değiştirebilir, görünürlüğünü etkinleştirebilir veya devre dışı bırakabilir ya da diğer özellikleri gerektiği gibi değiştirebilirsiniz.

#### S: Bir belgede aynı ada sahip birden çok form alanı alabilir miyim?

 C: Evet, bir belgede aynı ada sahip birden çok form alanı olabilir. bu durumda,`Document.Range.FormFields[name]` method, belirtilen adla bulunan ilk form alanını döndürür. Aynı ada sahip birden fazla form alanınız varsa, alanları değiştirirken bunu dikkate almanız gerekecektir.

#### S: Bir belgedeki tüm form alanları üzerinde nasıl yineleme yapabilirim?

 C: Bir belgedeki tüm form alanları üzerinde yineleme yapmak için bir`foreach` döngü üzerinde`Document.Range.FormFields` Toplamak. Bu, her bir form alanına ayrı ayrı erişmenizi ve her biri üzerinde işlem gerçekleştirmenizi sağlar.