---
title: Paragraftaki Alanları Dönüştür
linktitle: Paragraftaki Alanları Dönüştür
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile IF alanlarını bir paragraftaki düz metne dönüştürün.
type: docs
weight: 10
url: /tr/net/working-with-fields/convert-fields-in-paragraph/
---

İşte, Aspose.Words for .NET ile Alanları Paragrafa Dönüştür özelliğinin nasıl kullanılacağını gösteren bir öğretici. Bu kod, bir belgenin son paragrafında karşılaşılan tüm IF tipi alanları düz metne dönüştürür. Bu kodu anlamak ve çalıştırmak için aşağıdaki adımları izleyin.

Başlamadan önce Aspose.Words for .NET'i kurduğunuzdan ve geliştirme ortamınızı kurduğunuzdan emin olun.

## 1. Adım: Referansları içe aktarın

Aspose.Words'ü projenizde kullanmak için gerekli referansları eklemeniz gerekiyor. Projenizde Aspose.Words kitaplığına bir referans eklediğinizden emin olun.

## 2. Adım: Belgeyi yükleme

Alanları dönüştürmeden önce dönüştürülecek alanları içeren belgeyi yüklemeniz gerekir. Belgeyi içeren dizine doğru yolu belirttiğinizden emin olun. Belgeyi şu şekilde yükleyebilirsiniz:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin.
Document doc = new Document(dataDir + "Linked fields.docx");
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirin.

## 3. Adım: Alanları metne dönüştürme

Artık belge yüklendiğine göre, yazı alanlarını düz metne dönüştürmeye devam edebiliriz. Bu örnekte, yalnızca belgenin son paragrafında bulunan alanları hedefliyoruz. İşte bu dönüşümü gerçekleştiren kod:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Bu kod, belgenin son paragrafındaki alanları filtrelemek için LINQ yöntemlerinin bir kombinasyonunu kullanır ve ardından bunları çağırarak düz metne dönüştürür.`Unlink()` yöntem.

## 4. Adım: Değiştirilen belgeyi kaydetme

 Alanlar dönüştürüldükten sonra değiştirilen belgeyi kaydedebilirsiniz. Kullan`Save()` Bunun için yöntem. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Yedekleme için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Paragraftaki Alanları Dönüştürmek için kaynak kodu örneği

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin.
Document doc = new Document(dataDir + "Linked fields.docx");

// Belgenin son paragrafındaki IF alanlarını düz metne dönüştürün.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Değiştirilen belgeyi kaydedin.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```
