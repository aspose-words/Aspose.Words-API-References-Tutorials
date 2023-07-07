---
title: Sınırsız Bölüm
linktitle: Sınırsız Bölüm
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde kısıtlanmamış bölümlerin nasıl tanımlanacağını öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/unrestricted-section/
---

Bu öğreticide, Aspose.Words for .NET'in sınırsız bölüm özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, bir Word belgesinde, belgenin geri kalanı korumalı olsa bile, korunmayan belirli bölümleri tanımlamanıza olanak tanır. Aşağıdaki adımları takip et:

## Adım 1: Belgeyi ve Bölümleri Oluşturma

Document sınıfının bir örneğini ve DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belgeye içerik ekleyin
Belgeye içerik eklemek ve bölüm sonları eklemek için DocumentBuilder nesnesini kullanın:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## 3. Adım: Belgeyi ve Bölümleri Koruyun

Bölüm koruması yalnızca belge koruması etkinleştirildiğinde çalışır ve yalnızca form alanlarında düzenlemeye izin verilir. Document nesnesinin Protect() yöntemini kullanarak belgeyi koruyabilirsiniz:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Doğru koruma türünü belirttiğinizden ve istenen parolayı ayarladığınızdan emin olun.

## 4. Adım: Belirli bir bölüm için korumayı devre dışı bırakma

Varsayılan olarak tüm bölümler korumalıdır, ancak Section nesnesinin ProtectedForForms özelliğini kullanarak belirli bir bölüm için korumayı seçerek devre dışı bırakabilirsiniz:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

Bu örnekte, ilk bölüm için koruma devre dışı bırakılmıştır.

## 5. Adım: Belgeyi kaydedin

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Belgeyi sınırsız bölümlerle kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Unrestricted Section için örnek kaynak kodu

Aspose.Words for .NET kullanan kısıtlamasız bölüm için eksiksiz kaynak kodu burada:


```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Biraz metin içeren iki bölüm ekleyin.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Bölüm koruması yalnızca belge koruması açıldığında çalışır ve yalnızca form alanlarında düzenlemeye izin verilir.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Varsayılan olarak, tüm bölümler korumalıdır, ancak korumayı seçerek kapatabiliriz.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Bu adımları izleyerek, Aspose.Words for .NET ile Word belgenizde sınırsız bölümleri kolayca tanımlayabileceksiniz.

