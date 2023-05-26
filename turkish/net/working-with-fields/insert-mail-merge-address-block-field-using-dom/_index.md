---
title: DOM Kullanarak Adres Mektup Birleştirme Adres Bloğu Alanı Ekleme
linktitle: DOM Kullanarak Adres Mektup Birleştirme Adres Bloğu Alanı Ekleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerinize adres mektup birleştirme adres bloğu alanını nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Aspose.Words for .NET'in "Adres Mektup Birleştirme Adres Bloğu Alanı Ekle" özelliğini kullanan aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Document ve DocumentBuilder'ı Oluşturma

Yeni bir belge oluşturarak ve bir DocumentBuilder başlatarak başlıyoruz.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: İmleci paragrafa taşıma

 DocumentBuilder'ı kullanıyoruz`MoveTo()` imleci adres mektup birleştirme adres bloğu alanını eklemek istediğimiz paragrafa taşıma yöntemi.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## 4. Adım: Adres Mektup Birleştirme Adres Bloğu Alanını Ekleme

 DocumentBuilder'ı kullanıyoruz`InsertField()` Paragrafa adres mektup birleştirme adres bloğu alanı ekleme yöntemi.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Ardından, ülke/bölge adını dahil etme, adresi ülkeye/bölgeye göre biçimlendirme, hariç tutulan ülke/bölge adları, ad ve adres biçimi ve dil tanımlayıcı gibi uygun seçenekleri belirterek adres bloğu alanının özelliklerini yapılandırırız.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Son olarak, diyoruz`Update()` alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile adres mektup birleştirme adres bloğu alanı eklemek için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Bunun gibi bir adres mektup birleştirme adres bloğu eklemek istiyoruz:
// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { ADRES BLOĞU \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { ADRES BLOĞU \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ADRES BLOĞU \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
