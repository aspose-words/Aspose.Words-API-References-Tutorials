---
title: Biçimlendirilmiş Tablo
linktitle: Biçimlendirilmiş Tablo
second_title: Aspose.Words Belge İşleme API'si
description: Bu ayrıntılı adım adım kılavuzla Aspose.Words for .NET'i kullanarak Word belgelerinde tabloları nasıl oluşturacağınızı ve formatlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/formatted-table/
---
## giriiş

Word belgelerinde tabloları programlı olarak oluşturmak ve biçimlendirmek göz korkutucu bir görev gibi görünebilir, ancak Aspose.Words for .NET ile bu iş basit ve yönetilebilir hale geliyor. Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde biçimlendirilmiş bir tablonun nasıl oluşturulacağını size anlatacağız. Ortamınızı ayarlamaktan belgenizi güzel biçimlendirilmiş bir tabloyla kaydetmeye kadar her şeyi ele alacağız.

## Önkoşullar

Koda dalmadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1. Aspose.Words for .NET Kütüphanesi: Şu adresten indirin:[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio benzeri bir IDE.
3. .NET Framework: Makinenizde .NET Framework'ün kurulu olduğundan emin olun.

## Ad Alanlarını İçe Aktar

Gerçek kodu yazmadan önce gerekli ad alanlarını içe aktarmanız gerekir:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

## 1. Adım: Belge Dizininizi Kurun

Öncelikle belgenizin kaydedileceği yolu tanımlamanız gerekir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz gerçek yolla.

## Adım 2: Document'ı ve DocumentBuilder'ı başlatın

Şimdi yeni bir belge ve DocumentBuilder nesnesini başlatın.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

`DocumentBuilder` belge oluşturma sürecini basitleştiren bir yardımcı sınıftır.

## 3. Adım: Tabloyu Başlatın

 Daha sonra tabloyu kullanarak tabloyu oluşturmaya başlayın.`StartTable` Yöntem.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

Tabloyu başlatmak için bir hücre eklemek gereklidir.

## 4. Adım: Tablo Genelinde Formatlamayı Uygulayın

Tablonun tamamını etkileyen biçimlendirmeyi uygulayabilirsiniz. Örneğin, sol girintiyi ayarlamak:

```csharp
table.LeftIndent = 20.0;
```

## Adım 5: Başlık Satırını Biçimlendirin

Başlık satırının yüksekliğini, hizalamasını ve diğer özelliklerini ayarlayın.

```csharp
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");
```

Bu adımda arka plan rengini, yazı tipi boyutunu ve hizalamayı ayarlayarak başlık satırının öne çıkmasını sağlıyoruz.

## Adım 6: Ek Başlık Hücreleri Ekleme

Başlık satırına daha fazla hücre ekleyin:

```csharp
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");
builder.EndRow();
```

## Adım 7: Gövde Satırlarını Biçimlendirin

Başlığı ayarladıktan sonra tablonun gövdesini biçimlendirin:

```csharp
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;
```

## Adım 8: Gövde Satırlarını Ekle

İçeriği içeren gövde satırlarını ekleyin:

```csharp
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Row 1, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 1, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 1, Cell 3 Content");
builder.EndRow();
```

Ek satırlar için tekrarlayın:

```csharp
builder.InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Row 2, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 2, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 2, Cell 3 Content.");
builder.EndRow();
builder.EndTable();
```

## Adım 9: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Bu, biçimlendirilmiş tabloyla bir Word belgesi oluşturup kaydedecektir.

## Çözüm

Ve işte karşınızda! Bu adımları izleyerek Aspose.Words for .NET'i kullanarak bir Word belgesinde iyi biçimlendirilmiş bir tablo oluşturabilirsiniz. Bu güçlü kitaplık, Word belgelerini programlı olarak düzenlemeyi kolaylaştırarak zamandan ve emekten tasarruf etmenizi sağlar.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, Word belgelerini programlı olarak oluşturmak, düzenlemek ve dönüştürmek için güçlü bir kütüphanedir.

### Farklı satırlar için farklı renkler kullanabilir miyim?
Evet, farklı satırlara veya hücrelere renkler de dahil olmak üzere farklı biçimlendirmeler uygulayabilirsiniz.

### Aspose.Words for .NET ücretsiz mi?
 Aspose.Words for .NET ücretli bir kütüphanedir, ancak[ücretsiz deneme](https://releases.aspose.com/).

### Aspose.Words for .NET için nasıl destek alabilirim?
 adresinden destek alabilirsiniz.[Topluluk forumlarını görevlendirin](https://forum.aspose.com/c/words/8).

### Aspose.Words for .NET ile başka türde belgeler oluşturabilir miyim?
Evet, Aspose.Words for .NET, PDF, HTML ve TXT dahil olmak üzere çeşitli belge formatlarını destekler.