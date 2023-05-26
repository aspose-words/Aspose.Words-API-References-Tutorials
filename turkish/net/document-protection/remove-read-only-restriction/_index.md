---
title: Salt Okunur Kısıtlamasını Kaldır
linktitle: Salt Okunur Kısıtlamasını Kaldır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinden salt okunur kısıtlamasını nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/remove-read-only-restriction/
---
Bu öğreticide, Aspose.Words for .NET salt okunur kısıtlama kaldırma özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesini düzenlenebilir hale getirmek için salt okunur kısıtlamasını kaldırmanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi Oluşturma ve Korumayı Ayarlama

Document sınıfının bir örneğini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

WriteProtection nesnesinin SetPassword() özelliğini kullanarak belge için bir parola belirleyin:

Belgeyi korumak için kullandığınız gerçek parola ile "Parolam"ı değiştirdiğinizden emin olun.

## 2. Adım: Salt okunur kısıtlamasını kaldırın

Salt okunur kısıtlamasını kaldırmak için ReadOnlyRecommended özelliğini false olarak ayarlayın:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## 3. Adım: Sınırsız Koruma Uygulayın

Son olarak, Document nesnesinin Protect() yöntemini kullanarak sınırsız koruma uygulayın:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Belgeyi salt okunur kısıtlaması olmadan kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Salt Okunur Kısıtlamayı Kaldır için örnek kaynak kodu

Aspose.Words for .NET kullanarak salt okunur kısıtlamasını kaldırmak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	// En fazla 15 karakter uzunluğunda bir parola girin.
	doc.WriteProtection.SetPassword("MyPassword");

	// Salt okunur seçeneğini kaldırın.
	doc.WriteProtection.ReadOnlyRecommended = false;

	// Herhangi bir koruma olmadan yazma koruması uygulayın.
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

Bu adımları izleyerek bir Word belgesindeki salt okunur kısıtlamasını Aspose.Words for .NET ile kolayca kaldırabilirsiniz.

