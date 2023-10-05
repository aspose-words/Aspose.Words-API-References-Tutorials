---
title: Dönüştürülen Öğeleri Rasterleştir
linktitle: Dönüştürülen Öğeleri Rasterleştir
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile PCL formatına dönüştürürken dönüştürülen öğelerin rasterleştirilmesini nasıl devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET, bir C# uygulamasında Word belgelerini oluşturmak, değiştirmek ve dönüştürmek için kullanılan güçlü bir kütüphanedir. Aspose.Words'ün sunduğu özellikler arasında, belgeleri farklı formatlara dönüştürürken dönüştürülen öğeleri rasterleştirme yeteneği de vardır. Bu kılavuzda, bir belgeyi PCL formatına dönüştürürken dönüştürülen öğelerin rasterleştirilmesini devre dışı bırakmak için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgeleriyle Kelime İşlemeyi kolay ve verimli hale getiren popüler bir kütüphanedir. Dönüştürme sırasında dönüştürülen öğelerin rasterleştirilmesi desteği de dahil olmak üzere, Word belgelerinin oluşturulması, düzenlenmesi ve dönüştürülmesi için çok çeşitli özellikler sunar.

## Word belgesini yükleme

İlk adım, PCL formatına dönüştürmek istediğiniz Word belgesini yüklemektir. Belgeyi kaynak dosyadan yüklemek için Document sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Bu örnekte, belgeler dizininde bulunan "Rendering.docx" belgesini yüklüyoruz.

## Yedekleme seçeneklerini yapılandırma

Bir sonraki adım, PCL formatına dönüştürmek için kaydetme seçeneklerini yapılandırmaktır. PclSaveOptions sınıfını kullanın ve RasterizeTransformedElements özelliğini false olarak ayarlayın. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Yeni bir PclSaveOptions nesnesi oluşturuyoruz ve belgeyi PCL formatında kaydetmek istediğimizi belirtmek için SaveFormat özelliğini SaveFormat.Pcl olarak ayarlıyoruz. Daha sonra, dönüştürülen öğelerin rasterleştirilmesini devre dışı bırakmak için RasterizeTransformedElements özelliğini false olarak ayarlıyoruz.

## Belgeyi PCL formatına dönüştürme

Artık kaydetme seçeneklerini yapılandırdığımıza göre belgeyi PCL formatına dönüştürmeye devam edebiliriz. Kaydetme seçeneklerini belirterek dönüştürülen belgeyi PCL biçiminde kaydetmek için Document sınıfının Kaydet yöntemini kullanın. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

Bu örnekte, dönüştürülen belgeyi belirtilen kaydetme seçeneklerini kullanarak "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" olarak kaydediyoruz.

### Aspose.Words for .NET ile "Dönüştürülmüş Elemanları Rasterleştir" özelliği için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word belgesini yükleyin


Document doc = new Document(dataDir + "Rendering.docx");

// PCL formatına dönüştürme için yedekleme seçeneklerini yapılandırma
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Belgeyi PCL formatına dönüştürün
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Çözüm

Bu kılavuzda, sağlanan C# kaynak kodunu kullanarak bir belgeyi PCL formatına dönüştürürken dönüştürülen öğelerin rasterleştirilmesini devre dışı bırakmak için Aspose.Words for .NET'in nasıl kullanılacağını ele aldık. Verilen adımları takip ederek, Word belgelerinizi farklı formatlara dönüştürürken dönüştürülen öğelerin rasterleştirme davranışını kolayca kontrol edebilirsiniz. Aspose.Words, dönüştürülmüş öğelerle çalışmak için muazzam bir esneklik ve güç sunarak, tam olarak özel ihtiyaçlarınıza göre dönüştürülmüş belgeler oluşturmanıza olanak tanır.