---
title: Belge Oluşturucu Olmadan TOA Alanını Ekle
linktitle: Belge Oluşturucu Olmadan TOA Alanını Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Document Builder olmadan TOA alanı eklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-toafield-without-document-builder/
---

Aşağıda Aspose.Words for .NET'in "TOA Alan Ekleme" özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstenilen sonuçları elde etmek için her adımı dikkatlice izleyin.

## Adım 1: Belge Dizini Kurulumu

Verilen kodda belgelerinizin dizinini belirtmelisiniz. "BELGE DİZİNİNİZ" değerini, belge dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi ve Paragrafı Oluşturma

Yeni bir belge oluşturup bir paragrafı başlatarak başlıyoruz.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 3. Adım: TA alanını ekleme

Paragrafa TA alanı eklemek için FieldTA sınıfını kullanıyoruz.

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

## Adım 6: TOA alanını ekleme

Paragrafa TOA alanı eklemek için FieldToa sınıfını kullanıyoruz.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Adım 7: Paragrafı belgenin gövdesine ekleme

TOA alanını içeren paragrafı belgenin gövdesine ekliyoruz.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 8. Adım: TOA Alanını Güncelleyin

 Son olarak şunu diyoruz:`Update()` TOA alanını güncelleme yöntemi.

```csharp
fieldToa.Update();
```

### Aspose.Words for .NET ile Document Builder olmadan TOA alanı eklemeye yönelik kaynak kodu örneği

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// TA ve TOA alanlarını şu şekilde eklemek istiyoruz:
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

### SSS'ler

#### S: Aspose.Words for .NET ile Word belgesine eklenen TOA alanının görünümü nasıl özelleştirilir?

C: Eklenen TOA alanının görünümünü, TOA alanının özelliklerini kullanarak özelleştirebilirsiniz.`FieldTOA` Biçimlendirme seçeneklerini belirtmek için nesne.

#### S: Aspose.Words for .NET'i kullanarak tek bir Word belgesine birden fazla TOA alanı ekleyebilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak tek bir Word belgesine birden fazla TOA alanı ekleyebilirsiniz. Her alan için ekleme adımlarını tekrarlamanız yeterlidir.

#### S: TOA alanının Aspose.Words for .NET ile Word belgesine başarıyla eklenip eklenmediğini nasıl kontrol edebilirim?

C: TOA alanının başarıyla eklenip eklenmediğini kontrol etmek için belge içeriğine göz atabilir ve TOA alanı örneklerini arayabilirsiniz.

#### S: DocumentBuilder kullanmadan TOA alanı eklemek Aspose.Words for .NET ile Word belgesi formatını etkiler mi?

C: DocumentBuilder'ı kullanmadan TOA alanı eklemek, Word belgesinin biçimlendirmesini doğrudan etkilemez. Ancak TOA alanı biçimlendirme seçenekleri belgenin genel biçimlendirmesini etkileyebilir.