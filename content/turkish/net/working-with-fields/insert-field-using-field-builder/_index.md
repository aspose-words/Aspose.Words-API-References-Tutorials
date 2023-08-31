---
title: Field Builder'ı Kullanarak Alan Ekle
linktitle: Field Builder'ı Kullanarak Alan Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinize özel alanları nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-field-using-field-builder/
---

Aşağıda Aspose.Words for .NET'in "FieldBuilder Kullanarak Alan Ekle" özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstediğiniz sonuçları elde etmek için her adımı dikkatlice takip ettiğinizden emin olun.

## Adım 1: Belge Dizini Kurulumu

Verilen kodda belgelerinizin dizinini belirtmelisiniz. "BELGE DİZİNİNİZ" değerini, belge dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi oluşturma

Yeni bir belge oluşturarak başlıyoruz.

```csharp
Document doc = new Document();
```

## 3. Adım: FieldBuilder'ı kullanarak IF alanını oluşturma

İç içe geçmiş iki MERGEFIELD alanına sahip bir IF alanı oluşturmak için FieldBuilder sınıfını kullanırız. Bu örnekte, EĞER alanı bir koşula göre ad ve soyadı görüntüler.

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

## Adım 4: IF alanını belgeye ekleme

 biz kullanıyoruz`BuildAndInsert()` IF alanını belgede belirli bir konuma oluşturma ve ekleme yöntemi.

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

// IF alanını belgeye ekleyin.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

Bu örnekte yeni bir belge oluşturduk, iç içe geçmiş MERGEFIELD alanlarıyla bir IF alanı oluşturduk ve ardından bu alanı belgenin belirli bir konumuna ekledik. Belge daha sonra belirli bir dosya adıyla kaydedilir.

### SSS'ler

#### S: Aspose.Words'te alan yapıcı nedir?

C: Aspose.Words'teki Field Builder, bir Word belgesinde alanlar oluşturmak ve değiştirmek için güçlü bir araçtır. Alan kodları ekleme ve biçimlendirme seçeneklerini yönetme de dahil olmak üzere, alanları oluşturmak ve özelleştirmek için gelişmiş özellikler sunar.

#### S: Alan oluşturucu kullanılarak ne tür alanlar eklenebilir?

C: Aspose.Words'teki alan oluşturucu, bir Word belgesine farklı türde alanlar eklemenizi sağlar. Yaygın olarak kullanılan alan türlerine bazı örnekler:

- MERGEFIELD: harici kaynaklardan gelen verileri birleştirmek için kullanılır.
- TARİH: Geçerli tarihi görüntüler.
- SAYFA: geçerli sayfa numarasını görüntüler.
- IF: bir içeriğin görüntülenmesini bir koşula göre koşullandırmayı sağlar.
- TOC: belge başlık stillerine göre otomatik olarak bir içindekiler tablosu oluşturur.

#### S: Alan oluşturucuyla eklenen alanlar nasıl özelleştirilir?

C: Alan oluşturucu, eklenen alanlar için özelleştirme seçenekleri sunar. Alan biçimlendirmesi, bağımsız değişkenler, anahtarlar ve varsayılan değerler gibi seçenekleri ayarlamak için alan oluşturucu yöntemlerini ve özelliklerini kullanabilirsiniz. Örneğin tarih biçimini, sayı biçimini, binlik ayırıcıyı vb. ayarlayabilirsiniz.
  