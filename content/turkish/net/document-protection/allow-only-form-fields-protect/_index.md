---
title: Word Belgesinde Yalnızca Form Alanlarının Korunmasına İzin Ver
linktitle: Word Belgesinde Yalnızca Form Alanlarının Korunmasına İzin Ver
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'i word belgesini korumak ve yalnızca form alanlarının düzenlenmesine izin vermek için nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/allow-only-form-fields-protect/
---
Belge koruması, C# uygulamanızdaki dosyalarla Sözcük İşleme yaparken önemli bir özelliktir. .NET için Aspose.Words kitaplığı ile belgelerinizi kolayca koruyabilir ve yalnızca form alanlarının düzenlenmesine izin verebilirsiniz. Bu adım adım kılavuzda, Aspose.Words for .NET'in Yalnızca Form Alanlarının Korunmasına İzin Ver özelliği kullanılarak yalnızca form alanlarının düzenlenmesine izin vermek için C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## 1. Adım: Belge Dizininin Ayarlanması

İlk adım, belgenizin dizinini tanımlamaktır. Korunan belgeyi kaydetmek istediğiniz yolu belirtmelisiniz. Örneğin :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 2. Adım: Bölümler ve Metin Ekleme

Ardından, belgenize bölümler ve metin eklemeniz gerekir. Belgenizin içeriğini oluşturmak için Aspose.Words tarafından sağlanan DocumentBuilder sınıfını kullanın. İşte basit bir örnek:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Bu örnekte, yeni bir boş belge oluşturuyoruz ve ardından bir metin satırı eklemek için DocumentBuilder'ı kullanıyoruz.

## 3. Adım: Belge Korumasını Etkinleştirme

 Belge koruması yalnızca belge koruması etkinleştirildiğinde çalışır. kullanarak belge korumasını etkinleştirebilirsiniz.`Protect` Document sınıfının yöntemi. İşte nasıl:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Bu örnekte, ` koruma türünü belirterek belge korumasını etkinleştiriyoruz.

AllowOnlyFormFields` ve bir parola ayarlama.

## 4. Adım: Yalnızca Form Alanlarına İzin Verme

Artık belge koruması etkinleştirildiğine göre, yalnızca form alanlarının düzenlenmesine izin verildiğini belirtmemiz gerekiyor. Bu, kullanıcıların belgenin yalnızca form alanları olan kısımlarını düzenleyebilmelerini sağlar. İşte nasıl:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

"Parola"yı daha önce belirlediğiniz parolayla değiştirdiğinizden emin olun.

## 5. Adım: Korumalı Belgeyi Kaydetme

 Son olarak, korumalı belgeyi kullanarak kaydedebilirsiniz.`Save` Document sınıfının yöntemi. Tam dosya yolunu ve istenen dosya adını belirtin. Örneğin :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

"dataDir" öğesini belge dizininizin yolu ile değiştirdiğinizden emin olun.

### Aspose.Words for .NET kullanan Allow Only Form Fields Protect özelliği için örnek kaynak kodu

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Biraz metin içeren iki bölüm ekleyin.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Bir belge koruması, yalnızca belge koruması açıldığında çalışır ve yalnızca form alanlarında düzenlemeye izin verilir.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Korunan belgeyi kaydedin.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Çözüm

Bu kılavuzda, bir belgeyi korumak ve yalnızca form alanlarının düzenlenmesine izin vermek için Aspose.Words kitaplığının .NET için nasıl kullanılacağını inceledik. Sağlanan adımları izleyerek bu işlevi C# uygulamanızda kolayca uygulayabilirsiniz. Belgelerinizin güvenliğini ve gizliliğini sağlamak için belge koruması şarttır.

### Word belgesinde yalnızca form alanlarının korunmasına izin verilmesiyle ilgili SSS

#### S: Aspose.Words for .NET'te belge koruması nedir?

Y: Aspose.Words for .NET'te belge koruması, düzenleme, biçimlendirme veya içerik değiştirme gibi belirli eylemleri kısıtlayarak belgelerinizi korumanıza izin veren bir özelliktir. Yetkisiz değişiklikleri önleyerek belgelerinizin bütünlüğünü ve gizliliğini korumaya yardımcı olur.

#### S: Bir belgeyi nasıl koruyabilirim ve Aspose.Words for .NET kullanarak yalnızca form alanlarının düzenlenmesine izin verebilirim?

Y: Bir belgeyi korumak ve Aspose.Words for .NET kullanılarak yalnızca form alanlarının düzenlenmesine izin vermek için şu adımları izleyebilirsiniz:
1. Belgeniz için dizin yolunu tanımlayın.
2.  kullanarak belgenize bölümler ve metin ekleyin.`DocumentBuilder` sınıf.
3.  kullanarak belge korumasını etkinleştirin.`Protect` yöntemi`Document` sınıf, koruma türünü şu şekilde belirterek`AllowOnlyFormFields` ve bir şifre sağlamak.
4.  kullanarak korunan belgeyi kaydedin.`Save` yöntemi`Document` sınıf.

#### S: Aspose.Words for .NET kullanarak korumalı bir belgeye form alanları ekleyebilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak korumalı bir belgeye form alanları ekleyebilirsiniz. ile belge koruması`AllowOnlyFormFields` type, kullanıcıların belge içeriğinin geri kalanını korurken yalnızca form alanlarını düzenlemesine olanak tanır. kullanabilirsiniz`DocumentBuilder` Korumayı etkinleştirmeden önce form alanlarını belgeye eklemek için sınıf.

#### S: Korumalı bir belgeden belge korumasını kaldırabilir miyim?

 C: Evet, Aspose.Words for .NET kullanarak korumalı bir belgeden belge korumasını kaldırabilirsiniz. Korumayı kaldırmak için,`Unprotect` yöntemi`Document` sınıf ve doğru parolayı sağlayın. Bu, korumayı kaldıracak ve belgenin sınırsız şekilde düzenlenmesine izin verecektir.

#### S: Bir belgeyi birden çok koruma türüyle korumak mümkün mü?

 C: Hayır, Aspose.Words for .NET bir defada bir belgeye yalnızca bir koruma türünün uygulanmasına izin verir. Ancak`AllowOnlyFormFields` koruma türü, diğer koruma türlerine izin verirken form alanlarını düzenlemeyi etkili bir şekilde kısıtlayabilir.`AllowOnlyComments` veya`AllowOnlyRevisions`form alanı korumasıyla birleştirilecek.

#### S: Bir belgede farklı koruma türleri için farklı parolalar belirleyebilir miyim?

C: Hayır, Aspose.Words for .NET, koruma türünden bağımsız olarak belge koruması için tek bir parola belirlemenize olanak tanır. Belge korumasını etkinleştirmek ve devre dışı bırakmak için aynı parola kullanılacaktır.