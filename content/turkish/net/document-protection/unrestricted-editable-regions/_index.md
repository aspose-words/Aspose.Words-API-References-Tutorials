---
title: Word Belgesinde Sınırsız Düzenlenebilir Bölgeler
linktitle: Word Belgesinde Sınırsız Düzenlenebilir Bölgeler
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde sınırsız düzenlenebilir alanların nasıl oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/unrestricted-editable-regions/
---
Bu eğitimde Aspose.Words for .NET'in sınırsız düzenlenebilir alanlar özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, bir Word belgesinde, belgenin geri kalanı salt okunur olsa bile içeriğin kısıtlama olmaksızın düzenlenebileceği alanları tanımlamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme ve korumayı ayarlama

Mevcut belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Salt okunur koruma türünü ve parolayı ayarlayarak belgeyi koruyun

## 2. Adım: Düzenlenebilir bir alan oluşturma

EditableRangeStart ve EditableRangeEnd nesnelerini kullanarak düzenlenebilir bir alan oluşturarak başlayın:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Az önce yaptığımız EditableRangeStart için bir EditableRange nesnesi oluşturulur.
EditableRange editableRange = edRangeStart.EditableRange;

// Düzenlenebilir aralığa bir şey koyun.
builder.Writeln("Paragraph inside first editable range");

// Düzenlenebilir bir aralık, bir başlangıcı ve bitişi varsa iyi biçimlendirilmiş demektir.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## 3. Adım: Düzenlenebilir alanların dışına içerik ekleyin

Düzenlenebilir alanların dışında salt okunur kalacak içerik ekleyebilirsiniz:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## 4. Adım: Belgeyi kaydedin

Son olarak değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Belgeyi düzenlenebilir alanlarla kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Kısıtlanmamış Düzenlenebilir Bölgeler için örnek kaynak kodu

Aspose.Words for .NET kullanan sınırsız düzenlenebilir alanlar için tam kaynak kodu:

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
// Az önce yaptığımız EditableRangeStart için bir EditableRange nesnesi oluşturulur.
EditableRange editableRange = edRangeStart.EditableRange;

// Düzenlenebilir aralığa bir şey koyun.
builder.Writeln("Paragraph inside first editable range");

// Düzenlenebilir bir aralık, bir başlangıcı ve bitişi varsa iyi biçimlendirilmiş demektir.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Bu adımları takip ederek Aspose.Words for .NET ile Word belgenizde kolayca sınırsız düzenlenebilir alanlar oluşturabilirsiniz.

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde sınırsız düzenlenebilir bölgelerin nasıl oluşturulacağını öğrendik. Sağlanan adımları izleyerek, belgenin geri kalanını salt okunur olarak tutarken kullanıcıların içeriği serbestçe düzenleyebileceği belge içinde belirli alanlar tanımlayabilirsiniz. Aspose.Words for .NET, belge koruma ve özelleştirme için güçlü özellikler sunarak Word belgelerinizin düzenleme özellikleri üzerinde kontrol sahibi olmanızı sağlar.

### Word belgesindeki sınırsız düzenlenebilir bölgeler için SSS

#### S: Aspose.Words for .NET'te sınırsız düzenlenebilir bölgeler nelerdir?

C: Aspose.Words for .NET'teki sınırsız düzenlenebilir bölgeler, bir Word belgesi içindeki, belgenin geri kalanı salt okunur olarak ayarlanmış olsa bile içeriğin herhangi bir kısıtlama olmaksızın düzenlenebildiği alanlardır. Bu bölgeler, genel belge korumasını korurken kullanıcıların değiştirebileceği belgenin belirli bölümlerini tanımlamanın bir yolunu sağlar.

#### S: Aspose.Words for .NET'i kullanarak nasıl sınırsız düzenlenebilir bölgeler oluşturabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinde sınırsız düzenlenebilir bölgeler oluşturmak için şu adımları takip edebilirsiniz:
1.  Mevcut belgeyi kullanarak yükleyin.`Document` sınıf.
2.  Belge korumasını salt okunur olarak ayarlayın.`Protect` yöntemi`Document` nesne.
3.  Kullan`DocumentBuilder` ekleyerek düzenlenebilir bir aralık oluşturmak için sınıf`EditableRangeStart` nesne ve bir`EditableRangeEnd` nesne.
4.  Kullanarak düzenlenebilir aralıktaki içeriği ekleyin`DocumentBuilder`.
5.  Değiştirilen belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

#### S: Bir Word belgesinde birden çok sınırsız düzenlenebilir bölgeye sahip olabilir miyim?

C: Evet, bir Word belgesinde birden fazla sınırsız düzenlenebilir bölgeye sahip olabilirsiniz. Bunu başarmak için birden fazla set oluşturabilirsiniz.`EditableRangeStart` Ve`EditableRangeEnd` kullanarak nesneler`DocumentBuilder` sınıf. Her nesne kümesi, kullanıcıların içeriği herhangi bir kısıtlama olmaksızın değiştirebileceği ayrı bir düzenlenebilir bölge tanımlayacaktır.

#### S: Düzenlenebilir bölgeleri iç içe yerleştirebilir miyim?

 C: Hayır, Aspose.Words for .NET'i kullanarak düzenlenebilir bölgeleri iç içe yerleştiremezsiniz. Bir tarafından tanımlanan her düzenlenebilir bölge`EditableRangeStart` Ve`EditableRangeEnd` çifti bağımsız olmalı ve çakışmamalı veya başka bir düzenlenebilir bölge içinde yuvalanmamalıdır. İç içe düzenlenebilir bölgeler desteklenmez.

#### S: Düzenlenebilir bir bölge içindeki belgeden salt okunur korumayı kaldırabilir miyim?

C: Hayır, düzenlenebilir bir bölge içindeki belgeden salt okunur korumayı kaldıramazsınız. Salt okunur koruma belgenin tamamına uygulanır ve belirli düzenlenebilir bölgeler içerisinde seçime bağlı olarak kaldırılamaz. Düzenlenebilir bölgelerin amacı, belgenin tamamını salt okunur halde tutarken içerik değişikliğine izin vermektir.