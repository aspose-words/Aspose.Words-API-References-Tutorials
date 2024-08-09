---
title: Ölçü Birimi
linktitle: Ölçü Birimi
second_title: Aspose.Words Belge İşleme API'si
description: ODT dönüşümü sırasında belge formatını korumak için Aspose.Words for .NET'te ölçü birimi özelliğini nasıl yapılandıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-odtsaveoptions/measure-unit/
---
## giriiş

Hiç Word belgelerinizi farklı formatlara dönüştürmek zorunda kaldınız mı, ancak düzeniniz için belirli bir ölçü birimine ihtiyaç duydunuz mu? İster inç, ister santimetre veya noktalarla ilgileniyor olun, dönüştürme işlemi sırasında belgenizin bütünlüğünü korumasını sağlamak çok önemlidir. Bu eğitimde Aspose.Words for .NET'te ölçü birimi özelliğinin nasıl yapılandırılacağını anlatacağız. Bu güçlü özellik, ODT (Açık Belge Metni) biçimine dönüştürürken belgenizin biçimlendirmesinin tam olarak ihtiyaç duyduğunuz şekilde korunmasını sağlar.

## Önkoşullar

Koda dalmadan önce başlamanız gereken birkaç şey var:

1. Aspose.Words for .NET: Aspose.Words for .NET'in en son sürümünün kurulu olduğundan emin olun. Henüz sahip değilseniz, adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: C# kodunuzu yazmak ve yürütmek için Visual Studio benzeri bir IDE.
3. Temel C# Bilgisi: C#'ın temellerini anlamak, öğreticiyi takip etmenize yardımcı olacaktır.
4. Bir Word Belgesi: Dönüştürme için kullanabileceğiniz örnek bir Word belgesini hazır bulundurun.

## Ad Alanlarını İçe Aktar

Kodlamaya başlamadan önce gerekli ad alanlarının içe aktarıldığından emin olalım. Bunları kullanarak yönergeleri kod dosyanızın en üstüne ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1. Adım: Belge Dizininizi Kurun

Öncelikle belge dizininizin yolunu tanımlamanız gerekir. Burası Word belgenizin bulunduğu ve dönüştürülen dosyanın kaydedileceği yerdir.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` Dizininizin gerçek yolu ile. Bu, kodunuzun Word belgenizi nerede bulacağını bilmesini sağlar.

## Adım 2: Word Belgesini Yükleyin

 Daha sonra dönüştürmek istediğiniz Word belgesini yüklemeniz gerekir. Bu, kullanılarak yapılır.`Document` Aspose.Words'ten sınıf.

```csharp
// Word belgesini yükleyin
Document doc = new Document(dataDir + "Document.docx");
```

"Document.docx" adlı Word belgenizin belirtilen dizinde bulunduğundan emin olun.

## 3. Adım: Ölçü Birimini Yapılandırın

 Şimdi ODT dönüşümü için ölçü birimini yapılandıralım. Sihrin gerçekleştiği yer burasıdır. Biz kuracağız`OdtSaveOptions` ölçü birimi olarak inç kullanmak.

```csharp
// Yedekleme seçeneklerinin "Ölçü birimi" özelliği ile yapılandırılması
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

 Bu örnekte ölçü birimini inç olarak ayarlıyoruz. Ayrıca aşağıdaki gibi diğer birimleri de seçebilirsiniz.`OdtSaveMeasureUnit.Centimeters` veya`OdtSaveMeasureUnit.Points` gereksinimlerinize bağlı olarak.

## Adım 4: Belgeyi ODT'ye Dönüştürün

 Son olarak, yapılandırılmış olanı kullanarak Word belgesini ODT formatına dönüştüreceğiz.`OdtSaveOptions`.

```csharp
// Belgeyi ODT'ye dönüştürün
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Bu kod satırı, dönüştürülen belgeyi, uygulanan yeni ölçü birimiyle belirtilen dizine kaydeder.

## Çözüm

Ve işte karşınızda! Bu adımları izleyerek Aspose.Words for .NET'teki ölçü birimi özelliğini kolayca yapılandırarak belgenizin düzeninin dönüştürme sırasında korunmasını sağlayabilirsiniz. İster inç, ister santimetre veya noktalarla çalışıyor olun, bu eğitim size belgenizin biçimlendirmesini nasıl kolaylıkla kontrol altına alacağınızı göstermiştir.

## SSS

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, Word belgeleriyle programlı olarak çalışmak için güçlü bir kütüphanedir. Geliştiricilerin Microsoft Word gerektirmeden Word belgelerini oluşturmasına, değiştirmesine, dönüştürmesine ve işlemesine olanak tanır.

### İnç dışında başka ölçü birimleri kullanabilir miyim?
 Evet, Aspose.Words for .NET santimetre ve nokta gibi diğer ölçü birimlerini destekler. İstediğiniz birimi kullanarak belirtebilirsiniz.`OdtSaveMeasureUnit` numaralandırma.

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.Words for .NET'in ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).

### Aspose.Words for .NET belgelerini nerede bulabilirim?
 Aspose.Words for .NET'in kapsamlı belgelerine şu adresten ulaşabilirsiniz:[bu bağlantı](https://reference.aspose.com/words/net/).

### Aspose.Words for .NET için nasıl destek alabilirim?
 Destek için Aspose.Words forumunu ziyaret edebilirsiniz:[bu bağlantı](https://forum.aspose.com/c/words/8).
