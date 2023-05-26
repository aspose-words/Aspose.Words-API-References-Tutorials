---
title: Salt Okunur Koruma
linktitle: Salt Okunur Koruma
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile salt okunur Word belgelerinizi nasıl koruyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/read-only-protection/
---
Bu eğitimde, Aspose.Words for .NET'in salt okunur koruma özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, yetkisiz değişiklik yapılmasını önlemek için bir Word belgesini salt okunur yapmanızı sağlar. Aşağıdaki adımları takip et:

## 1. Adım: Belge Oluşturma ve Koruma Uygulama

Document sınıfının bir örneğini ve DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belgeye içerik yazın
Belgeye içerik yazmak için DocumentBuilder nesnesini kullanın:

```csharp
builder.Write("Open document as read-only");
```

## 3. Adım: Parola belirleyin ve belgeyi salt okunur yapın

WriteProtection nesnesinin SetPassword() özelliğini kullanarak belge için bir parola belirleyin:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

"MyPassword" yerine kullanmak istediğiniz gerçek parolayı koyduğunuzdan emin olun.

## 4. Adım: Salt okunur belgeyi uygulayın

ReadOnlyRecommended özelliğini true olarak ayarlayarak belgeyi salt okunur yapın:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## 5. Adım: Salt okunur koruma uygulayın ve belgeyi kaydedin

Son olarak, Document nesnesinin Protect() yöntemini kullanarak salt okunur koruma uygulayın:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Korunan belgeyi kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Salt Okunur Koruma için örnek kaynak kodu

Aspose.Words for .NET kullanarak salt okunur koruma için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	// En fazla 15 karakter uzunluğunda bir parola girin.
	doc.WriteProtection.SetPassword("MyPassword");

	// Belgeyi salt okunur yapın.
	doc.WriteProtection.ReadOnlyRecommended = true;

	// Yazma korumasını salt okunur olarak uygulayın.
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Bu adımları izleyerek belgelerinizi kolayca koruyabilirsiniz.

