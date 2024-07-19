---
title: Pencereye Otomatik Sığdır
linktitle: Pencereye Otomatik Sığdır
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET'i kullanarak tabloları Word belgelerindeki pencereye kolayca otomatik olarak sığdırın. Daha temiz, profesyonel belgeler için mükemmeldir.
type: docs
weight: 10
url: /tr/net/programming-with-tables/auto-fit-to-page-width/
---
## giriiş

Hiç Word belgelerindeki tabloların sayfaya tam olarak sığmamasından kaynaklanan hayal kırıklığını hissettiniz mi? Kenar boşluklarını değiştiriyorsunuz, sütunları yeniden boyutlandırıyorsunuz ve yine de garip görünüyor. Aspose.Words for .NET kullanıyorsanız bu soruna şık bir çözüm var: tabloları pencereye otomatik olarak sığdırmak. Bu şık özellik, tablo genişliğini sayfa genişliğiyle mükemmel şekilde hizalanacak şekilde ayarlayarak belgenizin gösterişli ve profesyonel görünmesini sağlar. Bu kılavuzda, Aspose.Words for .NET ile bunu başarmak için gereken adımları size anlatacağız ve masalarınızın her zaman tam olarak oturmasını sağlayacağız.

## Önkoşullar

Koda dalmadan önce her şeyin yerli yerinde olduğundan emin olalım:

1. Visual Studio: .NET kodunuzu yazmak ve çalıştırmak için Visual Studio gibi bir IDE'ye ihtiyacınız olacak.
2.  Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/words/net/).
3. Temel C# Bilgisi: C# programlama diline aşinalık, kod parçacıklarını daha kolay anlamanıza yardımcı olacaktır.

Bu önkoşulları sıraladıktan sonra heyecan verici kısım olan kodlamaya geçelim!

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET ile çalışmaya başlamak için gerekli ad alanlarını içe aktarmanız gerekir. Bu, programınıza kullanacağınız sınıfları ve yöntemleri nerede bulacağını söyler.

Aspose.Words ad alanını şu şekilde içe aktarabilirsiniz:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

`Aspose.Words` ad alanı, Word belgelerini işlemek için temel sınıfları içerirken,`Aspose.Words.Tables` özellikle masaları işlemek içindir.

## 1. Adım: Belgenizi Ayarlayın

 Öncelikle otomatik sığdırmak istediğiniz tabloyu içeren Word belgesini yüklemeniz gerekir. Bunun için şunları kullanacaksınız:`Document` Aspose.Words tarafından sağlanan sınıf.

```csharp
// Belgeler dizininizin yolunu tanımlayın
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi belirtilen yoldan yükleyin
Document doc = new Document(dataDir + "Tables.docx");
```

 Bu adımda belgenizin saklanacağı yolu tanımlayacak ve onu bir`Document` nesne. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgenizin bulunduğu gerçek yolla.

## Adım 2: Tabloya Erişin

Belgenizi yükledikten sonraki adım, değiştirmek istediğiniz tabloya erişmek olacaktır. Belgedeki ilk tabloyu şu şekilde alabilirsiniz:

```csharp
// Belgeden ilk tabloyu alın
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Bu kod parçacığı, belgede bulunan ilk tabloyu getirir. Belgenizde birden fazla tablo varsa ve belirli bir tabloya ihtiyacınız varsa dizini buna göre ayarlamanız gerekebilir.

## Adım 3: Tabloyu Otomatik Sığdır

Artık tablonuz olduğuna göre otomatik sığdırma işlevini uygulayabilirsiniz. Bu, tabloyu otomatik olarak sayfanın genişliğine uyacak şekilde ayarlayacaktır:

```csharp
// Tabloyu pencere genişliğine otomatik olarak sığdır
table.AutoFit(AutoFitBehavior.AutoFitToWindow);
```

`AutoFit` ile yöntem`AutoFitBehavior.AutoFitToWindow` tablo genişliğinin sayfanın tüm genişliğine sığacak şekilde ayarlanmasını sağlar.

## Adım 4: Değiştirilen Belgeyi Kaydedin

Tablo otomatik olarak yerleştirildiğinde son adım, değişiklikleri yeni bir belgeye kaydetmektir:

```csharp
// Değiştirilen belgeyi yeni bir dosyaya kaydedin
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToWindow.docx");
```

Bu, değiştirilen belgenizi otomatik olarak takılan tabloyla birlikte yeni bir dosyaya kaydedecektir. Artık bu belgeyi Word'de açabilirsiniz; tablo, sayfa genişliğine mükemmel şekilde sığacaktır.

## Çözüm

Ve işte, Aspose.Words for .NET ile tabloları pencereye otomatik olarak sığdırmak çocuk oyuncağı! Bu basit adımları izleyerek tablolarınızın her zaman profesyonel görünmesini ve belgelerinizle mükemmel uyum sağlamasını sağlarsınız. İster kapsamlı tablolarla uğraşıyor olun, ister yalnızca belgenizi düzenlemek istiyor olun, bu özellik oyunun kurallarını değiştirecek. Bir deneyin ve belgelerinizin düzgün, iyi hizalanmış tablolarla parlamasına izin verin!

## SSS'ler

### Bir belgeye birden çok tabloyu otomatik olarak sığdırabilir miyim?  
Evet, bir belgedeki tüm tablolar arasında geçiş yapabilir ve her birine otomatik sığdırma yöntemini uygulayabilirsiniz.

### Otomatik sığdırma tablonun içeriğini etkiler mi?  
Hayır, otomatik sığdırma tablonun genişliğini ayarlar ancak hücrelerin içindeki içeriği değiştirmez.

### Tablomda tutmak istediğim belirli sütun genişlikleri varsa ne olur?  
Otomatik sığdırma belirli sütun genişliklerini geçersiz kılacaktır. Belirli genişlikleri korumanız gerekiyorsa otomatik sığdırmayı uygulamadan önce sütunları manuel olarak ayarlamanız gerekebilir.

### Diğer belge formatlarındaki tablolar için otomatik sığdırmayı kullanabilir miyim?  
Aspose.Words öncelikle Word belgelerini (.docx) destekler. Diğer formatları önce .docx'e dönüştürmeniz gerekebilir.

### Aspose.Words'ün deneme sürümünü nasıl edinebilirim?  
 Ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/).