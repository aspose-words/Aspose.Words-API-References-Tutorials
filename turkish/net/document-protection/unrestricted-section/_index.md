---
title: Word Belgesinde Sınırsız Bölüm
linktitle: Word Belgesinde Sınırsız Bölüm
second_title: Aspose.Words Belge İşleme API'sı
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

Varsayılan olarak, tüm bölümler korumalıdır, ancak Section nesnesinin ProtectedForForms özelliğini kullanarak belirli bir bölüm için korumayı seçerek devre dışı bırakabilirsiniz:

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

//Varsayılan olarak, tüm bölümler korumalıdır, ancak korumayı seçerek kapatabiliriz.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Bu adımları izleyerek, Aspose.Words for .NET ile Word belgenizde sınırsız bölümleri kolayca tanımlayabileceksiniz.

## Çözüm

Bu eğitimde, Aspose.Words for .NET'in, bir Word belgesindeki belirli bölümlerin, belgenin geri kalanı korunurken korumasız kalmasına izin veren sınırsız bölüm özelliğini inceledik. Sağlanan adımları izleyerek, belgenizde, kullanıcıların diğer bölümlerin korumasını sürdürürken içeriği özgürce düzenleyebileceği bölümleri kolayca tanımlayabilirsiniz. Aspose.Words for .NET, belge koruma ve özelleştirme için güçlü yetenekler sunarak Word belgelerinizdeki düzenleme izinleri üzerinde kontrol sahibi olmanızı sağlar.

### Word belgesinde sınırsız bölüm için SSS

#### S: Aspose.Words for .NET'te sınırsız bölümler nelerdir?

C: Aspose.Words for .NET'teki sınırsız bölümler, belgenin geri kalanı korumalı olsa bile bir Word belgesinde korunmayan belirli bölümlerdir. Bu bölümler, kullanıcıların belgenin geri kalan bölümleri için koruma sağlarken içlerindeki içeriği değiştirmelerine olanak tanır.

#### S: Aspose.Words for .NET kullanarak kısıtlamasız bölümleri nasıl oluşturabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinde kısıtlanmamış bölümler oluşturmak için şu adımları takip edebilirsiniz:
1.  örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` nesne.
2.  Kullan`DocumentBuilder` belgeye içerik eklemek ve bölüm sonları eklemek için.
3.  kullanarak belgeyi koruyun.`Protect` yöntemi`Document` nesne, istenen koruma tipini ve şifreyi belirterek.
4.  ayarlayarak belirli bir bölüm için korumayı devre dışı bırakın.`ProtectedForForms` karşılık gelen özellik`Section` itiraz etmek`false`.
5. Değiştirilen belgeyi kaydedin.

#### S: Bir Word belgesinde birden fazla kısıtlanmamış bölüme sahip olabilir miyim?

 C: Evet, bir Word belgesinde birden çok sınırsız bölümünüz olabilir. kullanarak belirli bölümler için korumayı seçerek devre dışı bırakarak`ProtectedForForms` mülkiyeti`Section`nesne, kullanıcıların diğer bölümleri korurken içeriği özgürce değiştirebileceği birden çok bölüm tanımlayabilirsiniz.

#### S4. Başlangıçta korunan bir bölümden korumayı kaldırabilir miyim?
 Evet, ayarlayarak başlangıçta korunan bir bölümden korumayı kaldırabilirsiniz.`ProtectedForForms` karşılık gelen özellik`Section` itiraz etmek`false`. Bu, kullanıcıların söz konusu bölümdeki içeriği herhangi bir kısıtlama olmaksızın düzenlemesine olanak tanır.

#### S: Bir Word belgesine hangi koruma türleri uygulanabilir?

C: Aspose.Words for .NET, bir Word belgesine uygulanabilen çeşitli koruma türleri sağlar, bunlar arasında:
- Koruma Yok: Koruma uygulanmaz.
- AllowOnlyRevisions: Kullanıcılar belgede yalnızca düzeltmeler yapabilir.
- AllowOnlyComments: Kullanıcılar belgeye yalnızca yorum ekleyebilir.
- AllowOnlyFormFields: Kullanıcılar belgedeki yalnızca form alanlarını düzenleyebilir.
- Salt Okunur: Belge salt okunurdur ve düzenlemeye izin verilmez.


