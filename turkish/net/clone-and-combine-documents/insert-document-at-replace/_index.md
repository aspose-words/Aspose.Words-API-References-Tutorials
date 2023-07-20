---
title: Değiştirme Sırasında Belge Ekle
linktitle: Değiştirme Sırasında Belge Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak değiştirme sırasında nasıl belge ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/insert-document-at-replace/
---
Bu eğitimde, Aspose.Words for .NET'in Insert Document When Changeing özelliğini kullanarak değiştirirken bir belgeyi başka bir belgeye nasıl ekleyeceğinizi size göstereceğiz. Kaynak kodunu anlamak ve belge ekleme işlemini gerçekleştirmek için aşağıdaki adımları izleyin.

## 1. Adım: Ana belgenin yüklenmesi

Başlamak için belgeleriniz için dizini belirtin ve ana belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 2. Adım: Arama ve değiştirme seçeneklerini yapılandırın

Şimdi bir belgeyi başka bir belgeye eklemek için arama yönünü ve geri aramayı değiştir'i belirterek bul ve değiştir seçeneklerini yapılandıracağız. İşte nasıl:

```csharp
// Arama ve değiştirme seçeneklerini yapılandırın.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## 3. Adım: Değiştirme yöntemini çağırma

Şimdi, yapılandırılmış seçenekleri kullanarak belirtilen metni bulup boş bir dizeyle değiştirmek için replace yöntemini çağıracağız. İşte nasıl:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Aspose.Words for .NET kullanarak Insert Document At Change için örnek kaynak kodu

Aspose.Words for .NET'i değiştirirken Belge Ekle özelliğinin tam kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Bul ve değiştir seçeneklerini ayarlayın.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// replace yöntemini çağırın.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET'in Insert Document When Changeing özelliğini kullanarak değiştirme sırasında başka bir belgeye nasıl belge ekleneceğini inceledik. Bul ve değiştir seçeneklerini yapılandırarak ve gerekli verileri sağlayarak, belirli yer tutucuları diğer belge şablonlarının veya bölümlerinin içerikleriyle değiştirerek belgeleri dinamik olarak bir araya getirebilirsiniz. Aspose.Words for .NET, karmaşık belge işleme görevlerini yönetmek için güçlü ve esnek bir yol sunarak, belge oluşturma ve içerik ekleme senaryolarını otomatikleştirmek için onu değerli bir araç haline getirir.

### SSS

#### S: Değiştirme sırasında bir belgeyi başka bir belgeye eklemenin amacı nedir?

C: Değiştirme sırasında bir belgeyi başka bir belgeye eklemek, belirli bir yer tutucuyu dinamik olarak ayrı bir belgenin içeriğiyle değiştirmenize olanak tanır. Bu özellik, çeşitli önceden tanımlanmış belge şablonlarını veya bölümleri belirli yer tutucularda birleştirerek daha büyük bir belgeyi birleştirmek istediğinizde özellikle kullanışlıdır.

#### S: Aspose.Words for .NET kullanarak değiştirme sırasında bir belgeyi başka bir belgeye nasıl ekleyebilirim?

C: Aspose.Words for .NET kullanarak değiştirme sırasında başka bir belgeye belge eklemek için şu adımları izleyin:
1. Yer tutucuları içeren ana belgeyi bir Belge nesnesine yükleyin.
2. Belge eklemeyi işlemek için arama yönü ve geri aramayı değiştir dahil olmak üzere bul ve değiştir seçeneklerini yapılandırın.
3. Yapılandırılan seçenekleri kullanarak yer tutucuları boş bir dizeyle değiştirerek, replace yöntemini uygun arama modeliyle çağırın.

#### S: Değiştirme sırasında ekleme davranışını özelleştirebilir miyim?

Y: Evet, özel bir ReplasmanGeri Çağırma uygulayarak değiştirme sırasında ekleme davranışını özelleştirebilirsiniz. IReplacingCallback arayüzünden devralarak, yer tutucuları değiştirirken özel gereksinimlerinize göre belgelerin nasıl ekleneceğini ve birleştirileceğini kontrol edebilirsiniz.

#### S: Birden çok yer tutucuyu farklı belgelerle değiştirebilir miyim?

C: Evet, her bir yer tutucu için uygun arama kalıplarını belirleyerek ve eklenecek ilgili belgeleri sağlayarak birden çok yer tutucuyu farklı belgelerle değiştirebilirsiniz.