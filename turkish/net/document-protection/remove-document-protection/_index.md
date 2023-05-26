---
title: Belge Korumasını Kaldır
linktitle: Belge Korumasını Kaldır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinden korumayı nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/remove-document-protection/
---

Bu öğreticide, Aspose.Words for .NET'in korumayı kaldır belge özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, daha fazla düzenleme için erişilebilir hale getirmek için bir Word belgesinden korumayı kaldırmanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belge Oluşturma ve İçerik Ekleme

Document sınıfının bir örneğini ve DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belgeye içerik ekleyin

Belgeye içerik eklemek için DocumentBuilder nesnesini kullanın:

```csharp
builder.Writeln("Text added to a document.");
```

## 3. Adım: Belgenin korumasını kaldırın

Belgenin korumasını kaldırmak için Document nesnesinin Unprotect() yöntemini kullanabilirsiniz. Korumayı parola olmadan veya doğru parolayla kaldırmayı seçebilirsiniz. Parolasız korumayı kaldırma:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

"YeniParola"yı doğru belge parolasıyla değiştirdiğinizden emin olun.

## 4. Adım: Belgeyi korumasız kaydedin

Son olarak, Document nesnesinin Save() yöntemini kullanarak belgeyi korumasız olarak kaydedin:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Belgeyi korumasız kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Belge Korumasını Kaldır için örnek kaynak kodu

Aspose.Words for .NET kullanarak belgenin korumasını kaldırmak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Text added to a document.");

	// Dokümanların koruması, şifre olmadan veya doğru şifre ile kaldırılabilir.
	doc.Unprotect();
	doc.Protect(ProtectionType.ReadOnly, "newPassword");
	doc.Unprotect("newPassword");

	doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Bu adımları izleyerek, Aspose.Words for .NET ile Word belgesindeki korumayı kolaylıkla kaldırabilirsiniz.
