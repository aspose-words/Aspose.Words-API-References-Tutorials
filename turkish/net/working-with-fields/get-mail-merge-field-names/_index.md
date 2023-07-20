---
title: Adres Mektup Birleştirme Alan Adlarını Alın
linktitle: Adres Mektup Birleştirme Alan Adlarını Alın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile Word belgelerinizde adres mektup birleştirme alan adlarını nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/get-mail-merge-field-names/
---

Aspose.Words for .NET'in "Get Merge Field Names" özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleme

İlk adım, belgeyi birleştirme alan adlarını almak istediğiniz yere yüklemektir.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

"BELGE DOSYASINIZ"ı kendi dosyanızın adıyla değiştirdiğinizden emin olun.

## 3. Adım: Birleştirme alan adlarını alın

 biz kullanıyoruz`GetFieldNames()` belgede bulunan birleştirme alanlarının adlarını içeren bir dizi elde etme yöntemi.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 bu`fieldNames` değişken artık birleştirme alanlarının adlarını içerir.

### Aspose.Words for .NET ile Alan Adlarını Birleştirme İçin Kaynak Kodu Örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Birleştirme alan adlarını alın.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Birleştirme alanlarının sayısını görüntüleyin.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 Bu örnekte, bir belge yükledik, birleştirme alan adlarını`GetFieldNames()` yöntemi ve belgede bulunan birleştirme alanlarının sayısını görüntüler.

Bu, Aspose.Words for .NET ile "Get Merge Field Names" özelliğinin kullanımına ilişkin kılavuzumuzun sonuna geliyor.

### SSS

#### S1: Aspose.Words'te adres mektup birleştirme nedir?

Aspose.Words'te adres mektup birleştirme, kişiselleştirilmiş belgeler oluşturmak için harici bir kaynaktan (örn. Excel elektronik tablosu veya veritabanı) verileri bir şablon Word belgesiyle birleştirme işlemidir. Bu, mektupların, raporların ve diğer benzer belgelerin otomatik olarak oluşturulmasını kolaylaştırır.

#### S2: Bir Word belgesinde bulunan adres-mektup birleştirme alanlarının listesini nasıl alabilirim?

Bir Word belgesinde bulunan adres-mektup birleştirme alanlarının listesini almak için şu adımları izleyebilirsiniz:

1. Aspose.Words ad alanından Document ve MailMergeFieldNames sınıflarını içe aktarın.
2. Word belgenizi yükleyerek bir Belge örneği oluşturun.
3. Kullanılabilir adres mektup birleştirme alanlarının listesini almak için Document nesnesinin GetMailMergeFieldNames yöntemini kullanın.

İşlemi göstermek için örnek bir kod aşağıda verilmiştir:

```csharp
// Gerekli ad alanlarını içe aktarın
using Aspose.Words;
using Aspose.Words.MailMerging;

// Mevcut belgeyi yükle
Document document = new Document("FilePath");

// Adres mektup birleştirme alanlarının listesini alın
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Kullanılabilir adres mektup birleştirme alanları arasında geçiş yapın
foreach (string fieldName in fieldNames)
{
     // Alan adıyla bir şeyler yapın
     Console.WriteLine(fieldName);
}
```
### SSS

#### S: Aspose.Words'ta adres mektup birleştirme nedir?

C: Aspose.Words'ta adres mektup birleştirme, kişiselleştirilmiş belgeler oluşturmak için harici bir kaynaktan (örn. Excel elektronik tablosu veya veritabanı) verileri bir şablon Word belgesiyle birleştirme işlemidir. Bu, mektupların, raporların ve diğer benzer belgelerin otomatik olarak oluşturulmasını kolaylaştırır.

#### S: Bir Word belgesinde bulunan adres-mektup birleştirme alanlarının listesini nasıl alabilirim?

C: Bir Word belgesinde bulunan adres-mektup birleştirme alanlarının listesini almak için şu adımları izleyebilirsiniz:

1. Aspose.Words ad alanından Document ve MailMergeFieldNames sınıflarını içe aktarın.
2. Word belgenizi yükleyerek bir Belge örneği oluşturun.
3. Kullanılabilir adres mektup birleştirme alanlarının listesini almak için Document nesnesinin GetMailMergeFieldNames yöntemini kullanın.

#### S: Adres mektup birleştirme alanlarını Excel elektronik tablosu gibi harici bir veri kaynağından alabilir miyim?

C: Evet, adres mektup birleştirme alanlarını Excel elektronik tablosu gibi harici bir veri kaynağından alabilirsiniz. Bunun için Aspose.Words'ün veri bağlama özelliklerini kullanarak veri kaynağı ile bağlantı kurabilir ve mevcut alanların isimlerini alabilirsiniz.

#### S: Adres mektup birleştirme alanlarını belirli kriterlere göre filtrelemek mümkün mü?

C: Evet, adres-mektup birleştirme alanlarını belirli kriterlere göre filtrelemek mümkündür. Adres mektup birleştirme alanlarını filtrelemek ve yalnızca belirli ölçütlerinizi karşılayanları almak için normal ifadeleri veya belirli koşulları kullanabilirsiniz.

#### S: Aspose.Words'te adres-mektup birleştirme alanlarını nasıl değiştirebilirim?

C: Aspose.Words'deki adres-mektup birleştirme alanlarını değiştirmek için Document ve MailMergeField nesneleri tarafından sağlanan yöntemleri ve özellikleri kullanabilirsiniz. Adres mektup birleştirme alanlarını ekleyebilir, kaldırabilir veya güncelleyebilirsiniz, ayrıca alanlarla ilişkili değerleri alabilir ve düzenleyebilirsiniz.