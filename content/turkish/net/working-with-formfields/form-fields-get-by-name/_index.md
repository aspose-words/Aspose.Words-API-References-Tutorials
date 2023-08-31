---
title: Form Alanları Ada Göre Al
linktitle: Form Alanları Ada Göre Al
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde form alanlarını ada göre nasıl alacağınızı ve değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-formfields/form-fields-get-by-name/
---

Bu adım adım eğitimde, bir Word belgesinden form alanlarını ada göre almak için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve kurulu olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin.[Aspose.Releases]https://releases.aspose.com/words/net/.

## Adım 1: Belge Nesnesini Başlatma

 İlk olarak, başlat`Document` form alanlarını içeren kaynak belgenizin yolunu sağlayarak nesneyi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## 2. Adım: Form Alanlarını Alma

 Daha sonra şuraya erişin:`FormFields` mülkiyeti`Range` tüm form alanlarını almak için belgedeki nesne:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Form alanlarını dizine veya ada göre alabilirsiniz. Bu örnekte, her iki yöntemi de kullanarak bir form alanı alıyoruz:

```csharp
FormField formField1 = documentFormFields[3]; //Dizine göre alma
FormField formField2 = documentFormFields["Text2"]; // İsme göre alma
```

## 3. Adım: Form Alanı Özelliklerini Değiştirme

 Form alanlarını aldıktan sonra özelliklerini gerektiği gibi değiştirebilirsiniz. Bu örnekte yazı tipi boyutunu değiştiriyoruz.`formField1` 20'ye ve yazı tipi rengine`formField2` kırmızıya:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Adım 4: Belgeyi Kaydetme

Son olarak değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesinde form alanlarını başarıyla ada göre aldınız ve özelliklerini değiştirdiniz.

### Aspose.Words for .NET kullanılarak İsme Göre Al Form Alanları için örnek kaynak kodu

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

Bu kodu kendi projelerinizde kullanmaktan ve özel gereksinimlerinize göre değiştirmekten çekinmeyin.

### SSS'ler

#### S: Aspose.Words'te bir form alanını ada göre nasıl edinebilirim?

 C: Aspose.Words'te ada göre bir form alanı almak için`Document.Range.FormFields[name]` yöntem. Bu yöntem, belirtilen ada karşılık gelen form alanını döndürür.

#### S: Belirtilen ada sahip form alanı belgede mevcut değilse ne olur?

 C: Belirtilen adda form alanı belgede mevcut değilse,`Document.Range.FormFields[name]` yöntem geri dönecek`null`Form alanının bulunmadığı durumları işlemek için bu sonucu kontrol edebilirsiniz.

#### S: Bulunan bir form alanının özelliklerini nasıl değiştirebilirim?

C: Bir form alanını ada göre aldığınızda, bu alanın bireysel özelliklerine erişerek bunları düzenleyebilirsiniz. Örneğin alanın değerini değiştirebilir, görünürlüğünü etkinleştirebilir veya devre dışı bırakabilir veya diğer özellikleri gerektiği gibi değiştirebilirsiniz.

#### S: Bir belgede aynı ada sahip birden fazla form alanı alabilir miyim?

 C: Evet, bir belgede aynı adda birden fazla form alanının bulunması mümkündür. Bu durumda,`Document.Range.FormFields[name]` yöntemi belirtilen adla bulunan ilk form alanını döndürecektir. Aynı ada sahip birden fazla form alanınız varsa alanları düzenlerken bunu dikkate almanız gerekir.

#### S: Bir belgedeki tüm form alanlarını nasıl yineleyebilirim?

 C: Bir belgedeki tüm form alanlarını yinelemek için`foreach` döngü üzerinde`Document.Range.FormFields` Toplamak. Bu, her form alanına ayrı ayrı erişmenize ve her biri üzerinde işlem yapmanıza olanak tanır.