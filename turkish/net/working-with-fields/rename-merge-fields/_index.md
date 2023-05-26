---
title: Birleştirme Alanlarını Yeniden Adlandırın
linktitle: Birleştirme Alanlarını Yeniden Adlandırın
second_title: Aspose.Words for .NET API Referansı
description: Bu öğreticide, Aspose.Words for .NET kullanarak bir belgedeki birleştirme alanlarını nasıl yeniden adlandıracağınızı öğreneceksiniz.
type: docs
weight: 10
url: /tr/net/working-with-fields/rename-merge-fields/
---

Aspose.Words for .NET'in birleştirme alanı yeniden adlandırma özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice izleyin.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi oluşturma ve birleştirme alanlarını ekleme

 Yeni bir belge oluşturarak başlıyoruz ve bir`DocumentBuilder` birleştirme alanlarını eklemek için.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## 3. Adım: Birleştirme Alanlarını Yeniden Adlandırma

Belge aralığındaki her alan arasında dolaşıyoruz ve bu bir birleştirme alanıysa, " ekleyerek alanı yeniden adlandırıyoruz._Yeniden adlandırılmış" soneki.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## 4. Adım: Belgeyi kaydetme

 Son olarak, diyoruz`Save()` değiştirilen belgeyi kaydetme yöntemi.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Aspose.Words for .NET ile birleştirme alanlarını yeniden adlandırmak için kaynak kodu örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi oluşturun ve birleştirme alanlarını ekleyin.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Birleştirme alanlarını yeniden adlandırın.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Belgeyi kaydedin.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Aspose.Words for .NET kullanarak belgenizdeki birleştirme alanlarını yeniden adlandırmak için bu adımları izleyin.