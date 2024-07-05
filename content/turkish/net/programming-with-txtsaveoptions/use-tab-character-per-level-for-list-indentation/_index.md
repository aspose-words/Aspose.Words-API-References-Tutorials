---
title: Liste Girintisi İçin Düzey Başına Sekme Karakteri Kullan
linktitle: Liste Girintisi İçin Düzey Başına Sekme Karakteri Kullan
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te sekme karakterleri içeren girinti listeleri özelliğini nasıl kullanacağınızı öğrenin. Bu güçlü özellikle zamandan tasarruf edin ve iş akışınızı geliştirin.
type: docs
weight: 10
url: /tr/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

Bu eğitimde Aspose.Words for .NET ile "Liste girintisi için seviye başına bir sekme karakteri kullan" özelliği için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, her düzeydeki girintili listeler için sekme karakterlerini uygulamanıza olanak tanıyarak belgelerinizin görünümü üzerinde daha fazla esneklik ve kontrol sağlar.

## 1. Adım: Ortamı ayarlama

Başlamadan önce Aspose.Words for .NET ile geliştirme ortamınızı kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## Adım 2: Belgeyi ve oluşturucuyu oluşturma

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Bu adımda yeni bir tane oluşturuyoruz.`Document` nesne ve ilişkili`DocumentBuilder` nesne. Bu nesneler belgemizi değiştirmemize ve oluşturmamıza olanak tanıyacaktır.

## 3. Adım: Üç düzeyde girintiye sahip bir liste oluşturma

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

Bu adımda, liste numaralarının varsayılan formatını aşağıdaki komutu kullanarak uyguluyoruz:`ApplyNumberDefault()` liste biçimlendiricinin yöntemi. Daha sonra belge oluşturucuyu kullanarak listemize üç öğe ekliyoruz.`Writeln()` Ve`Write()` yöntemler. biz kullanıyoruz`ListIndent()` Her düzeyde girintiyi artırma yöntemi.

## 4. Adım: Kayıt seçeneklerini yapılandırın

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 Bu adımda belgeyi kaydetme seçeneklerini yapılandırıyoruz. Yeni bir tane yaratıyoruz`TxtSaveOptions` nesneyi ayarlayın ve`ListIndentation.Count` Girinti düzeyi başına sekme karakterlerinin sayısını belirtmek için özelliği 1 olarak ayarlayın. Biz de ayarladık`ListIndentation.Character` Sekme karakterlerini kullanmak istediğimizi belirtmek için özelliği '\t' olarak değiştirin.

## 5. Adım: Belgeyi kaydedin

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 Bu son adımda belgeyi belirtilen kaydetme seçenekleriyle kaydediyoruz. biz kullanıyoruz`Save()` çıktı dosyasının tam yolunu geçen belgenin yöntemi ve kaydetme seçenekleri.


Artık sekme karakterlerini kullanarak liste girintili bir belge oluşturmak için kaynak kodunu çalıştırabilirsiniz. Çıktı dosyası, "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET'teki liste girintisi için seviye başına bir sekme karakteri kullan özelliği için örnek kod kaynağı:

```csharp

// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Üç düzeyde girintiye sahip bir liste oluşturun
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

Artık sekme karakterlerini kullanarak liste girintili belgenizi oluşturmayı tamamladığınıza göre, makale içeriğinizi biçimlendirmek için Markdown'ı kullanabilirsiniz. Başlıkları, alt başlıkları ve dahil edilen kaynak kodunu vurgulamak için uygun biçimlendirme etiketlerini kullandığınızdan emin olun.

### Sıkça Sorulan Sorular

#### S: Aspose.Words for .NET'in "Liste girintisi için seviye başına bir sekme karakteri kullan" özelliği nedir?
Aspose.Words for .NET'in "Liste girintisi için seviye başına bir sekme karakteri kullan" özelliği, her seviyede liste girintisi için sekme karakterlerinin uygulanmasına olanak tanır. Bu, belgelerinizin görünümü üzerinde daha fazla esneklik ve kontrol sağlar.

#### S: Bu özelliği Aspose.Words for .NET ile nasıl kullanabilirim?
Bu özelliği Aspose.Words for .NET ile kullanmak için şu adımları takip edebilirsiniz:

Gerekli referansları ekleyerek ve uygun ad alanlarını içe aktararak geliştirme ortamınızı kurun.

 Yeni bir tane oluştur`Document` nesne ve ilişkili`DocumentBuilder` nesne.

 Kullan`DocumentBuilder` yöntemleri kullanarak birden fazla girinti düzeyine sahip bir liste oluşturmak için`ApplyNumberDefault()` varsayılan liste numarası biçimini uygulamak için,`Writeln()` Ve`Write()` Listeye öğe eklemek için ve`ListIndent()`Her düzeyde girintiyi artırmak için.

 Bir kayıt oluşturarak kaydetme seçeneklerini yapılandırın`TxtSaveOptions` nesne ve özelliklerin ayarlanması`ListIndentation.Count` seviye başına sekme karakterlerinin sayısına ve`ListIndentation.Character` ile`'\t'` Sekme karakterlerini kullanmak için

 kullanarak belgeyi kaydedin.`Save()` çıktı dosyasının tam yolunu ve kaydetme seçeneklerini belirten belge yöntemi.

#### S: Liste girintisi için düzey başına sekme karakterlerinin sayısını özelleştirmek mümkün mü?
 Evet, liste girintisi için düzey başına sekme karakterlerinin sayısını, değerini değiştirerek özelleştirebilirsiniz.`ListIndentation.Count` içindeki mülk`TxtSaveOptions` sınıf. Her girinti düzeyi için istediğiniz sekme karakterlerinin sayısını belirtebilirsiniz.

#### S: Aspose.Words for .NET'te liste girintisi için başka hangi karakterleri kullanabilirim?
 Aspose.Words for .NET ile sekme karakterlerinin yanı sıra liste girintisi için başka karakterler de kullanabilirsiniz. Ayarlayabilirsiniz`ListIndentation.Character` özelliği, boşluk ( gibi) istenen herhangi bir karaktere`' '`), listeleri girintilemek için.

#### S: Aspose.Words for .NET listeleri yönetmek için başka özellikler sunuyor mu?
Evet, Aspose.Words for .NET, Word belgelerindeki listeleri yönetmek için birçok özellik sunar. Numaralandırılmış veya madde işaretli listeler oluşturabilir, girinti düzeylerini ayarlayabilir, listelerin stilini özelleştirebilir, liste öğeleri ekleyebilir ve daha fazlasını yapabilirsiniz.