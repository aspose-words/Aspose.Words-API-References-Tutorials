---
title: Liste Girintisi İçin Düzey Başına Sekme Karakteri Kullan
linktitle: Liste Girintisi İçin Düzey Başına Sekme Karakteri Kullan
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te sekme karakterleriyle girinti listelerini nasıl kullanacağınızı öğrenin. Bu güçlü özellikle zaman kazanın ve iş akışınızı iyileştirin.
type: docs
weight: 10
url: /tr/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

Bu eğitimde, Aspose.Words for .NET ile "Liste girintisi için seviye başına bir sekme karakteri kullan" özelliği için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, her düzeyde girintili listeler için sekme karakterleri uygulamanıza izin vererek belgelerinizin görünümü üzerinde daha fazla esneklik ve kontrol sağlar.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## 2. Adım: Belgeyi ve oluşturucuyu oluşturma

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Bu adımda yeni bir tane oluşturuyoruz.`Document` nesne ve ilişkili`DocumentBuilder` nesne. Bu nesneler, belgemizi manipüle etmemize ve oluşturmamıza izin verecektir.

## 3. Adım: Üç girinti düzeyine sahip bir liste oluşturma

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

 Bu adımda, liste numaralarının varsayılan biçimini kullanarak uygularız.`ApplyNumberDefault()` liste biçimlendirici yöntemi. Ardından, belge oluşturucuyu kullanarak listemize üç öğe ekliyoruz.`Writeln()` Ve`Write()` yöntemler. biz kullanıyoruz`ListIndent()` girintiyi her düzeyde artırma yöntemi.

## 4. Adım: Kayıt seçeneklerini yapılandırın

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 Bu adımda, belgeyi kaydetme seçeneklerini yapılandırıyoruz. yeni bir tane yaratıyoruz`TxtSaveOptions` nesne ve ayarlayın`ListIndentation.Count`girinti düzeyi başına sekme karakteri sayısını belirtmek için özelliği 1 olarak değiştirin. biz de ayarlıyoruz`ListIndentation.Character` sekme karakterlerini kullanmak istediğimizi belirtmek için özelliği '\t' olarak değiştirin.

## 5. Adım: Belgeyi kaydedin

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 Bu son adımda, belirtilen kaydetme seçenekleriyle belgeyi kaydediyoruz. biz kullanıyoruz`Save()` çıktı dosyasının tam yolunu geçiren belgenin yöntemi ve kaydetme seçenekleri.


Artık sekme karakterlerini kullanarak liste girintili bir belge oluşturmak için kaynak kodunu çalıştırabilirsiniz. Çıktı dosyası "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET ile Liste girintisi için seviye başına bir sekme karakteri kullan özelliği için örnek kod kaynağı:

```csharp

// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Üç girinti düzeyi içeren bir liste oluşturun
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

Sekme karakterlerini kullanarak liste girintili belgenizi oluşturmayı bitirdiğinize göre, makale içeriğinizi biçimlendirmek için Markdown'ı kullanabilirsiniz. Başlıkları, altyazıları ve dahil edilen kaynak kodunu vurgulamak için uygun biçimlendirme etiketlerini kullandığınızdan emin olun.