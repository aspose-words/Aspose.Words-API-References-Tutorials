---
title: Sonraki Sayfalarda Satırları Tekrarla
linktitle: Sonraki Sayfalarda Satırları Tekrarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak yinelenen tablo başlığı satırlarına sahip Word belgelerinin nasıl oluşturulacağını öğrenin. Profesyonel ve gösterişli belgeler elde etmek için bu kılavuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---
## giriiş

Program aracılığıyla bir Word belgesi oluşturmak, özellikle birden fazla sayfada biçimlendirmeyi korumanız gerektiğinde göz korkutucu bir görev olabilir. Hiç Word'de bir tablo oluşturmayı denediğinizde başlık satırlarınızın sonraki sayfalarda tekrarlanmadığını fark ettiğiniz oldu mu? Korkma! Aspose.Words for .NET ile tablo başlıklarınızın her sayfada tekrarlanmasını kolayca sağlayarak belgelerinize profesyonel ve şık bir görünüm kazandırabilirsiniz. Bu eğitimde, basit kod örnekleri ve ayrıntılı açıklamalar kullanarak bunu başarmanıza yönelik adımlarda size yol göstereceğiz. Hadi dalalım!

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET: İndirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
2. .NET Framework makinenizde yüklü.
3. Visual Studio veya .NET geliştirmeyi destekleyen başka bir IDE.
4. C# programlamanın temel anlayışı.

Devam etmeden önce Aspose.Words for .NET'i yüklediğinizden ve geliştirme ortamınızı kurduğunuzdan emin olun.

## Ad Alanlarını İçe Aktar

Başlamak için projenize gerekli ad alanlarını içe aktarmanız gerekir. C# dosyanızın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Bu ad alanları, Word belgelerini ve tablolarını yönetmek için gereken sınıfları ve yöntemleri içerir.

## 1. Adım: Belgeyi Başlatın

 Öncelikle yeni bir Word belgesi oluşturalım ve`DocumentBuilder` masamızı oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Bu kod yeni bir belgeyi başlatır ve`DocumentBuilder` belge yapısının oluşturulmasına yardımcı olan nesne.

## Adım 2: Tabloyu Başlatın ve Başlık Satırlarını Tanımlayın

Daha sonra tabloyu başlatacağız ve sonraki sayfalarda tekrarlamak istediğimiz başlık satırlarını tanımlayacağız.

```csharp
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
```

 Burada yeni bir tablo başlatıyoruz,`HeadingFormat`mülkiyet`true` satırların başlık olduğunu belirtmek ve hücrelerin hizalamasını ve genişliğini tanımlamak için.

## 3. Adım: Tabloya Veri Satırları Ekleme

Şimdi tablomuza birden fazla veri satırı ekleyeceğiz. Bu satırlar sonraki sayfalarda tekrarlanmayacaktır.

```csharp
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
    builder.InsertCell();
    builder.RowFormat.HeadingFormat = false;
    builder.Write("Column 1 Text");
    
    builder.InsertCell();
    builder.Write("Column 2 Text");
    builder.EndRow();
}
```

 Bu döngü, her satırda iki sütun olacak şekilde tabloya 50 satırlık veri ekler.`HeadingFormat` şu şekilde ayarlandı:`false` bu satırlar için, çünkü bunlar başlık satırları değildir.

## Adım 4: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Bu, belgeyi belirtilen adla belge dizininize kaydeder.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak yalnızca birkaç satır kodla sonraki sayfalarda yinelenen başlık satırlarına sahip tablolar içeren bir Word belgesi oluşturabilirsiniz. Bu yalnızca belgelerinizin okunabilirliğini artırmakla kalmaz, aynı zamanda tutarlı ve profesyonel bir görünüm sağlar. Şimdi devam edin ve bunu projelerinizde deneyin!

## SSS'ler

### Başlık satırlarını daha da özelleştirebilir miyim?
 Evet, özelliklerini değiştirerek başlık satırlarına ek biçimlendirme uygulayabilirsiniz.`ParagraphFormat`, `RowFormat` , Ve`CellFormat`.

### Tabloya daha fazla sütun eklemek mümkün mü?
 Kesinlikle! Daha fazla hücre ekleyerek gerektiği kadar sütun ekleyebilirsiniz.`InsertCell` Yöntem.

### Diğer satırların sonraki sayfalarda tekrarlanmasını nasıl sağlayabilirim?
 Herhangi bir satırın tekrarlanmasını sağlamak için`RowFormat.HeadingFormat`mülkiyet`true` söz konusu satır için.

### Bu yöntemi bir belgedeki mevcut tablolar için kullanabilir miyim?
 Evet, mevcut tablolara şu adresten erişerek değiştirebilirsiniz:`Document` nesne ve benzer biçimlendirmenin uygulanması.

### Aspose.Words for .NET'te başka hangi tablo formatlama seçenekleri mevcut?
 Aspose.Words for .NET, hücre birleştirme, kenarlık ayarları ve tablo hizalama gibi çok çeşitli tablo formatlama seçenekleri sunar. Şuna göz atın:[dokümantasyon](https://reference.aspose.com/words/net/) daha fazla ayrıntı için.