---
title: Word Belgesinde Kısıtlanmamış Düzenlenebilir Bölgeler
linktitle: Word Belgesinde Kısıtlanmamış Düzenlenebilir Bölgeler
second_title: Aspose.Words Belge İşleme API'sı
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

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde kısıtlanmamış düzenlenebilir bölgelerin nasıl oluşturulacağını öğrendik. Sağlanan adımları izleyerek, belge içinde, kullanıcıların belgenin geri kalanını salt okunur tutarken içeriği serbestçe düzenleyebileceği belirli alanlar tanımlayabilirsiniz. Aspose.Words for .NET, belge koruma ve özelleştirme için güçlü özellikler sunarak Word belgelerinizin düzenleme yetenekleri üzerinde kontrol sahibi olmanızı sağlar.

### Word belgesindeki kısıtlanmamış düzenlenebilir bölgeler için SSS

#### S: Aspose.Words for .NET'te sınırsız düzenlenebilir bölgeler nelerdir?

C: Aspose.Words for .NET'teki sınırsız düzenlenebilir bölgeler, bir Word belgesinde, belgenin geri kalanı salt okunur olarak ayarlanmış olsa bile içeriğin herhangi bir kısıtlama olmadan düzenlenebildiği alanlardır. Bu bölgeler, kullanıcıların genel belge korumasını korurken değiştirebilecekleri belgenin belirli bölümlerini tanımlamanın bir yolunu sağlar.

#### S: Aspose.Words for .NET kullanarak kısıtlamasız düzenlenebilir bölgeleri nasıl oluşturabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinde kısıtlanmamış düzenlenebilir bölgeler oluşturmak için şu adımları takip edebilirsiniz:
1.  kullanarak mevcut belgeyi yükleyin.`Document` sınıf.
2.  kullanarak belge korumasını salt okunur olarak ayarlayın.`Protect` yöntemi`Document` nesne.
3.  Kullan`DocumentBuilder` ekleyerek düzenlenebilir bir aralık oluşturmak için sınıf`EditableRangeStart` nesne ve bir`EditableRangeEnd` nesne.
4.  kullanarak düzenlenebilir aralık içinde içerik ekleyin.`DocumentBuilder`.
5.  Değiştirilen belgeyi şunu kullanarak kaydedin:`Save` yöntemi`Document` nesne.

#### S: Bir Word belgesinde birden fazla kısıtlanmamış düzenlenebilir bölgeye sahip olabilir miyim?

C: Evet, bir Word belgesinde birden çok sınırsız düzenlenebilir bölgeye sahip olabilirsiniz. Bunu başarmak için birden fazla set oluşturabilirsiniz.`EditableRangeStart` Ve`EditableRangeEnd` kullanan nesneler`DocumentBuilder` sınıf. Her nesne grubu, kullanıcıların herhangi bir kısıtlama olmaksızın içeriği değiştirebileceği ayrı bir düzenlenebilir bölge tanımlayacaktır.

#### S: Düzenlenebilir bölgeleri iç içe yerleştirebilir miyim?

 C: Hayır, düzenlenebilir bölgeleri Aspose.Words for .NET kullanarak iç içe geçiremezsiniz. tarafından tanımlanan her bir düzenlenebilir bölge`EditableRangeStart` Ve`EditableRangeEnd` çifti bağımsız olmalı ve başka bir düzenlenebilir bölge içinde çakışmamalı veya iç içe olmamalıdır. İç içe düzenlenebilir bölgeler desteklenmez.

#### S: Düzenlenebilir bir bölge içinde belgeden salt okunur korumayı kaldırabilir miyim?

C: Hayır, düzenlenebilir bir bölge içinde belgeden salt okunur korumayı kaldıramazsınız. Salt okunur koruma belgenin tamamına uygulanır ve belirli düzenlenebilir bölgelerden seçilerek kaldırılamaz. Düzenlenebilir bölgelerin amacı, genel belgeyi salt okunur tutarken içerik değişikliğine izin vermektir.