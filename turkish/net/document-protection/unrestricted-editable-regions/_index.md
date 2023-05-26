---
title: Kısıtlanmamış Düzenlenebilir Bölgeler
linktitle: Kısıtlanmamış Düzenlenebilir Bölgeler
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde sınırsız düzenlenebilir alanların nasıl oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/unrestricted-editable-regions/
---

Bu öğreticide, Aspose.Words for .NET'in sınırsız düzenlenebilir alanlar özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, bir Word belgesinde, belgenin geri kalanı salt okunur olsa bile içeriğin kısıtlama olmadan düzenlenebileceği alanları tanımlamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme ve korumayı ayarlama

Mevcut belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Salt okunur koruma türü ve parola ayarlayarak belgeyi koruyun

## 2. Adım: Düzenlenebilir bir alan oluşturma

EditableRangeStart ve EditableRangeEnd nesnelerini kullanarak düzenlenebilir bir alan oluşturarak başlayın:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Az önce oluşturduğumuz EditableRangeStart için bir EditableRange nesnesi oluşturulur.
EditableRange editableRange = edRangeStart.EditableRange;

// Düzenlenebilir aralığın içine bir şey koyun.
builder.Writeln("Paragraph inside first editable range");

// Düzenlenebilir bir aralık, bir başlangıcı ve bir sonu varsa iyi biçimlendirilmiştir.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## 3. Adım: Düzenlenebilir alanların dışında içerik ekleyin

Salt okunur olarak kalacak olan düzenlenebilir alanların dışına içerik ekleyebilirsiniz:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## 4. Adım: Belgeyi kaydedin

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Belgeyi düzenlenebilir alanlarla kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Sınırsız Düzenlenebilir Bölgeler için örnek kaynak kodu

Aspose.Words for .NET kullanan sınırsız düzenlenebilir alanlar için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Bir belge yükleyin ve onu salt okunur yapın.
	Document doc = new Document(MyDir + "Document.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	doc.Protect(ProtectionType.ReadOnly, "MyPassword");

	builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

	// Düzenlenebilir bir aralık başlatın.
	EditableRangeStart edRangeStart = builder.StartEditableRange();
	// Az önce oluşturduğumuz EditableRangeStart için bir EditableRange nesnesi oluşturulur.
	EditableRange editableRange = edRangeStart.EditableRange;

	// Düzenlenebilir aralığın içine bir şey koyun.
	builder.Writeln("Paragraph inside first editable range");

	// Düzenlenebilir bir aralık, bir başlangıcı ve bir sonu varsa iyi biçimlendirilmiştir.
	EditableRangeEnd edRangeEnd = builder.EndEditableRange();

	builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

	doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Bu adımları izleyerek, Aspose.Words for .NET ile Word belgenizde kolayca sınırsız düzenlenebilir alanlar oluşturabilirsiniz.


