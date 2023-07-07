---
title: Belge Oluşturucu Olmadan TOA Alanı Ekle
linktitle: Belge Oluşturucu Olmadan TOA Alanı Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Document Builder olmadan TOA alanı eklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-toafield-without-document-builder/
---

Aspose.Words for .NET'in "TOA Alan Ekleme" özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice izleyin.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi ve Paragrafı Oluşturma

Yeni bir belge oluşturarak ve bir paragraf başlatarak başlıyoruz.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 3. Adım: TA alanını ekleme

Paragrafa bir TA alanı eklemek için FieldTA sınıfını kullanırız.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Adım 4: Paragrafı belgenin gövdesine ekleme

TA alanını içeren paragrafı belgenin gövdesine ekliyoruz.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Adım 5: TOA alanı için paragraf oluşturma

TOA alanı için yeni bir paragraf oluşturuyoruz.

```csharp
para = new Paragraph(doc);
```

## 6. Adım: TOA alanını ekleme

Paragrafa bir TOA alanı eklemek için FieldToa sınıfını kullanırız.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Adım 7: Belgenin gövdesine paragraf ekleme

TOA alanını içeren paragrafı belgenin gövdesine ekliyoruz.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 8. Adım: TOA Alanını Güncelleyin

 Son olarak, diyoruz`Update()` TOA alanını güncelleme yöntemi.

```csharp
fieldToa.Update();
```

### Aspose.Words for .NET ile Document Builder olmadan TOA alanı ekleme için kaynak kodu örneği

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Bunun gibi TA ve TOA alanları eklemek istiyoruz:
// { TA \c 1 \l "Değer 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### SSS

#### S: Aspose.Words for .NET ile Word belgesine eklenen TOA alanının görünümü nasıl özelleştirilir?

C: Eklenen TOA alanının görünümünü, özelliklerini kullanarak özelleştirebilirsiniz.`FieldTOA` biçimlendirme seçeneklerini belirtmek için nesne.

#### S: Aspose.Words for .NET kullanarak tek bir Word belgesine birden fazla TOA alanı ekleyebilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak tek bir Word belgesine birden fazla TOA alanı ekleyebilirsiniz. Her alan için ekleme adımlarını tekrarlamanız yeterlidir.

#### S: Aspose.Words for .NET ile bir TOA alanının bir Word belgesine başarıyla eklenip eklenmediğini nasıl kontrol edebilirim?

Y: Bir TOA alanının başarıyla eklenip eklenmediğini kontrol etmek için, belge içeriğine göz atabilir ve TOA alanı örneklerini arayabilirsiniz.

#### S: DocumentBuilder kullanmadan bir TOA alanı eklemek, Aspose.Words for .NET ile Word belgesi biçimlendirmesini etkiler mi?

A: DocumentBuilder kullanmadan bir TOA alanı eklemek, Word belgesinin biçimlendirmesini doğrudan etkilemez. Ancak TOA alanı biçimlendirme seçenekleri, belgenin genel biçimlendirmesini etkileyebilir.