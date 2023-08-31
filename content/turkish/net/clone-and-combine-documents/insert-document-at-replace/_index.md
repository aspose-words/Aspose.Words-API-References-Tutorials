---
title: Belgeyi Değiştirme Sırasına Ekle
linktitle: Belgeyi Değiştirme Sırasına Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeyi değiştirildiğinde nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/insert-document-at-replace/
---
Bu eğitimde, Aspose.Words for .NET'in Değiştirirken Belge Ekle özelliğini kullanarak bir belgeyi değiştirirken başka bir belgeye nasıl ekleyeceğinizi anlatacağız. Kaynak kodunu anlamak ve belge ekleme işlemini gerçekleştirmek için aşağıdaki adımları izleyin.

## 1. Adım: Ana belgeyi yükleme

Başlamak için belgelerinizin dizini belirtin ve ana belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 2. Adım: Arama ve değiştirme seçeneklerini yapılandırın

Şimdi, bir belgeyi başka bir belgeye eklemek için arama yönünü ve değiştirme geri çağrısını belirterek bul ve değiştir seçeneklerini yapılandıracağız. İşte nasıl:

```csharp
// Arama ve değiştirme seçeneklerini yapılandırın.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## 3. Adım: Değiştirme yöntemini çağırma

Şimdi, yapılandırılmış seçenekleri kullanarak, belirtilen metni bulup boş bir dizeyle değiştirmek için değiştirme yöntemini çağıracağız. İşte nasıl:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Aspose.Words for .NET kullanarak Değiştirme Sırasında Belge Ekle için örnek kaynak kodu

Aspose.Words for .NET'i değiştirirken Belge Ekle özelliğinin tam kaynak kodunu burada bulabilirsiniz:

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

// Değiştirme yöntemini çağırın.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Çözüm

Bu eğitimde, Aspose.Words for .NET'in Değiştirirken Belge Ekle özelliğini kullanarak değiştirme sırasında bir belgeyi başka bir belgeye nasıl ekleyeceğimizi araştırdık. Bul ve değiştir seçeneklerini yapılandırarak ve gerekli verileri sağlayarak, belirli yer tutucuları diğer belge şablonlarının veya bölümlerinin içerikleriyle değiştirerek belgeleri dinamik olarak birleştirebilirsiniz. Aspose.Words for .NET, karmaşık belge işleme görevlerini yönetmek için güçlü ve esnek bir yol sunarak onu belge oluşturma ve içerik ekleme senaryolarını otomatikleştirmek için değerli bir araç haline getiriyor.

### SSS'ler

#### S: Değiştirme sırasında bir belgeyi başka bir belgeye eklemenin amacı nedir?

C: Değiştirme sırasında bir belgeyi başka bir belgeye eklemek, belirli bir yer tutucuyu dinamik olarak ayrı bir belgenin içeriğiyle değiştirmenize olanak tanır. Bu özellik, önceden tanımlanmış çeşitli belge şablonlarını veya bölümlerini belirli yer tutucularda birleştirerek daha büyük bir belge oluşturmak istediğinizde özellikle kullanışlıdır.

#### S: Aspose.Words for .NET kullanarak değiştirme sırasında bir belgeyi başka bir belgeye nasıl eklerim?

C: Aspose.Words for .NET kullanarak değiştirme sırasında bir belgeyi başka bir belgeye eklemek için şu adımları izleyin:
1. Yer tutucuları içeren ana belgeyi bir Document nesnesine yükleyin.
2. Belge ekleme işlemini gerçekleştirmek için arama yönü ve geri aramayı değiştirme de dahil olmak üzere bul ve değiştir seçeneklerini yapılandırın.
3. Yapılandırılmış seçenekleri kullanarak yer tutucuları boş bir dizeyle değiştirerek değiştirme yöntemini uygun arama düzeniyle çağırın.

#### S: Değiştirme sırasında ekleme davranışını özelleştirebilir miyim?

C: Evet, özel bir ReplaceingCallback uygulayarak değiştirme sırasında ekleme davranışını özelleştirebilirsiniz. IReplacingCallback arayüzünden miras alarak, yer tutucuları değiştirirken özel gereksinimlerinize göre belgelerin nasıl eklendiğini ve birleştirildiğini kontrol edebilirsiniz.

#### S: Birden fazla yer tutucuyu farklı belgelerle değiştirebilir miyim?

C: Evet, her yer tutucu için uygun arama modellerini belirleyerek ve ilgili belgelerin eklenmesini sağlayarak birden çok yer tutucuyu farklı belgelerle değiştirebilirsiniz.