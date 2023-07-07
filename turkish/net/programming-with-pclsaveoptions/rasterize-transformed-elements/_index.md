---
title: Dönüştürülen Öğeleri Rasterleştir
linktitle: Dönüştürülen Öğeleri Rasterleştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile PCL formatına dönüştürürken dönüştürülmüş öğelerin rasterleştirmesini nasıl devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmak, işlemek ve dönüştürmek için güçlü bir kitaplıktır. Aspose.Words'ün sunduğu özellikler arasında, belgeleri farklı biçimlere dönüştürürken dönüştürülen öğeleri rasterleştirme yeteneği bulunur. Bu kılavuzda, bir belgeyi PCL formatına dönüştürürken dönüştürülmüş öğelerin rasterleştirmesini devre dışı bırakmak için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, Word belgeleriyle çalışmayı kolay ve verimli hale getiren popüler bir kitaplıktır. Dönüştürme sırasında dönüştürülen öğeleri rasterleştirme desteği de dahil olmak üzere, Word belgeleri oluşturmak, düzenlemek ve dönüştürmek için çok çeşitli özellikler sunar.

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

Yeni bir PclSaveOptions nesnesi oluşturuyoruz ve belgeyi PCL formatında kaydetmek istediğimizi belirtmek için SaveFormat özelliğini SaveFormat.Pcl olarak ayarlıyoruz. Ardından, dönüştürülen öğelerin rasterleştirilmesini devre dışı bırakmak için RasterizeTransformedElements özelliğini false olarak ayarladık.

## Belgeyi PCL biçimine dönüştürme

Artık kaydetme seçeneklerini yapılandırdığımıza göre, belgeyi PCL formatına dönüştürmeye devam edebiliriz. Kaydetme seçeneklerini belirterek dönüştürülen belgeyi PCL formatında kaydetmek için Document sınıfının Save yöntemini kullanın. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

Bu örnekte, dönüştürülen belgeyi belirtilen kaydetme seçeneklerini kullanarak "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" olarak kaydediyoruz.

### Aspose.Words for .NET ile "Dönüştürülmüş Öğeleri Rasterleştir" özelliği için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word belgesini yükleyin


Document doc = new Document(dataDir + "Rendering.docx");

// PCL biçimine dönüştürme için yedekleme seçeneklerini yapılandırın
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Belgeyi PCL formatına dönüştürün
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Çözüm

Bu kılavuzda, sağlanan C# kaynak kodunu kullanarak bir belgeyi PCL formatına dönüştürürken dönüştürülmüş öğelerin rasterleştirmesini devre dışı bırakmak için Aspose.Words for .NET'in nasıl kullanılacağını ele aldık. Sağlanan adımları izleyerek, Word belgelerinizi farklı biçimlere dönüştürürken dönüştürülen öğelerin rasterleştirme davranışını kolayca kontrol edebilirsiniz. Aspose.Words, dönüştürülmüş öğelerle çalışmak için muazzam bir esneklik ve güç sunarak, tam olarak özel ihtiyaçlarınıza göre dönüştürülmüş belgeler oluşturmanıza olanak tanır.