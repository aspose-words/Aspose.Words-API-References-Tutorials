---
title: Paragraftaki Alanları Dönüştür
linktitle: Paragraftaki Alanları Dönüştür
second_title: Aspose.Words Belge İşleme API'sı
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

### SSS

#### S: Aspose.Words'te dönüştürme alanı nedir?

C: Aspose.Words'teki bir dönüştürme alanı, bir değeri veya ifadeyi başka bir biçime veya veri türüne dönüştüren bir alan türüdür. Örneğin, bir tarihi belirli bir biçime, bir sayıyı metne dönüştürmek veya diğer dönüştürme türlerini gerçekleştirmek için bir dönüştürme alanı kullanabilirsiniz.

#### S: Aspose.Words ile bir paragrafa dönüştürme alanı nasıl eklenir?

C: Aspose.Words ile bir paragrafa dönüştürme alanı eklemek için şu adımları izleyebilirsiniz:

1. Aspose.Words ad alanından Document sınıfını içe aktarın.
2. Mevcut belgenizi yükleyerek bir Belge örneği oluşturun.
3. Dönüştürme alanını eklemek istediğiniz paragrafı alın.
4. Dönüştürme alanını doğru sözdizimiyle eklemek için InsertField yöntemini kullanın.

#### S: Aspose.Words hangi dönüştürme formatlarını destekliyor?

C: Aspose.Words, tarih formatları, sayı formatları, metin formatları, para birimi formatları, yüzde formatları ve daha fazlası dahil olmak üzere alanlarda çok çeşitli dönüştürme formatlarını destekler. Kullanılabilir dönüştürme biçimlerinin tam listesi için Aspose.Words belgelerine bakabilirsiniz.

#### S: Bir Word belgesindeki dönüştürme alanı Aspose.Words ile nasıl güncellenir?

C: Bir Word belgesindeki dönüştürme alanını Aspose.Words ile güncellemek için UpdateFields yöntemini kullanabilirsiniz. Bu yöntem belgede döngü halinde dolaşır ve dönüştürme alanları da dahil olmak üzere tüm alanları güncel verilere göre değerleri yeniden hesaplayarak günceller.