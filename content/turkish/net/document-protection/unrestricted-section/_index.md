---
title: Word Belgesinde Sınırsız Bölüm
linktitle: Word Belgesinde Sınırsız Bölüm
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde sınırsız bölümleri nasıl tanımlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-protection/unrestricted-section/
---
Bu eğitimde Aspose.Words for .NET'in sınırsız bölüm özelliğini kullanma adımlarında size rehberlik edeceğiz. Bu özellik, belgenin geri kalanı korunsa bile, bir Word belgesinde korunmayan belirli bölümleri tanımlamanıza olanak tanır. Aşağıdaki adımları takip et:

## Adım 1: Belgeyi ve Bölümleri Oluşturma

Document sınıfının bir örneğini ve bir DocumentBuilder nesnesini oluşturarak başlayın:

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

Bölüm koruması yalnızca belge koruması etkinleştirildiğinde çalışır ve yalnızca form alanlarında düzenlemeye izin verilir. Belgeyi, Document nesnesinin Koruma() yöntemini kullanarak koruyabilirsiniz:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Doğru koruma türünü belirttiğinizden ve istediğiniz şifreyi ayarladığınızdan emin olun.

## 4. Adım: Belirli bir bölüm için korumayı devre dışı bırakma

Varsayılan olarak tüm bölümler korunur, ancak Bölüm nesnesinin KorumalıForForms özelliğini kullanarak belirli bir bölüm için korumayı seçerek devre dışı bırakabilirsiniz:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

Bu örnekte, ilk bölüm için koruma devre dışı bırakılmıştır.

## 5. Adım: Belgeyi kaydedin

Son olarak değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Belgeyi sınırsız bölümlerle kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanan Kısıtlanmamış Bölüm için örnek kaynak kodu

Aspose.Words for .NET kullanan sınırsız bölümün kaynak kodunun tamamı burada:


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

//Varsayılan olarak tüm bölümler korunur, ancak korumayı seçerek kapatabiliriz.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Bu adımları takip ederek Aspose.Words for .NET ile Word belgenizdeki sınırsız bölümleri kolayca tanımlayabileceksiniz.

## Çözüm

Bu eğitimde, Aspose.Words for .NET'in, Word belgesindeki belirli bölümlerin korumasız kalmasına ve belgenin geri kalanının korunmasına olanak tanıyan sınırsız bölüm özelliğini inceledik. Sağlanan adımları izleyerek, belgenizde, diğer bölümlerin korumasını korurken kullanıcıların içeriği serbestçe düzenleyebileceği bölümleri kolayca tanımlayabilirsiniz. Aspose.Words for .NET, belge koruması ve özelleştirme için güçlü yetenekler sunarak, Word belgelerinizdeki düzenleme izinleri üzerinde kontrol sahibi olmanızı sağlar.

### Word belgesindeki sınırsız bölüm için SSS

#### S: Aspose.Words for .NET'te sınırsız bölümler nelerdir?

C: Aspose.Words for .NET'teki sınırsız bölümler, belgenin geri kalanı korunsa bile, Word belgesindeki korunmayan belirli bölümlerdir. Bu bölümler, kullanıcıların belgenin geri kalan bölümleri için korumayı sürdürürken içlerindeki içeriği değiştirmelerine olanak tanır.

#### S: Aspose.Words for .NET'i kullanarak nasıl sınırsız bölümler oluşturabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinde sınırsız bölümler oluşturmak için şu adımları takip edebilirsiniz:
1.  Bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` nesne.
2.  Kullan`DocumentBuilder` Belgeye içerik eklemek ve bölüm sonları eklemek için.
3.  Belgeyi kullanarak koruyun`Protect` yöntemi`Document` İstenilen koruma tipini ve şifreyi belirterek nesneyi seçin.
4.  Ayarlayarak belirli bir bölüm için korumayı devre dışı bırakın`ProtectedForForms` karşılık gelen mülk`Section` itiraz etmek`false`.
5. Değiştirilen belgeyi kaydedin.

#### S: Bir Word belgesinde birden fazla sınırsız bölüme sahip olabilir miyim?

 C: Evet, bir Word belgesinde birden fazla sınırsız bölüm bulunabilir. Belirli bölümler için korumayı seçerek devre dışı bırakarak`ProtectedForForms` mülkiyeti`Section`nesnesinde, diğer bölümleri korurken kullanıcıların içeriği serbestçe değiştirebileceği birden fazla bölüm tanımlayabilirsiniz.

#### S4. Başlangıçta korunan bir bölümün korumasını kaldırabilir miyim?
 Evet, başlangıçta korunan bir bölümün korumasını aşağıdaki ayarları yaparak kaldırabilirsiniz:`ProtectedForForms` karşılık gelen mülk`Section` itiraz etmek`false`. Bu, kullanıcıların söz konusu bölümdeki içeriği herhangi bir kısıtlama olmaksızın düzenlemesine olanak tanır.

#### S: Bir Word belgesine hangi koruma türleri uygulanabilir?

C: Aspose.Words for .NET, bir Word belgesine uygulanabilecek çeşitli koruma türleri sağlar; örneğin:
- Koruma Yok: Hiçbir koruma uygulanmaz.
- AllowOnlyRevisions: Kullanıcılar yalnızca belgede revizyon yapabilir.
- AllowOnlyComments: Kullanıcılar belgeye yalnızca yorum ekleyebilir.
- AllowOnlyFormFields: Kullanıcılar yalnızca belgedeki form alanlarını düzenleyebilir.
- Salt Okunur: Belge salt okunurdur ve düzenleme yapılmasına izin verilmez.


