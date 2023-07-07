---
title: Field Builder'ı Kullanarak Alan Ekleme
linktitle: Field Builder'ı Kullanarak Alan Ekleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerinize nasıl özel alanlar ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-field-using-field-builder/
---

Aspose.Words for .NET'in "FieldBuilder'ı kullanarak Alan Ekle" özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi oluşturma

Yeni bir belge oluşturarak başlıyoruz.

```csharp
Document doc = new Document();
```

## 3. Adım: FieldBuilder kullanarak IF alanını oluşturma

FieldBuilder sınıfını, iç içe geçmiş iki MERGFIELD alanıyla bir EĞER alanı oluşturmak için kullanıyoruz. Bu örnekte, EĞER alanı bir koşula göre adı ve soyadı görüntüler.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Adım 4: EĞER alanını belgeye ekleme

 biz kullanıyoruz`BuildAndInsert()` EĞER alanını belgede belirli bir konuma oluşturma ve ekleme yöntemi.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Aspose.Words for .NET ile FieldBuilder kullanarak alan eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma.
Document doc = new Document();

// FieldBuilder kullanılarak IF alanının oluşturulması.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// EĞER alanını belgeye ekleyin.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

Bu örnekte, yeni bir belge oluşturduk, iç içe geçmiş MERGFIELD alanlarıyla bir IF alanı oluşturduk ve ardından bu alanı belgenin belirli bir konumuna ekledik. Belge daha sonra belirli bir dosya adıyla kaydedilir.

### SSS

#### S: Aspose.Words'te alan oluşturucu nedir?

C: Aspose.Words'ta bir Alan Oluşturucu, bir Word belgesinde alanlar oluşturmak ve değiştirmek için güçlü bir araçtır. Alan kodları ekleme ve biçimlendirme seçeneklerini yönetme dahil olmak üzere alanları oluşturmak ve özelleştirmek için gelişmiş özellikler sunar.

#### S: Alan oluşturucu kullanılarak ne tür alanlar eklenebilir?

C: Aspose.Words'deki alan oluşturucu, bir Word belgesine farklı türde alanlar eklemenize izin verir. Yaygın olarak kullanılan alan türlerine ilişkin bazı örnekler aşağıda verilmiştir:

- MERGFIELD: Dış kaynaklardan gelen verileri birleştirmek için kullanılır.
- TARİH: geçerli tarihi görüntüler.
- SAYFA: geçerli sayfa numarasını görüntüler.
- IF: bir içeriğin görüntülenmesini bir koşula göre koşullandırmaya izin verir.
- TOC: belge başlık stillerine göre otomatik olarak bir içindekiler tablosu oluşturur.

#### S: Alan oluşturucu ile eklenen alanlar nasıl özelleştirilir?

A: Alan oluşturucu, eklenen alanlar için özelleştirme seçenekleri sunar. Alan biçimlendirmesi, bağımsız değişkenler, anahtarlar ve varsayılan değerler gibi seçenekleri ayarlamak için alan oluşturucu yöntemlerini ve özelliklerini kullanabilirsiniz. Örneğin, tarih biçimini, sayı biçimini, binler ayırıcısını vb. ayarlayabilirsiniz.
  