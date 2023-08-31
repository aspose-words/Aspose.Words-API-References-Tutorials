---
title: DOM Kullanarak Adres Mektup Birleştirme Adres Bloğu Alanı Ekleme
linktitle: DOM Kullanarak Adres Mektup Birleştirme Adres Bloğu Alanı Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinize adres-mektup birleştirme adresi bloğu alanını nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Aşağıda, Aspose.Words for .NET'in "Adres Mektup Birleştirme Adres Blok Alanını Ekle" özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstediğiniz sonuçları elde etmek için her adımı dikkatlice takip ettiğinizden emin olun.

## Adım 1: Belge Dizini Kurulumu

Verilen kodda belgelerinizin dizinini belirtmelisiniz. "BELGE DİZİNİNİZ" değerini, belge dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Document ve DocumentBuilder'ı Oluşturma

Yeni bir belge oluşturup DocumentBuilder'ı başlatarak başlıyoruz.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: İmleci paragrafa taşıma

 DocumentBuilder'ı kullanıyoruz`MoveTo()` İmleci, adres-mektup birleştirme adres bloğu alanını eklemek istediğimiz paragrafa taşıma yöntemini kullanın.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Adım 4: Adres Mektup Birleştirme Adres Bloğu Alanını Ekleme

 DocumentBuilder'ı kullanıyoruz`InsertField()` Paragrafa adres-mektup birleştirme adresi bloğu alanı ekleme yöntemi.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Daha sonra, ülke/bölge adının dahil edilmesi, adresin ülkeye/bölgeye göre biçimlendirilmesi, ülke/bölge adlarının hariç tutulması, ad ve adres biçimi ve dil tanımlayıcı gibi uygun seçenekleri belirterek adres bloğu alanının özelliklerini yapılandırırız.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Son olarak şunu diyoruz:`Update()` Alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile adres-mektup birleştirme adresi blok alanı eklemek için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Bunun gibi bir adres-mektup birleştirme adres bloğu eklemek istiyoruz:
// { ADRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { ADRESSBLOCK \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { ADRESSBLOCK \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ADRESSBLOCK \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ADRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### SSS'ler

#### S: Aspose.Words for .NET ile bir Word belgesindeki posta adresinin formatını nasıl özelleştirebilirim?

 C: Aspose.Words for .NET'in özelliklerini kullanarak bir Word belgesindeki posta adresinin biçimini özelleştirebilirsiniz.`FieldAddressBlock`nesne. İstediğiniz formatı elde etmek için adres stili, ayırıcılar, isteğe bağlı öğeler vb. gibi formatlama seçeneklerini ayarlayabilirsiniz.

#### S: Aspose.Words for .NET'te posta adresi alanının kaynak verilerini nasıl belirleyebilirim?

 C: Aspose.Words for .NET'te posta adresi alanının kaynak verilerini belirtmek için`FieldAddressBlock.StartAddress` Ve`FieldAddressBlock.EndAddress` özellikler. Bu özellikler, CSV dosyası, veritabanı vb. gibi harici veri kaynağındaki adres aralıklarını tanımlamak için kullanılır.

#### S: Aspose.Words for .NET ile posta adresi alanına isteğe bağlı öğeler ekleyebilir miyim?

 C: Evet, Aspose.Words for .NET ile posta adresi alanına isteğe bağlı öğeler ekleyebilirsiniz. İsteğe bağlı öğeleri kullanarak tanımlayabilirsiniz.`FieldAddressBlock.OmitOptional` Alıcı adı, şirket adı vb. gibi isteğe bağlı öğelerin dahil edilip edilmeyeceğini belirtme yöntemi.

#### S: DOM kullanarak posta adresi alanı eklemek Aspose.Words for .NET ile Word belgesinin yapısını etkiler mi?

C: DOM kullanarak posta adresi alanı eklemek, Word belgesinin yapısını doğrudan etkilemez. Ancak belge içeriğine yeni bir alan öğesi ekler. Mevcut öğeleri ihtiyaçlarınıza göre ekleyerek, silerek veya değiştirerek belge yapısını değiştirebilirsiniz.