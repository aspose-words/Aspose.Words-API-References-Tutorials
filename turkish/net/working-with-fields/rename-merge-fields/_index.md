---
title: Birleştirme Alanlarını Yeniden Adlandırın
linktitle: Birleştirme Alanlarını Yeniden Adlandırın
second_title: Aspose.Words Belge İşleme API'sı
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

### SSS

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki birleştirilmiş alanları nasıl yeniden adlandırabilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesindeki birleştirilmiş alanları yeniden adlandırmak için,`FieldMergingArgs` sınıflandırın ve kullanın`FieldMergingArgs.FieldName` alanı yeniden adlandırma yöntemi.

#### S: Aspose.Words for .NET ile bir Word belgesindeki yalnızca belirli birleştirilmiş alanları yeniden adlandırmak mümkün mü?

C: Evet, Aspose.Words for .NET ile bir Word belgesindeki yalnızca belirli birleştirilmiş alanları yeniden adlandırmak mümkündür. Alan adı veya diğer ilgili özellikler gibi belirli ölçütleri kullanarak hangi alanların yeniden adlandırılacağını filtreleyebilirsiniz. Ardından ilgili alanları kullanarak yeniden adlandırabilirsiniz.`FieldMergingArgs.FieldName` yöntem.

#### S: Aspose.Words for .NET ile bir Word belgesinde birleştirilmiş bir alanın başarıyla yeniden adlandırılıp adlandırılmadığını nasıl kontrol edebilirim?

 C: Aspose.Words for .NET ile bir Word belgesinde birleştirilmiş bir alanın başarıyla yeniden adlandırılıp adlandırılmadığını kontrol etmek için`FieldMergedArgs` sınıf ve erişim`FieldMergedArgs.IsMerged` alanın hit ile yeniden adlandırılıp adlandırılmadığını belirlemek için özellik.

#### S: Bir Word belgesindeki birleştirilmiş bir alanı Aspose.Words for .NET ile yeniden adlandırmanın sonuçları nelerdir?

C: Bir Word belgesindeki birleştirilmiş bir alanı Aspose.Words for .NET ile yeniden adlandırdığınızda, belgedeki alanın adını değiştirir, bu da alan adına bağlı diğer işlevleri veya süreçleri etkileyebilir. Birleştirilmiş alanları yeniden adlandırmadan önce bu olası sonuçları göz önünde bulundurduğunuzdan emin olun.

#### S: Aspose.Words for .NET ile yeniden adlandırdıktan sonra birleştirilmiş bir alanın orijinal adını geri yüklemek mümkün müdür?

C: Evet, Aspose.Words for .NET ile yeniden adlandırdıktan sonra birleştirilmiş bir alanın orijinal adını geri yüklemek mümkündür. Alanın orijinal adını bir değişkende veya listede saklayabilir ve ardından gerekirse orijinal adı geri yüklemek için bu bilgileri kullanabilirsiniz.