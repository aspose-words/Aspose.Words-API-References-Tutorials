---
title: Adres Mektup Birleştirme Alan Adlarını Alma
linktitle: Adres Mektup Birleştirme Alan Adlarını Alma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinizde adres-mektup birleştirme alan adlarını nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/get-mail-merge-field-names/
---

Aşağıda Aspose.Words for .NET'in "Birleştirme Alan Adlarını Al" özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstediğiniz sonuçları elde etmek için her adımı dikkatlice takip ettiğinizden emin olun.

## Adım 1: Belge Dizini Kurulumu

Verilen kodda belgelerinizin dizinini belirtmelisiniz. "BELGE DİZİNİNİZ" değerini, belge dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi yükleme

İlk adım, belgeyi birleştirme alanı adlarını almak istediğiniz yere yüklemektir.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

"BELGE DOSYALARINIZ" kısmını kendi dosyanızın adıyla değiştirdiğinizden emin olun.

## 3. Adım: Birleştirme alanı adlarını alın

 biz kullanıyoruz`GetFieldNames()` Belgede bulunan birleştirme alanlarının adlarını içeren bir dizi elde etme yöntemi.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

`fieldNames` değişken artık birleştirme alanlarının adlarını içeriyor.

### Aspose.Words for .NET ile Birleştirme Alan Adlarını Almak için Kaynak Kodu Örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Birleştirme alanı adlarını alın.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Birleştirme alanlarının sayısını görüntüleyin.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 Bu örnekte bir belge yükledik, birleştirme alanı adlarını aldık.`GetFieldNames()` yöntemi ve belgede bulunan birleştirme alanlarının sayısını görüntüledi.

Bu, Aspose.Words for .NET ile "Birleştirme Alan Adlarını Al" özelliğinin kullanımına ilişkin kılavuzumuzu tamamlıyor.

### SSS

#### S1: Aspose.Words'te adres-mektup birleştirme nedir?

Aspose.Words'de adres-mektup birleştirme, kişiselleştirilmiş belgeler oluşturmak için harici bir kaynaktan (örn. Excel elektronik tablosu veya veri tabanı) verileri şablon Word belgesiyle birleştirme işlemidir. Bu, mektupların, raporların ve diğer benzer belgelerin otomatik olarak oluşturulmasını kolaylaştırır.

#### S2: Bir Word belgesinde bulunan adres-mektup birleştirme alanlarının listesini nasıl edinebilirim?

Bir Word belgesinde bulunan adres-mektup birleştirme alanlarının listesini almak için şu adımları takip edebilirsiniz:

1. Document ve MailMergeFieldNames sınıflarını Aspose.Words ad alanından içe aktarın.
2. Word belgenizi yükleyerek bir Belge örneği oluşturun.
3. Kullanılabilir adres-mektup birleştirme alanlarının listesini almak için Document nesnesinin GetMailMergeFieldNames yöntemini kullanın.

İşlemi açıklamak için örnek bir kod aşağıda verilmiştir:

```csharp
// Gerekli ad alanlarını içe aktarın
using Aspose.Words;
using Aspose.Words.MailMerging;

// Mevcut belgeyi yükleyin
Document document = new Document("FilePath");

// Adres-mektup birleştirme alanlarının listesini alın
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Kullanılabilir adres-mektup birleştirme alanları arasında geçiş yapın
foreach (string fieldName in fieldNames)
{
     // Alan adıyla bir şeyler yapın
     Console.WriteLine(fieldName);
}
```
### SSS'ler

#### S: Aspose.Words'te adres-mektup birleştirme nedir?

C: Aspose.Words'te adres-mektup birleştirme, kişiselleştirilmiş belgeler oluşturmak için harici bir kaynaktan (örn. Excel elektronik tablosu veya veri tabanı) verileri şablon Word belgesiyle birleştirme işlemidir. Bu, mektupların, raporların ve diğer benzer belgelerin otomatik olarak oluşturulmasını kolaylaştırır.

#### S: Bir Word belgesinde bulunan adres-mektup birleştirme alanlarının listesini nasıl edinebilirim?

C: Bir Word belgesinde bulunan adres-mektup birleştirme alanlarının listesini almak için şu adımları takip edebilirsiniz:

1. Document ve MailMergeFieldNames sınıflarını Aspose.Words ad alanından içe aktarın.
2. Word belgenizi yükleyerek bir Belge örneği oluşturun.
3. Kullanılabilir adres-mektup birleştirme alanlarının listesini almak için Document nesnesinin GetMailMergeFieldNames yöntemini kullanın.

#### S: Adres-mektup birleştirme alanlarını Excel elektronik tablosu gibi harici bir veri kaynağından alabilir miyim?

C: Evet, adres-mektup birleştirme alanlarını Excel elektronik tablosu gibi harici bir veri kaynağından alabilirsiniz. Bunun için Aspose.Words'ün veri bağlama özelliklerini kullanarak veri kaynağıyla bağlantı kurabilir ve mevcut alanların adlarını alabilirsiniz.

#### S: Adres-mektup birleştirme alanlarını belirli ölçütlere göre filtrelemek mümkün mü?

C: Evet, adres-mektup birleştirme alanlarını belirli ölçütlere göre filtrelemek mümkündür. Adres-mektup birleştirme alanlarını filtrelemek ve yalnızca belirli ölçütlerinize uyanları almak için normal ifadeleri veya belirli koşulları kullanabilirsiniz.

#### S: Aspose.Words'te adres-mektup birleştirme alanlarını nasıl değiştirebilirim?

C: Aspose.Words'teki adres-mektup birleştirme alanlarını değiştirmek için Document ve MailMergeField nesnelerinin sağladığı yöntem ve özellikleri kullanabilirsiniz. Adres-mektup birleştirme alanlarını ekleyebilir, kaldırabilir veya güncelleyebilir, ayrıca alanlarla ilişkili değerleri alabilir ve düzenleyebilirsiniz.