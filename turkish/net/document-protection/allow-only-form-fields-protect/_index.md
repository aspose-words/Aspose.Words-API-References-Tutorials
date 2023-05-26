---
title: Yalnızca Form Alanlarının Korunmasına İzin Ver
linktitle: Yalnızca Form Alanlarının Korunmasına İzin Ver
second_title: Aspose.Words for .NET API Referansı
description: Belgeleri korumak ve yalnızca form alanlarının düzenlenmesine izin vermek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/allow-only-form-fields-protect/
---

Belge koruması, C# uygulamanızdaki dosyalarla çalışırken önemli bir özelliktir. .NET için Aspose.Words kitaplığı ile belgelerinizi kolayca koruyabilir ve yalnızca form alanlarının düzenlenmesine izin verebilirsiniz. Bu adım adım kılavuzda, Aspose.Words for .NET'in Yalnızca Form Alanlarının Korunmasına İzin Ver özelliği kullanılarak yalnızca form alanlarının düzenlenmesine izin vermek için C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

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
