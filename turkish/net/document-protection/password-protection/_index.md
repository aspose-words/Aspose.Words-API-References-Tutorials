---
title: Şifre Koruması
linktitle: Şifre Koruması
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinizi nasıl parola ile koruyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/password-protection/
---

Bu öğreticide, Aspose.Words for .NET'in parola koruma özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, gizliliğini sağlamak için bir Word belgesini bir parola ile korumanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belge Oluşturma ve Koruma Uygulama

Document sınıfının bir örneğini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Parola koruması uygulayın

Ardından, Document nesnesinin Protect() yöntemini kullanarak parola koruması uygulayabilirsiniz:

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

Belgeyi korumak için kullanmak istediğiniz asıl parolayı "parola" ile değiştirdiğinizden emin olun.

## 3. Adım: Korunan Belgeyi Kaydetme

Son olarak, Document nesnesinin Save() yöntemini kullanarak korunan belgeyi kaydedebilirsiniz:

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

Korunan belgeyi kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Parola Koruması için örnek kaynak kodu

Aspose.Words for .NET kullanarak parola koruması için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	//Belge korumasını uygulayın.
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

"BELGELER DİZİNİNİZİ" belgelerinizin dizini ile ve "parola"yı kullanmak istediğiniz gerçek parolayla değiştirmeyi unutmayın.

