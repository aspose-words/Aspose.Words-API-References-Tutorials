---
title: Tabloyu ve Hücreyi Farklı Kenarlıklarla Biçimlendir
linktitle: Tabloyu ve Hücreyi Farklı Kenarlıklarla Biçimlendir
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak tabloları ve hücreleri farklı kenarlıklarla nasıl formatlayacağınızı öğrenin. Word belgelerinizi özelleştirilmiş tablo stilleri ve hücre gölgelendirmesiyle geliştirin.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---
## giriiş

Tabloların ve hücrelerin kenarlıklarını özelleştirerek Word belgelerinizin daha profesyonel görünmesini hiç denediniz mi? Değilse, bir ziyafet içindesiniz! Bu eğitim, Aspose.Words for .NET'i kullanarak tabloları ve hücreleri farklı kenarlıklarla biçimlendirme sürecinde size yol gösterecektir. Yalnızca birkaç satır kodla tablolarınızın görünümünü değiştirme gücüne sahip olduğunuzu hayal edin. İlginizi mi çekti? Gelin derinlemesine inceleyelim ve bunu kolaylıkla nasıl başarabileceğinizi keşfedelim.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- C# programlamanın temel anlayışı.
- Bilgisayarınızda Visual Studio yüklü.
-  Aspose.Words for .NET kitaplığı. Henüz yüklemediyseniz indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
-  Geçerli bir Aspose lisansı. Şu adresten ücretsiz deneme sürümü veya geçici lisans alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET ile çalışmak için gerekli ad alanlarını projenize aktarmanız gerekir. Kod dosyanızın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System.Drawing;
```

## 1. Adım: Document ve DocumentBuilder'ı başlatın

Öncelikle yeni bir belge oluşturmanız ve belge içeriğinin oluşturulmasına yardımcı olan DocumentBuilder'ı başlatmanız gerekir. 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Tablo Oluşturmaya Başlayın

Daha sonra, bir tablo oluşturmaya başlamak ve ilk hücreyi eklemek için DocumentBuilder'ı kullanın.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

## 3. Adım: Tablo Kenarlıklarını Ayarlayın

Tüm tablonun kenarlıklarını ayarlayın. Bu adım, aksi belirtilmedikçe tablodaki tüm hücrelerin tutarlı bir kenarlık stiline sahip olmasını sağlar.

```csharp
// Tüm tablonun kenarlıklarını ayarlayın.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
```

## Adım 4: Hücre Gölgelemeyi Uygulayın

Hücreleri görsel olarak farklı kılmak için gölgelendirme uygulayın. Bu örnekte ilk hücrenin arka plan rengini kırmızıya ayarlayacağız.


```csharp
// Bu hücre için hücre gölgelendirmesini ayarlayın.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
```

## Adım 5: Farklı Gölgelendirmeye Sahip Başka Bir Hücre Ekleme

İkinci hücreyi ekleyin ve farklı bir gölgeleme rengi uygulayın. Bu, tablonun daha renkli ve okunması kolay olmasını sağlar.

```csharp
builder.InsertCell();
// İkinci hücre için farklı bir hücre gölgelemesi belirtin.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
```

## Adım 6: Hücre Biçimlendirmesini Temizle

Sonraki hücrelerin aynı stilleri devralmamasını sağlamak için önceki işlemlerdeki hücre biçimlendirmesini temizleyin.


```csharp
// Önceki işlemlerden hücre biçimlendirmesini temizleyin.
builder.CellFormat.ClearFormatting();
```

## Adım 7: Belirli Hücreler İçin Kenarlıkları Özelleştirin

Öne çıkmalarını sağlamak için belirli hücrelerin kenarlıklarını özelleştirin. Burada yeni satırın ilk hücresi için daha büyük kenarlıklar ayarlayacağız.

```csharp
builder.InsertCell();
// Bu satırın ilk hücresi için daha büyük kenarlıklar oluşturun. Bu farklı olacak
// tablo için belirlenen kenarlıklarla karşılaştırılır.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
```

## Adım 8: Son Hücreyi Ekle

Son hücreyi ekleyin ve tablonun varsayılan stillerini kullanması için biçimlendirmesinin temizlendiğinden emin olun.

```csharp
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Adım 9: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Çözüm

İşte buyur! Aspose.Words for .NET kullanarak tabloları ve hücreleri farklı kenarlıklarla nasıl formatlayacağınızı öğrendiniz. Tablo kenarlıklarını ve hücre gölgelendirmesini özelleştirerek belgelerinizin görsel çekiciliğini önemli ölçüde artırabilirsiniz. Öyleyse devam edin, farklı stilleri deneyin ve belgelerinizin öne çıkmasını sağlayın!

## SSS'ler

### Her hücre için farklı kenarlık stilleri kullanabilir miyim?
 Evet, her hücre için farklı kenarlık stilleri ayarlayabilirsiniz.`CellFormat.Borders` mülk.

### Bir tablodaki tüm sınırları nasıl kaldırabilirim?
 Kenarlık stilini şu şekilde ayarlayarak tüm kenarlıkları kaldırabilirsiniz:`LineStyle.None`.

### Her hücre için farklı kenarlık renkleri ayarlamak mümkün mü?
 Kesinlikle! kullanarak her hücrenin kenarlık rengini özelleştirebilirsiniz.`CellFormat.Borders.Color` mülk.

### Görüntüleri hücre arka planı olarak kullanabilir miyim?
Aspose.Words görselleri doğrudan hücre arka planı olarak desteklemese de, hücreye bir görsel ekleyebilir ve hücre alanını kaplayacak şekilde boyutunu ayarlayabilirsiniz.

### Tablodaki hücreleri nasıl birleştiririm?
 kullanarak hücreleri birleştirebilirsiniz.`CellFormat.HorizontalMerge`Ve`CellFormat.VerticalMerge` özellikler.