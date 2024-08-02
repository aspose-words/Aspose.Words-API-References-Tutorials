---
title: Bölünmüş Tablo
linktitle: Bölünmüş Tablo
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki tabloları nasıl böleceğinizi öğrenin. Adım adım kılavuzumuz masa yönetimini kolay ve verimli hale getirir.
type: docs
weight: 10
url: /tr/net/programming-with-tables/split-table/
---
## giriiş

Hiç kendinizi bir Word belgesinde büyük bir tabloyla çalışırken buldunuz mu ve onu daha küçük, daha kolay yönetilebilir iki tabloya bölmeyi dilediniz mi? Bugün Aspose.Words for .NET kullanarak bunu tam olarak nasıl başarabileceğinizi inceliyoruz. İster kapsamlı veri tablolarıyla ister karmaşık belge yapılarıyla ilgileniyor olun, tabloları bölmek okunabilirliği ve düzeni artırmanıza yardımcı olabilir. Aspose.Words for .NET kullanarak bir tabloyu bölmek için adım adım süreci inceleyelim.

## Önkoşullar

Eğiticiye geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET Kütüphanesi: Aspose.Words for .NET kütüphanesini indirip yüklediğinizden emin olun. Şu adresten alabilirsiniz:[Aspose sürümler sayfası](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi .NET framework desteğine sahip bir geliştirme ortamı kurun.
3. Örnek Belge: Word belgesi hazırlayın (`Tables.docx`) bölme işlemini uygulamak için en az bir tabloyla.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını projenize aktarın. Bu, Aspose.Words tarafından sağlanan sınıflara ve yöntemlere erişmenizi sağlar.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## 1. Adım: Belgeyi Yükleyin

Bölmek istediğiniz tabloyu içeren belgeyi yükleyerek başlayalım. Belgenizin doğru yolunu belirttiğinizden emin olun.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
```

## Adım 2: Bölünecek Tabloyu Belirleyin

Daha sonra bölmek istediğiniz tabloyu tanımlayın ve alın. Bu örnekte belgedeki ilk tabloyu hedefleyeceğiz.

```csharp
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Adım 3: Bölünecek Satırı Seçin

Tabloyu bölmek istediğiniz satırı belirleyin. Burada tabloyu üçüncü satıra (dahil) bölüyoruz.

```csharp
Row row = firstTable.Rows[2];
```

## Adım 4: Yeni Bir Masa Kabı Oluşturun

Orijinal tablodan taşınacak satırları tutacak yeni bir tablo kapsayıcısı oluşturun.

```csharp
Table table = (Table)firstTable.Clone(false);
```

## Adım 5: Yeni Masa Kabını Takın

Yeni masa kabını belgedeki orijinal masanın hemen sonrasına ekleyin.

```csharp
firstTable.ParentNode.InsertAfter(table, firstTable);
```

## Adım 6: Tampon Paragrafı Ekleme

İki tablonun ayrı kalmasını sağlamak için arasına bir tampon paragraf ekleyin.

```csharp
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
```

## Adım 7: Satırları Yeni Tabloya Taşı

Satırları orijinal tablodan yeni tablo kapsayıcısına taşıyın. Bu döngü belirtilen satır (dahil) taşınıncaya kadar devam eder.

```csharp
Row currentRow;
do
{
    currentRow = firstTable.LastRow;
    table.PrependChild(currentRow);
} while (currentRow != row);
```

## Adım 8: Belgeyi Kaydedin

Son olarak, değiştirilen belgeyi tablolar bölünmüş olarak kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Çözüm

İşte buyur! Bu adımları izleyerek Aspose.Words for .NET'i kullanarak bir Word belgesindeki tabloyu kolayca bölebilirsiniz. Bu yaklaşım, büyük tabloları daha etkili bir şekilde yönetmenize yardımcı olarak belgelerinizin okunabilirliğini ve organizasyonunu geliştirir. Bir deneyin ve Word belgelerindeki tablolarla çalışmanızı nasıl kolaylaştırdığını görün.

## SSS'ler

### Bir tabloyu birden fazla satıra bölebilir miyim?
Evet, her bölme noktası için işlemi tekrarlayarak bir tabloyu birden çok satıra bölebilirsiniz.

### Orijinal tablonun formatına ne olur?
Yeni tablo, orijinal tablonun biçimlendirmesini devralır. Gerektiğinde yeni tabloya belirli biçimlendirme değişiklikleri uygulanabilir.

### Tabloları tekrar birleştirmek mümkün mü?
Evet, benzer yöntemleri kullanarak satırları bir tablodan diğerine taşıyarak tabloları birleştirebilirsiniz.

### Bu yöntem iç içe geçmiş tablolarla çalışır mı?
Evet, Aspose.Words for .NET iç içe tablolardaki işlemleri de destekler.

### Bu işlemi birden fazla belge için otomatikleştirebilir miyim?
Kesinlikle! Birden fazla belge için tablo bölme işlemini otomatikleştirmek amacıyla bir komut dosyası veya uygulama oluşturabilirsiniz.