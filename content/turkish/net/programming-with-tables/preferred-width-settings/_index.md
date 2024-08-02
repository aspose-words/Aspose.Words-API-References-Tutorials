---
title: Tercih Edilen Genişlik Ayarları
linktitle: Tercih Edilen Genişlik Ayarları
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET'te mutlak, göreceli ve otomatik genişlik ayarlarına sahip tablolar oluşturmayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/preferred-width-settings/
---
## giriiş

Tablolar, Word belgelerinizdeki bilgileri düzenlemenin ve sunmanın güçlü bir yoludur. Aspose.Words for .NET'te tablolarla çalışırken, belgenizin düzenine mükemmel şekilde uymalarını sağlamak amacıyla tablo hücrelerinin genişliğini ayarlamak için çeşitli seçenekleriniz vardır. Bu kılavuz, mutlak, göreceli ve otomatik boyutlandırma seçeneklerine odaklanarak Aspose.Words for .NET'i kullanarak tercih edilen genişlik ayarlarına sahip tablolar oluşturma sürecinde size yol gösterecektir. 

## Önkoşullar

Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET: Geliştirme ortamınızda Aspose.Words for .NET'in kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/words/net/).

2. .NET Geliştirme Ortamı: Visual Studio gibi bir .NET geliştirme ortamını kurun.

3. Temel C# Bilgisi: C# programlamaya aşinalık, kod parçacıklarını ve örnekleri daha iyi anlamanıza yardımcı olacaktır.

4.  Aspose.Words Belgeleri: Bkz.[Aspose.Words Belgeleri](https://reference.aspose.com/words/net/) ayrıntılı API bilgileri ve daha fazla bilgi için.

## Ad Alanlarını İçe Aktar

Kodlamaya başlamadan önce gerekli ad alanlarını C# projenize aktarmanız gerekir:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Bu ad alanları Aspose.Words ve Table nesnesinin temel işlevlerine erişim sağlayarak belge tablolarını değiştirmenize olanak tanır.

Tercih edilen farklı genişlik ayarlarına sahip bir tablo oluşturma sürecini net, yönetilebilir adımlara ayıralım.

## Adım 1: Document'ı ve DocumentBuilder'ı başlatın

Başlık: Yeni Bir Belge ve DocumentBuilder Oluşturma

 Açıklama: Yeni bir Word belgesi oluşturarak başlayın ve`DocumentBuilder` misal.`DocumentBuilder` class, belgenize içerik eklemenin basit bir yolunu sağlar.

```csharp
// Belgenin kaydedileceği yolu tanımlayın.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir Belge oluşturun.
Document doc = new Document();

// Bu Belge için bir DocumentBuilder oluşturun.
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Burada belgenin kaydedileceği dizini belirlersiniz ve`Document`Ve`DocumentBuilder` nesneler.

## Adım 2: İlk Tablo Hücresini Mutlak Genişliğe Sahip Yerleştirin

İlk hücreyi 40 puntoluk sabit genişlikte tabloya ekleyin. Bu, tablo boyutundan bağımsız olarak bu hücrenin her zaman 40 puntoluk bir genişliği korumasını sağlayacaktır.

```csharp

// Mutlak boyutlu bir hücre ekleyin.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell at 40 points width");
```

Bu adımda tabloyu oluşturmaya başlayacak ve mutlak genişliğe sahip bir hücre ekleyeceksiniz.`PreferredWidth.FromPoints(40)` yöntemi hücrenin genişliğini 40 noktaya ayarlar ve`Shading.BackgroundPatternColor` açık sarı arka plan rengi uygular.

## Adım 3: Göreceli Boyutta Bir Hücre Ekleme

Tablonun toplam genişliğinin %20'si kadar genişliğe sahip başka bir hücre ekleyin. Bu göreceli boyutlandırma, hücrenin masanın genişliğine orantılı olarak ayarlanmasını sağlar.

```csharp
// Göreceli (yüzde) boyutlu bir hücre ekleyin.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell at 20% width");
```

Bu hücrenin genişliği, tablonun toplam genişliğinin %20'si olacak ve bu da tablonun farklı ekran boyutlarına veya belge düzenlerine uyarlanabilmesini sağlayacaktır.

### Adım 4: Otomatik Boyutlandırılmış Hücre Ekleme

Son olarak, tabloda kalan kullanılabilir alana göre kendisini otomatik olarak boyutlandıran bir hücre ekleyin.

```csharp
// Otomatik boyutlu bir hücre ekleyin.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Cell automatically sized. The size of this cell is calculated from the table preferred width.");
builder.Writeln("In this case the cell will fill up the rest of the available space.");
```

`PreferredWidth.Auto` ayarı, bu hücrenin, diğer hücreler hesaba katıldıktan sonra kalan alana göre genişlemesine veya daralmasına olanak tanır. Bu, masa düzeninin dengeli ve profesyonel görünmesini sağlar.

## Adım 5: Belgeyi Sonlandırın ve Kaydedin

Tüm hücrelerinizi ekledikten sonra tabloyu doldurun ve belgeyi belirttiğiniz yola kaydedin.

```csharp
// Belgeyi kaydedin.
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Bu adım, tabloyu sonlandırır ve belgeyi, belirlediğiniz dizine "WorkingWithTables.PreferredWidthSettings.docx" dosya adıyla kaydeder.

## Çözüm

Aspose.Words for .NET'te tercih edilen genişlik ayarlarıyla tablolar oluşturmak, mevcut farklı boyutlandırma seçeneklerini anladığınızda çok kolaydır. İster sabit, göreli veya otomatik hücre genişliklerine ihtiyacınız olsun, Aspose.Words çeşitli tablo düzeni senaryolarını verimli bir şekilde yönetme esnekliği sağlar. Bu kılavuzda özetlenen adımları izleyerek tablolarınızın iyi yapılandırılmış ve Word belgelerinizde görsel olarak çekici olmasını sağlayabilirsiniz.

## SSS'ler

### Mutlak ve bağıl hücre genişlikleri arasındaki fark nedir?
Mutlak hücre genişlikleri sabittir ve değişmez; göreceli genişlikler ise tablonun toplam genişliğine göre ayarlanır.

### Göreli genişlikler için negatif yüzdeler kullanabilir miyim?
Hayır, hücre genişlikleri için negatif yüzdeler geçerli değildir. Yalnızca pozitif yüzdelere izin verilir.

### Otomatik boyutlandırma özelliği nasıl çalışır?
Otomatik boyutlandırma, diğer hücreler boyutlandırıldıktan sonra tabloda kalan alanı dolduracak şekilde hücrenin genişliğini ayarlar.

### Farklı genişlik ayarlarına sahip hücrelere farklı stiller uygulayabilir miyim?
Evet, genişlik ayarlarına bakılmaksızın hücrelere çeşitli stiller ve biçimlendirmeler uygulayabilirsiniz.

### Tablonun toplam genişliği tüm hücre genişliklerinin toplamından azsa ne olur?
Tablo, hücrelerin genişliklerini mevcut alana sığacak şekilde otomatik olarak ayarlayacaktır; bu, bazı hücrelerin küçülmesine neden olabilir.