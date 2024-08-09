---
title: Hücre İçi Düzen
linktitle: Hücre İçi Düzen
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı kılavuzla Aspose.Words for .NET kullanarak hücre düzenini nasıl ayarlayacağınızı öğrenin. Word belgelerini özelleştirmek isteyen geliştiriciler için mükemmeldir.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/layout-in-cell/
---
## giriiş

Word belgelerindeki tablo hücrelerinizin düzenine programlı olarak ince ayar yapmak istediyseniz, doğru yerdesiniz. Bugün Aspose.Words for .NET'i kullanarak hücre düzenini nasıl ayarlayacağımızı ele alacağız. Kolayca takip edebilmeniz için pratik bir örneği adım adım inceleyeceğiz.

## Önkoşullar

Koda geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Aspose.Words for .NET kütüphanesinin kurulu olduğundan emin olun. Eğer yapmadıysanız, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: .NET ile kurulmuş bir geliştirme ortamına ihtiyacınız olacak. Öneriler arıyorsanız Visual Studio mükemmel bir seçimdir.
3. Temel C# Bilgisi: Her adımı açıklayacağım, ancak temel C# anlayışı daha kolay ilerlemenize yardımcı olacaktır.
4.  Belge Dizini: Belgelerinizi kaydedeceğiniz dizin yolunu hazırlayın. Buna şu şekilde değineceğiz:`YOUR DOCUMENT DIRECTORY`.

## Ad Alanlarını İçe Aktar

Başlamak için projenize gerekli ad alanlarını içe aktardığınızdan emin olun:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Süreci yönetilebilir adımlara ayıralım.

## 1. Adım: Yeni Bir Belge Oluşturun

 İlk önce yeni bir Word belgesi oluşturacağız ve`DocumentBuilder` içeriğimizi oluşturmamıza yardımcı olacak nesne.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Bir Tablo Başlatın ve Satır Formatını Ayarlayın

Bir tablo oluşturmaya başlayacağız ve satırların yükseklik ve yükseklik kuralını belirleyeceğiz.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## 3. Adım: Hücreleri Ekleyin ve İçerikle Doldurun

Daha sonra, hücreleri tabloya eklemek için döngü yapıyoruz. Her 7 hücre için yeni bir tane oluşturmak üzere satırı sonlandıracağız.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## 4. Adım: Filigran Şekli Ekleme

 Şimdi belgemize filigran ekleyelim. Bir oluşturacağız`Shape` nesneyi seçin ve özelliklerini ayarlayın.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Şekli bir hücreye yerleştirilecekse tablo hücresinin dışında görüntüleyin.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Adım 5: Filigran Görünümünü Özelleştirin

Renk ve metin özelliklerini ayarlayarak filigranın görünümünü daha da özelleştireceğiz.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Adım 6: Belgeye Filigran Ekleme

Belgedeki son çalıştırmayı bulacağız ve filigranı bu konuma ekleyeceğiz.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Adım 7: Belgeyi Word 2010 için Optimize Edin

Uyumluluğu sağlamak için belgeyi Word 2010 için optimize edeceğiz.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Adım 8: Belgeyi Kaydedin

Son olarak belgemizi belirtilen dizine kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak özelleştirilmiş tablo düzenine sahip bir Word belgesini başarıyla oluşturdunuz ve filigran eklediniz. Bu eğitim, sürecin her bölümünü anlamanıza yardımcı olacak açık ve adım adım bir kılavuz sağlamayı amaçladı. Bu becerilerle artık programlı olarak daha karmaşık ve özelleştirilmiş Word belgeleri oluşturabilirsiniz.

## SSS'ler

### Filigran metni için farklı bir yazı tipi kullanabilir miyim?
 Evet, yazı tipini ayarlayarak değiştirebilirsiniz.`watermark.TextPath.FontFamily` özelliği istediğiniz yazı tipine ekleyin.

### Filigranın konumunu nasıl ayarlarım?
 Değiştirebilirsiniz`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , Ve`VerticalAlignment` filigranın konumunu ayarlamaya yönelik özellikler.

### Filigran için metin yerine resim kullanmak mümkün mü?
 Kesinlikle! Bir oluşturabilirsiniz`Shape` türü ile`ShapeType.Image` ve görüntüsünü kullanarak ayarlayın.`ImageData.SetImage` Yöntem.

### Farklı satır yüksekliklerine sahip tablolar oluşturabilir miyim?
Evet, yüksekliği değiştirerek her sıra için farklı yükseklikler ayarlayabilirsiniz.`RowFormat.Height` Bu satıra hücreleri eklemeden önce özelliği.

### Belgeden filigranı nasıl kaldırabilirim?
 Filigranı belgenin şekiller koleksiyonunda bulup, filigranı çağırarak kaldırabilirsiniz.`Remove` Yöntem.