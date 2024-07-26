---
title: Paragraftaki Alanları Dönüştür
linktitle: Paragraftaki Alanları Dönüştür
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile IF alanlarını paragraftaki düz metne dönüştürün.
type: docs
weight: 10
url: /tr/net/working-with-fields/convert-fields-in-paragraph/
---

Burada Aspose.Words for .NET ile Alanları Paragrafa Dönüştür özelliğinin nasıl kullanılacağını gösteren bir eğitim bulunmaktadır. Bu kod, bir belgenin son paragrafında karşılaşılan tüm IF türü alanları düz metne dönüştürür. Bu kodu anlamak ve çalıştırmak için aşağıdaki adımları izleyin.

Başlamadan önce Aspose.Words for .NET'i yüklediğinizden ve geliştirme ortamınızı kurduğunuzdan emin olun.

## 1. Adım: Referansları içe aktarın

Aspose.Words'ü projenizde kullanmak için gerekli referansları eklemeniz gerekir. Projenize Aspose.Words kütüphanesine bir referans eklediğinizden emin olun.

## Adım 2: Belgeyi yükleme

Alanları dönüştürebilmeniz için önce dönüştürülecek alanları içeren belgeyi yüklemeniz gerekir. Belgeyi içeren dizinin doğru yolunu belirttiğinizden emin olun. Belgeyi şu şekilde yükleyebilirsiniz:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin.
Document doc = new Document(dataDir + "Linked fields.docx");
```

"BELGELERİNİZ DİZİNİ"ni belgeler dizininizin gerçek yolu ile değiştirin.

## 3. Adım: Alanları metne dönüştürme

Artık belge yüklendiğine göre, yazım alanlarını düz metne dönüştürmeye devam edebiliriz. Bu örnekte yalnızca belgenin son paragrafında bulunan alanları hedefliyoruz. İşte bu dönüşümü gerçekleştiren kod:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Bu kod, belgenin son paragrafındaki alanları filtrelemek için LINQ yöntemlerinin bir birleşimini kullanır ve ardından bunları çağırarak bunları düz metne dönüştürür.`Unlink()` yöntem.

## Adım 4: Değiştirilen belgeyi kaydetme

 Alanlar dönüştürüldükten sonra değiştirilen belgeyi kaydedebilirsiniz. Kullan`Save()` bunun için yöntem. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Yedekleme için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Paragraftaki Alanları Dönüştürme için kaynak kodu örneği

```csharp
// Belgeler dizininin yolu.
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

### SSS'ler

#### S: Aspose.Words'te dönüşüm alanı nedir?

C: Aspose.Words'teki dönüştürme alanı, bir değeri veya ifadeyi başka bir formata veya veri türüne dönüştüren bir alan türüdür. Örneğin, bir tarihi belirli bir biçime, bir sayıyı metne dönüştürmek veya başka türde dönüştürmeler gerçekleştirmek için bir dönüştürme alanı kullanabilirsiniz.

#### S: Aspose.Words ile paragrafa dönüşüm alanı nasıl eklenir?

C: Aspose.Words ile bir paragrafa dönüşüm alanı eklemek için şu adımları takip edebilirsiniz:

1. Aspose.Words ad alanından Document sınıfını içe aktarın.
2. Mevcut belgenizi yükleyerek bir Belge örneği oluşturun.
3. Dönüşüm alanını eklemek istediğiniz paragrafı alın.
4. Dönüştürme alanını doğru sözdizimi ile eklemek için InsertField yöntemini kullanın.

#### S: Aspose.Words hangi dönüştürme formatlarını destekliyor?

C: Aspose.Words, tarih formatları, sayı formatları, metin formatları, para birimi formatları, yüzde formatları ve daha fazlasını içeren alanlarda çok çeşitli dönüştürme formatlarını destekler. Mevcut dönüştürme formatlarının tam listesi için Aspose.Words belgelerine göz atabilirsiniz.

#### S: Aspose.Words ile bir Word belgesindeki dönüşüm alanı nasıl güncellenir?

C: Bir Word belgesindeki dönüştürme alanını Aspose.Words ile güncellemek için UpdateFields yöntemini kullanabilirsiniz. Bu yöntem, belgede döngü yapar ve dönüştürme alanları da dahil olmak üzere tüm alanları güncelleyerek değerleri geçerli verilere göre yeniden hesaplar.