---
title: Word Belgesinde Yalnızca Form Alanlarının Korunmasına İzin Ver
linktitle: Word Belgesinde Yalnızca Form Alanlarının Korunmasına İzin Ver
second_title: Aspose.Words Belge İşleme API'si
description: Word belgesini korumak ve yalnızca form alanlarının düzenlenmesine izin vermek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/allow-only-form-fields-protect/
---
Belge koruması, C# uygulamanızdaki dosyalarla Kelime İşleme yaparken önemli bir özelliktir. .NET için Aspose.Words kütüphanesi ile belgelerinizi kolayca koruyabilir ve yalnızca form alanlarının düzenlenmesine izin verebilirsiniz. Bu adım adım kılavuzda, Aspose.Words for .NET'in Yalnızca Form Alanlarını Korumaya İzin Ver özelliğini kullanarak yalnızca form alanlarının düzenlenmesine izin vermek için C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Adım 1: Belge Dizinini Ayarlama

İlk adım belgenizin dizinini tanımlamaktır. Korumalı belgeyi kaydetmek istediğiniz yolu belirtmeniz gerekir. Örneğin :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 2: Bölüm ve Metin Ekleme

Daha sonra belgenize bölümler ve metin eklemeniz gerekir. Belgenizin içeriğini oluşturmak için Aspose.Words tarafından sağlanan DocumentBuilder sınıfını kullanın. İşte basit bir örnek:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Bu örnekte yeni bir boş belge oluşturuyoruz ve ardından bir metin satırı eklemek için DocumentBuilder'ı kullanıyoruz.

## 3. Adım: Belge Korumasını Etkinleştirme

 Belge koruması yalnızca belge koruması etkinleştirildiğinde çalışır. Belge korumasını kullanarak etkinleştirebilirsiniz.`Protect` Document sınıfının yöntemi. İşte nasıl:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Bu örnekte koruma tipini belirterek belge korumasını etkinleştiriyoruz `

AllowOnlyFormFields` ve bir şifre ayarlama.

## 4. Adım: Yalnızca Form Alanlarına İzin Verme

Artık belge koruması etkinleştirildiğine göre yalnızca form alanlarının düzenlenmesine izin verildiğini belirtmemiz gerekiyor. Bu, kullanıcıların belgenin yalnızca form alanları olan bölümlerini düzenleyebilmesini sağlar. İşte nasıl:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

"Şifre"yi daha önce belirlediğiniz şifreyle değiştirdiğinizden emin olun.

## Adım 5: Korumalı Belgeyi Kaydetme

 Son olarak, korumalı belgeyi kullanarak kaydedebilirsiniz.`Save` Document sınıfının yöntemi. Tam dosya yolunu ve istediğiniz dosya adını belirtin. Örneğin :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

"dataDir" yerine belge dizininizin yolunu yazdığınızdan emin olun.

### Aspose.Words for .NET kullanan Yalnızca Form Alanlarını Korumaya İzin Ver özelliği için örnek kaynak kodu

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Biraz metin içeren iki bölüm ekleyin.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Belge koruması yalnızca belge koruması açıldığında çalışır ve yalnızca form alanlarında düzenlemeye izin verilir.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Korumalı belgeyi kaydedin.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Çözüm

Bu kılavuzda, bir belgeyi korumak ve yalnızca form alanlarının düzenlenmesine izin vermek için .NET için Aspose.Words kütüphanesinin nasıl kullanılacağını araştırdık. Verilen adımları takip ederek bu işlevselliği C# uygulamanıza kolayca uygulayabilirsiniz. Belgelerinizin güvenliğini ve gizliliğini sağlamak için belge koruması önemlidir.

### Word belgesinde yalnızca izin verilen form alanlarının korunmasına ilişkin SSS'ler

#### S: Aspose.Words for .NET'te belge koruması nedir?

C: Aspose.Words for .NET'te belge koruması; düzenleme, biçimlendirme veya içerik değişikliği gibi belirli eylemleri kısıtlayarak belgelerinizi koruma altına almanızı sağlayan bir özelliktir. Yetkisiz değişiklikleri önleyerek belgelerinizin bütünlüğünü ve gizliliğini korumaya yardımcı olur.

#### S: Bir belgeyi nasıl koruyabilirim ve Aspose.Words for .NET kullanarak yalnızca form alanlarının düzenlenmesine nasıl izin verebilirim?

C: Bir belgeyi korumak ve Aspose.Words for .NET kullanılarak yalnızca form alanlarının düzenlenmesine izin vermek için şu adımları takip edebilirsiniz:
1. Belgenizin dizin yolunu tanımlayın.
2.  kullanarak belgenize bölümler ve metin ekleyin.`DocumentBuilder` sınıf.
3.  kullanarak belge korumasını etkinleştirin.`Protect` yöntemi`Document` koruma tipini belirterek sınıf`AllowOnlyFormFields` ve bir şifre sağlıyoruz.
4.  Korumalı belgeyi kullanarak kaydedin.`Save` yöntemi`Document` sınıf.

#### S: Aspose.Words for .NET kullanarak form alanlarını korumalı bir belgeye ekleyebilir miyim?

C: Evet, Aspose.Words for .NET kullanarak form alanlarını korumalı bir belgeye ekleyebilirsiniz. Belge koruması ile`AllowOnlyFormFields` tür, kullanıcıların belgenin geri kalan içeriğini korurken yalnızca form alanlarını düzenlemesine olanak tanır. Şunu kullanabilirsiniz:`DocumentBuilder` Korumayı etkinleştirmeden önce form alanlarını belgeye eklemek için sınıf.

#### S: Korumalı bir belgeden belge korumasını kaldırabilir miyim?

 C: Evet, Aspose.Words for .NET'i kullanarak korumalı bir belgedeki belge korumasını kaldırabilirsiniz. Korumayı kaldırmak için şunu kullanabilirsiniz:`Unprotect` yöntemi`Document` sınıf ve doğru şifreyi girin. Bu, korumayı kaldıracak ve belgenin sınırsız düzenlenmesine olanak tanıyacaktır.

#### S: Bir belgeyi birden fazla koruma türüyle korumak mümkün müdür?

 C: Hayır, Aspose.Words for .NET bir belgeye aynı anda yalnızca tek bir koruma türünün uygulanmasına izin verir. Ancak`AllowOnlyFormFields` koruma türü, diğer koruma türlerine izin verirken, form alanlarındaki düzenlemeyi etkili bir şekilde kısıtlayabilir:`AllowOnlyComments` veya`AllowOnlyRevisions`form alanı korumasıyla birleştirilecek.

#### S: Bir belgedeki farklı koruma türleri için farklı şifreler ayarlayabilir miyim?

C: Hayır, Aspose.Words for .NET, koruma türünden bağımsız olarak belge koruması için tek bir şifre belirlemenize olanak tanır. Belge korumasını etkinleştirmek ve devre dışı bırakmak için aynı şifre kullanılacaktır.