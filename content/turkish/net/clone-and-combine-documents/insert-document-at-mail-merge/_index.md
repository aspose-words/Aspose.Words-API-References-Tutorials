---
title: Adres Mektup Birleştirmede Belgeyi Ekle
linktitle: Adres Mektup Birleştirmede Belgeyi Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak adres-mektup birleştirme sırasında belgeyi başka bir belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
Bu eğitimde, Aspose.Words for .NET'in Adres Mektup Birleştirme Sırasında Belge Ekle özelliğini kullanarak adres-mektup birleştirme sırasında başka bir belgeye nasıl belge ekleyeceğinizi anlatacağız. Kaynak kodunu anlamak ve belge ekleme işlemini gerçekleştirmek için aşağıdaki adımları izleyin.

## 1. Adım: Ana belgeyi yükleme

Başlamak için belgelerinizin dizini belirtin ve ana belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 2. Adım: Adres Mektup Birleştirmeyi Yapılandırma

Şimdi adres-mektup birleştirmeyi yapılandıralım ve bir belgeyi başka bir belgeye eklemek için alan birleştirme geri çağrısını belirtelim. İşte nasıl:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## 3. Adım: Adres Mektup Birleştirmeyi Çalıştırma

Adres-mektup birleştirmeyi, birleştirme alanlarının adlarını ve ilgili verileri sağlayarak çalıştıracağız. İşte nasıl:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Aspose.Words for .NET kullanarak Adres Mektup Birleştirmede Belge Ekle için örnek kaynak kodu

Aspose.Words for .NET'in Adres Mektup Birleştirmede Belge Ekle özelliğinin tam kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Ana belgenin içinde "Belge_1" adında bir birleştirme alanı vardır.
// Bu alana karşılık gelen veriler, belgeye giden tam yolu içerir.
// Bu alana eklenmesi gerekir.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Bu kodla, Aspose.Words for .NET'i kullanarak adres-mektup birleştirme sırasında bir belgeyi başka bir belgeye ekleyebileceksiniz. Ortaya çıkan belge yeni bir adla kaydedilecek


## Çözüm

Bu eğitimde, Aspose.Words for .NET'in Adres Mektup Birleştirme Sırasında Belge Ekle özelliğini kullanarak adres-mektup birleştirme sırasında başka bir belgeye nasıl belge ekleneceğini araştırdık. Adres-mektup birleştirmeyi yapılandırarak ve gerekli verileri sağlayarak, çeşitli belge şablonlarını veya bölümlerini birleştirerek belgeleri dinamik olarak bir araya getirebilirsiniz. Aspose.Words for .NET, karmaşık belge oluşturma senaryolarını yönetmek için esnek ve güçlü bir yol sağlayarak onu belge oluşturma ve düzenleme görevlerini otomatikleştirmek için değerli bir araç haline getirir.

### SSS'ler

#### S: Adres-mektup birleştirme sırasında bir belgeyi başka bir belgeye eklemenin amacı nedir?

C: Adres-mektup birleştirme sırasında bir belgeyi başka bir belgeye eklemek, birleştirme işlemi sırasında sağlanan verilere dayalı olarak farklı belge şablonlarını veya bölümlerini dinamik olarak birleştirmenize olanak tanır. Bu özellik, önceden tanımlanmış çeşitli şablonları veya bölümleri nihai bir belgede birleştirerek karmaşık belgeleri birleştirmek istediğinizde özellikle kullanışlıdır.

#### S: Aspose.Words for .NET kullanarak adres-mektup birleştirme sırasında bir belgeyi başka bir belgeye nasıl eklerim?

C: Aspose.Words for .NET kullanarak adres-mektup birleştirme sırasında başka bir belgeye belge eklemek için şu adımları izleyin:
1. Temel görevi görecek ana belgeyi bir Document nesnesine yükleyin.
2. Adres-mektup birleştirmeyi yapılandırın ve belge ekleme işlemini gerçekleştirmek için alan birleştirme geri çağrısını belirtin.
3. Adres-mektup birleştirmeyi, birleştirme alanlarının adlarıyla ve karşılık gelen verilerle (eklenecek belgenin yolu) çalıştırın.

#### S: Adres-mektup birleştirme sırasında ekleme davranışını nasıl özelleştirebilirim?

C: Adres-mektup birleştirme sırasında ekleme davranışını özelleştirmek için, IFieldMergingCallback arabiriminden devralarak özel bir FieldMergingCallback uygulayabilirsiniz. Bu, özel gereksinimlerinize göre belgelerin nasıl eklendiğini ve birleştirildiğini kontrol etmenize olanak tanır.

#### S: Adres-mektup birleştirme sırasında birden fazla belge ekleyebilir miyim?

C: Evet, her birleştirme alanı için uygun verileri sağlayarak adres-mektup birleştirme sırasında birden çok belge ekleyebilirsiniz. Belge eklenmesini gerektiren her birleştirme alanı için, ilgili belgenin yolunu veri olarak belirtin.


