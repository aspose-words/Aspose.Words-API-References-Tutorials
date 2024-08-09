---
title: Anahat Kenarlığını Uygula
linktitle: Anahat Kenarlığını Uygula
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word'deki bir tabloya nasıl anahat kenarlığı uygulayacağınızı öğrenin. Mükemmel tablo biçimlendirmesi için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/apply-outline-border/
---
## giriiş

Bugünkü dersimizde Aspose.Words for .NET'i kullanarak belge işleme dünyasına dalacağız. Özellikle, bir Word belgesindeki bir tabloya anahat kenarlığının nasıl uygulanacağını öğreneceğiz. Otomatik belge oluşturma ve biçimlendirmeyle sık sık çalışıyorsanız, bu, araç çantanızda bulunması gereken harika bir beceridir. O halde masalarınızı yalnızca işlevsel değil aynı zamanda görsel olarak da çekici hale getirmeye yönelik bu yolculuğa başlayalım.

## Önkoşullar

Koda geçmeden önce ihtiyacınız olacak birkaç şey var:

1.  Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olması gerekir. İndirebilirsin[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi uygun bir geliştirme ortamı.
3. Temel C# Bilgisi: Temel C# anlayışı, öğreticiyi takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Başlangıç olarak gerekli ad alanlarının içe aktarıldığından emin olun. Aspose.Words işlevlerine erişim için bu çok önemlidir.

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

Süreci basit, yönetilebilir adımlara ayıralım.

## 1. Adım: Belgeyi Yükleyin

Öncelikle formatlamak istediğimiz tablonun bulunduğu Word belgesini yüklememiz gerekiyor.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
```

 Bu adımda, şunu kullanıyoruz:`Document` Mevcut bir belgeyi yüklemek için Aspose.Words'ten sınıf. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin saklandığı gerçek yolla.

## Adım 2: Tabloya Erişin

Daha sonra biçimlendirmek istediğimiz tabloya erişmemiz gerekiyor. 

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

 Burada,`GetChild` yöntem belgedeki ilk tabloyu getirir. Parametreler`NodeType.Table, 0, true` doğru düğüm türünü aldığımızdan emin olun.

## Adım 3: Tabloyu Hizalayın

Şimdi tabloyu sayfanın ortasına hizalayalım.

```csharp
table.Alignment = TableAlignment.Center;
```

Bu adım, masanın düzgün bir şekilde ortalanmasını sağlayarak ona profesyonel bir görünüm kazandırır.

## Adım 4: Mevcut Sınırları Temizleyin

Yeni sınırları uygulamadan önce mevcut sınırları temizlememiz gerekir.

```csharp
table.ClearBorders();
```

Sınırların temizlenmesi, yeni sınırlarımızın eski tarzlara müdahale etmeden temiz bir şekilde uygulanmasını sağlar.

## Adım 5: Anahat Kenarlıklarını Ayarlayın

Şimdi yeşil çerçeve kenarlıklarını tabloya uygulayalım.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

 Her kenarlık türü (sol, sağ, üst, alt) ayrı ayrı ayarlanır. Kullanıyoruz`LineStyle.Single` sağlam bir çizgi için`1.5` çizgi genişliği için ve`Color.Green` kenarlık rengi için.

## Adım 6: Hücre Gölgelemeyi Uygulayın

Tabloyu görsel olarak daha çekici hale getirmek için hücreleri açık yeşil renkle dolduralım.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

 Burada,`SetShading` Hücrelere düz bir açık yeşil renk uygulayarak masanın öne çıkmasını sağlar.

## Adım 7: Belgeyi Kaydedin

Son olarak değiştirilen belgeyi kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Bu adım, belgenizi uygulanan biçimlendirmeyle kaydeder. Güzel biçimlendirilmiş tabloyu görmek için açabilirsiniz.

## Çözüm

Ve işte karşınızda! Bu adımları izleyerek, Aspose.Words for .NET'i kullanarak bir Word belgesindeki tabloya anahat kenarlığını başarıyla uyguladınız. Bu eğitim belgenin yüklenmesini, tabloya erişmeyi, hizalamayı, mevcut sınırları temizlemeyi, yeni kenarlıklar uygulamayı, hücre gölgelendirmeyi eklemeyi ve son olarak belgeyi kaydetmeyi kapsıyordu. 

Bu becerilerle tablolarınızın görsel sunumunu geliştirebilir, belgelerinizi daha profesyonel ve çekici hale getirebilirsiniz. Mutlu kodlama!

## SSS'ler

### Tablonun her kenarlığına farklı stiller uygulayabilir miyim?  
 Evet, parametreleri ayarlayarak her kenarlığa farklı stiller ve renkler uygulayabilirsiniz.`SetBorder` Yöntem.

### Kenarlığın genişliğini nasıl değiştirebilirim?  
 Üçüncü parametreyi değiştirerek genişliği değiştirebilirsiniz.`SetBorder` Yöntem. Örneğin,`1.5` 1,5 puntoluk bir genişlik ayarlar.

### Gölgelendirmeyi tek tek hücrelere uygulamak mümkün mü?  
 Evet, her hücreye erişerek ve`SetShading` Yöntem.

### Kenarlıklar ve gölgelendirme için başka renkler kullanabilir miyim?  
 Kesinlikle! Mevcut olan herhangi bir rengi kullanabilirsiniz`System.Drawing.Color` sınıf.

### Tabloyu yatay olarak nasıl ortalayabilirim?  
`table.Alignment = TableAlignment.Center;` Koddaki satır, tabloyu sayfada yatay olarak ortalar.