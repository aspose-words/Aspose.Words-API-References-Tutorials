---
title: Dikey Ankraj
linktitle: Dikey Ankraj
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki metin kutuları için dikey bağlantı konumlarını nasıl ayarlayacağınızı öğrenin. Kolay adım adım kılavuz dahildir.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/vertical-anchor/
---
## giriiş

Hiç bir Word belgesindeki metin kutusunun içinde metnin tam olarak nerede görüneceğini kontrol etmeye ihtiyaç duyduğunuzu fark ettiniz mi? Belki metninizin metin kutusunun üstüne, ortasına veya altına sabitlenmesini istiyorsunuz? Eğer öyleyse, doğru yerdesiniz! Bu eğitimde, Word belgelerindeki metin kutularının dikey bağlantısını ayarlamak için Aspose.Words for .NET'in nasıl kullanılacağını keşfedeceğiz. Dikey sabitlemeyi, metninizi kabının içinde tam olarak istediğiniz yere konumlandıran sihirli bir değnek olarak düşünün. Dalmaya hazır mısınız? Hadi başlayalım!

## Önkoşullar

Dikey sabitlemenin somun ve cıvatalarına dalmadan önce birkaç şeyin hazır olması gerekir:

1.  Aspose.Words for .NET: Aspose.Words for .NET kütüphanesinin kurulu olduğundan emin olun. Henüz sahip değilseniz, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
2. Visual Studio: Bu eğitimde, kodlama için Visual Studio veya başka bir .NET IDE kullandığınız varsayılmaktadır.
3. Temel C# Bilgisi: C# ve .NET'e aşina olmak, süreci sorunsuz bir şekilde takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını C# kodunuza aktarmanız gerekir. Burası uygulamanıza kullanacağınız sınıfları ve yöntemleri nerede bulacağını söyleyeceğiniz yerdir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Bu ad alanları, belgeler ve şekillerle çalışmak için ihtiyaç duyacağınız sınıfları sağlar.

## 1. Adım: Belgeyi Başlatın

Öncelikle yeni bir Word belgesi oluşturmanız gerekiyor. Bunu, resim yapmaya başlamadan önce tuvalinizi hazırlamak olarak düşünün.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Burada,`Document` senin boş tuvalin ve`DocumentBuilder` şekil ve metin eklemenizi sağlayan boya fırçanızdır.

## Adım 2: TextBox Şekli Ekleme

Şimdi belgemize bir metin kutusu ekleyelim. Metninizin yaşayacağı yer burasıdır. 

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

 Bu örnekte,`ShapeType.TextBox` istediğiniz şekli belirtir ve`200, 200` metin kutusunun nokta cinsinden genişliği ve yüksekliğidir.

## Adım 3: Dikey Bağlantıyı Ayarlayın

İşte sihrin gerçekleştiği yer! Metin kutusu içindeki metnin dikey hizalamasını ayarlayabilirsiniz. Bu, metnin metin kutusunun üstüne mi, ortasına mı yoksa altına mı sabitleneceğini belirler.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

 Bu durumda,`TextBoxAnchor.Bottom`metnin metin kutusunun altına sabitlenmesini sağlar. Ortalanmasını veya üste hizalanmasını istiyorsanız şunu kullanırsınız:`TextBoxAnchor.Center` veya`TextBoxAnchor.Top`, sırasıyla.

## Adım 4: TextBox'a Metin Ekleme

Şimdi metin kutunuza biraz içerik eklemenin zamanı geldi. Bunu tuvalinizi son dokunuşlarla doldurmak olarak düşünün.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

 Burada,`MoveTo` Metnin metin kutusuna eklenmesini sağlar ve`Write` gerçek metni ekler.

## Adım 5: Belgeyi Kaydedin

Son adım belgenizi kaydetmektir. Bu, bitmiş tablonuzu bir çerçeveye koymak gibidir.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir Word belgesindeki metin kutusu içindeki metnin dikey hizalamasını nasıl kontrol edeceğinizi öğrendiniz. Metni ister üste, ortaya ister aşağıya tutturuyor olun, bu özellik size belgenizin düzeni üzerinde hassas kontrol sağlar. Yani bir dahaki sefere belgenizin metin yerleşiminde değişiklik yapmanız gerektiğinde ne yapmanız gerektiğini bileceksiniz!

## SSS'ler

### Word belgesinde dikey sabitleme nedir?
Dikey sabitleme, metnin üst, orta veya alt hizalama gibi bir metin kutusu içinde konumlandırıldığı yerleri kontrol eder.

### Metin kutularının yanı sıra başka şekiller de kullanabilir miyim?
Evet, dikey sabitlemeyi diğer şekillerle kullanabilirsiniz ancak metin kutuları en yaygın kullanım durumudur.

### Metin kutusunu oluşturduktan sonra bağlantı noktasını nasıl değiştiririm?
 Bağlantı noktasını ayarlayarak değiştirebilirsiniz.`VerticalAnchor` metin kutusu şekli nesnesindeki özellik.

### Metni metin kutusunun ortasına sabitlemek mümkün mü?
 Kesinlikle! Sadece kullan`TextBoxAnchor.Center` Metni metin kutusu içinde dikey olarak ortalamak için.

### Aspose.Words for .NET hakkında daha fazla bilgiyi nerede bulabilirim?
 Şuna göz atın:[Aspose.Words Belgeleri](https://reference.aspose.com/words/net/) daha fazla ayrıntı ve kılavuz için.