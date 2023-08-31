---
title: Adres Mektup Birleştirmede Belge Ekle
linktitle: Adres Mektup Birleştirmede Belge Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'i kullanarak adres-mektup birleştirme sırasında diğerine nasıl belge ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
Bu eğitimde, Aspose.Words for .NET'in Adres Mektup Birleştirme Sırasında Belge Ekle özelliğini kullanarak adres mektup birleştirme sırasında başka bir belgeye nasıl belge ekleyeceğinizi göstereceğiz. Kaynak kodunu anlamak ve belge ekleme işlemini gerçekleştirmek için aşağıdaki adımları izleyin.

## 1. Adım: Ana belgenin yüklenmesi

Başlamak için belgeleriniz için dizini belirtin ve ana belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 2. Adım: Adres Mektup Birleştirmeyi Yapılandırın

Şimdi adres mektup birleştirmeyi yapılandıralım ve başka bir belgeye belge eklemek için alan birleştirme geri aramasını belirleyelim. İşte nasıl:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## 3. Adım: Adres Mektup Birleştirmeyi Çalıştırma

Birleştirme alanlarının adlarını ve karşılık gelen verileri sağlayarak adres mektup birleştirmeyi çalıştıracağız. İşte nasıl:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Aspose.Words for .NET kullanarak Adres Mektup Birleştirmede Belge Ekleme için örnek kaynak kodu

Aspose.Words for .NET'in Adres Mektup Birleştirmede Belge Ekle özelliğinin tam kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Ana belgenin içinde "Belge_1" adlı bir birleştirme alanı vardır.
// Bu alan için karşılık gelen veriler, belgeye giden tam nitelikli bir yol içerir.
// Bu alana girilmelidir.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Bu kodla, Aspose.Words for .NET kullanarak adres mektup birleştirme sırasında başka bir belgeye belge ekleyebileceksiniz. Ortaya çıkan belge yeni bir adla kaydedilecek


## Çözüm

Bu eğitimde, Aspose.Words for .NET'in Adres Mektup Birleştirme Sırasında Belge Ekle özelliğini kullanarak adres mektup birleştirme sırasında başka bir belgeye nasıl belge ekleneceğini inceledik. Adres mektup birleştirmeyi yapılandırarak ve gerekli verileri sağlayarak, çeşitli belge şablonlarını veya bölümlerini birleştirerek belgeleri dinamik olarak bir araya getirebilirsiniz. Aspose.Words for .NET, karmaşık belge oluşturma senaryolarını yönetmenin esnek ve güçlü bir yolunu sunarak, onu belge oluşturma ve değiştirme görevlerini otomatikleştirmek için değerli bir araç haline getirir.

### SSS

#### S: Adres mektup birleştirme sırasında bir belgeyi başka bir belgeye eklemenin amacı nedir?

C: Adres mektup birleştirme sırasında başka bir belgeye belge eklemek, birleştirme işlemi sırasında sağlanan verilere dayalı olarak farklı belge şablonlarını veya bölümleri dinamik olarak birleştirmenize olanak tanır. Bu özellik, önceden tanımlanmış çeşitli şablonları veya bölümleri nihai bir belgede birleştirerek karmaşık belgeleri bir araya getirmek istediğinizde özellikle kullanışlıdır.

#### S: Adres mektup birleştirme sırasında Aspose.Words for .NET kullanarak bir belgeyi başka bir belgeye nasıl ekleyebilirim?

Y: Adres mektup birleştirme sırasında Aspose.Words for .NET kullanarak bir belgeyi başka bir belgeye eklemek için şu adımları izleyin:
1. Temel olarak hizmet edecek ana belgeyi bir Belge nesnesine yükleyin.
2. Adres mektup birleştirmeyi yapılandırın ve belge eklemeyi işlemek için alan birleştirme geri aramasını belirtin.
3. Birleştirme alanlarının adları ve karşılık gelen verilerle (eklenecek belgenin yolu) adres mektup birleştirmeyi çalıştırın.

#### S: Adres mektup birleştirme sırasında ekleme davranışını nasıl özelleştirebilirim?

Y: Adres mektup birleştirme sırasında ekleme davranışını özelleştirmek için, IFieldMergingCallback arabiriminden devralarak özel bir FieldMergingCallback uygulayabilirsiniz. Bu, özel gereksinimlerinize göre belgelerin nasıl eklendiğini ve birleştirildiğini kontrol etmenizi sağlar.

#### S: Adres mektup birleştirme sırasında birden çok belge ekleyebilir miyim?

Y: Evet, adres mektup birleştirme sırasında her bir birleştirme alanı için uygun verileri sağlayarak birden çok belge ekleyebilirsiniz. Belge eklenmesini gerektiren her bir birleştirme alanı için, ilgili belgenin yolunu veri olarak belirtin.


