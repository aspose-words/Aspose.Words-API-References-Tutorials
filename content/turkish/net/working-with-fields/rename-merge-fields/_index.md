---
title: Birleştirme Alanlarını Yeniden Adlandırın
linktitle: Birleştirme Alanlarını Yeniden Adlandırın
second_title: Aspose.Words Belge İşleme API'si
description: Bu eğitimde Aspose.Words for .NET kullanarak bir belgedeki birleştirme alanlarını nasıl yeniden adlandıracağınızı öğreneceksiniz.
type: docs
weight: 10
url: /tr/net/working-with-fields/rename-merge-fields/
---

Aşağıda Aspose.Words for .NET'in birleştirme alanı yeniden adlandırma özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstenilen sonuçları elde etmek için her adımı dikkatlice izleyin.

## Adım 1: Belge Dizini Kurulumu

Verilen kodda belgelerinizin dizinini belirtmelisiniz. "BELGE DİZİNİNİZ" değerini, belge dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi oluşturma ve birleştirme alanlarını ekleme

Yeni bir belge oluşturup bir kullanarak başlıyoruz.`DocumentBuilder` birleştirme alanlarını eklemek için.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## 3. Adım: Birleştirme Alanlarını Yeniden Adlandırma

Belge aralığındaki her alan arasında döngü yaparız ve eğer bu bir birleştirme alanıysa, alanı "" ekleyerek yeniden adlandırırız._Yeniden adlandırıldı" son eki.

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

 Son olarak şunu diyoruz:`Save()` Değiştirilen belgeyi kaydetme yöntemi.

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

Aspose.Words for .NET'i kullanarak belgenizdeki birleştirme alanlarını yeniden adlandırmak için bu adımları izleyin.

### SSS'ler

#### S: Aspose.Words for .NET'i kullanarak bir Word belgesindeki birleştirilmiş alanları nasıl yeniden adlandırabilirim?

 C: Aspose.Words for .NET'i kullanarak bir Word belgesindeki birleştirilmiş alanları yeniden adlandırmak için, belgedeki alanlar arasında geçiş yapabilirsiniz.`FieldMergingArgs` sınıf ve kullanın`FieldMergingArgs.FieldName` alanları yeniden adlandırma yöntemi.

#### S: Aspose.Words for .NET ile bir Word belgesinde yalnızca belirli birleştirilmiş alanları yeniden adlandırmak mümkün mü?

C: Evet, Aspose.Words for .NET ile Word belgesindeki yalnızca belirli birleştirilmiş alanları yeniden adlandırmak mümkündür. Alan adı veya diğer ilgili özellikler gibi belirli kriterleri kullanarak hangi alanların yeniden adlandırılacağını filtreleyebilirsiniz. Daha sonra ilgili alanları aşağıdaki komutu kullanarak yeniden adlandırabilirsiniz:`FieldMergingArgs.FieldName` yöntem.

#### S: Birleştirilmiş bir alanın bir Word belgesinde Aspose.Words for .NET ile başarıyla yeniden adlandırılıp adlandırılmadığını nasıl kontrol edebilirim?

 C: Aspose.Words for .NET ile birleştirilmiş bir alanın Word belgesinde başarıyla yeniden adlandırılıp adlandırılmadığını kontrol etmek için şu komutu kullanabilirsiniz:`FieldMergedArgs` sınıfa erişin ve`FieldMergedArgs.IsMerged` Alanın hit ile yeniden adlandırılıp adlandırılmadığını belirleyen özellik.

#### S: Word belgesindeki birleştirilmiş bir alanı Aspose.Words for .NET ile yeniden adlandırmanın sonuçları nelerdir?

C: Bir Word belgesindeki birleştirilmiş bir alanı Aspose.Words for .NET ile yeniden adlandırdığınızda, belgedeki alanın adı değişir ve bu, alan adına bağlı diğer işlevleri veya süreçleri etkileyebilir. Birleştirilmiş alanları yeniden adlandırmadan önce bu olası sonuçları dikkate aldığınızdan emin olun.

#### S: Birleştirilmiş bir alanı Aspose.Words for .NET ile yeniden adlandırdıktan sonra orijinal adını geri yüklemek mümkün müdür?

C: Evet, birleştirilmiş bir alanı Aspose.Words for .NET ile yeniden adlandırdıktan sonra orijinal adını geri yüklemek mümkündür. Alanın orijinal adını bir değişkende veya listede saklayabilir ve daha sonra gerekirse bu bilgiyi orijinal adı geri yüklemek için kullanabilirsiniz.