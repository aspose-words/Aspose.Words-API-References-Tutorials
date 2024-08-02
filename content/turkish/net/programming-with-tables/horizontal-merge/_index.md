---
title: Yatay Birleştirme
linktitle: Yatay Birleştirme
second_title: Aspose.Words Belge İşleme API'si
description: Bu ayrıntılı, adım adım eğitimle Aspose.Words for .NET kullanarak bir Word belgesindeki hücreleri yatay olarak nasıl birleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/horizontal-merge/
---
## giriiş

Selam! Aspose.Words for .NET dünyasına dalmaya hazır mısınız? Bugün çok kullanışlı bir özelliği ele alacağız: tablolarda yatay birleştirme. Bu biraz teknik gelebilir ama endişelenmeyin, arkanızı kolluyorum. Bu eğitimin sonunda, Word belgelerinizdeki hücreleri programlı olarak birleştirme konusunda uzman olacaksınız. O halde haydi kollarımızı sıvayalım ve başlayalım!

## Önkoşullar

İşin özüne geçmeden önce, yerine getirmeniz gereken birkaç şey var:

1. Aspose.Words for .NET Kütüphanesi: Henüz yapmadıysanız Aspose.Words for .NET kütüphanesini indirin. Onu yakalayabilirsin[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi uygun bir geliştirme ortamının kurulduğundan emin olun.
3. Temel C# Bilgisi: C# programlamanın temel bir anlayışı yararlı olacaktır.

Bunları sıraladıktan sonra artık hazırsınız!

## Ad Alanlarını İçe Aktar

Koda dalmadan önce gerekli ad alanlarının içe aktarıldığından emin olalım. C# projenize şunları eklediğinizden emin olun:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Pekala, Aspose.Words for .NET kullanarak bir Word belgesinde tablo hücrelerini yatay olarak birleştirme sürecini inceleyelim.

## 1. Adım: Belgenizi Ayarlama

 Öncelikle yeni bir Word belgesi oluşturmamız ve başlatmamız gerekiyor.`DocumentBuilder`:

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Bu kod parçacığı yeni bir belge oluşturur ve`DocumentBuilder` hareket için.

## Adım 2: İlk Hücreyi Ekleme

Daha sonra ilk hücreyi yerleştirip yatay birleştirme için işaretleyerek başlıyoruz:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
```

 Burada yeni bir hücre ekliyoruz ve ayarlıyoruz.`HorizontalMerge`mülkiyet`CellMerge.First`, bu hücrenin birleştirilmiş hücre dizisinin başlangıcı olduğunu belirtir.

## Adım 3: Birleştirilmiş Hücreyi Ekleme

Şimdi öncekiyle birleştirilecek hücreyi ekliyoruz:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();
```

 Bu hücre, kullanılarak önceki hücreyle birleştirilecek şekilde ayarlandı.`CellMerge.Previous` . Satırı nasıl sonlandırdığımıza dikkat edin`builder.EndRow()`.

## Adım 4: Birleştirilmemiş Hücreleri Ekleme

Farkı göstermek için birkaç birleşmemiş hücre ekleyelim:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in one cell.");
builder.InsertCell();
builder.Write("Text in another cell.");
builder.EndRow();
```

Burada yatay birleştirme olmadan iki hücre ekliyoruz. Bu, hücrelerin birleştirilmiş bir dizinin parçası olmadıklarında nasıl davrandıklarını gösterir.

## Adım 5: Masayı Bitirmek

Son olarak tabloyu sonlandırıp belgeyi kaydediyoruz:

```csharp
builder.EndTable();
doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

Bu kod parçacığı tabloyu tamamlar ve belgeyi belirtilen dizine kaydeder.

## Çözüm

İşte buyur! Aspose.Words for .NET'i kullanarak bir Word belgesindeki hücreleri yatay olarak birleştirme sanatında artık ustalaştınız. Bu adımları takip ederek karmaşık tablo yapılarını kolaylıkla oluşturabilirsiniz. Belgelerinizi ihtiyaç duyduğunuz kadar dinamik ve esnek hale getirmek için Aspose.Words'ün yeteneklerini denemeye ve keşfetmeye devam edin. Mutlu kodlama!

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin .NET uygulamalarında Word belgelerini programlı olarak oluşturmasına, düzenlemesine ve işlemesine olanak tanıyan güçlü bir kitaplıktır.

### Aspose.Words for .NET ile hücreleri dikey olarak birleştirebilir miyim?
 Evet, hücreleri dikey olarak da birleştirebilirsiniz.`CellFormat.VerticalMerge` mülk.

### Aspose.Words for .NET'in kullanımı ücretsiz mi?
 Aspose.Words for .NET ücretsiz deneme sürümü sunuyor ancak tam işlevsellik için bir lisans satın almanız gerekecek. Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### Aspose.Words for .NET hakkında nasıl daha fazla bilgi edinebilirim?
 Ayrıntılı belgeleri inceleyebilirsiniz[Burada](https://reference.aspose.com/words/net/).

### Aspose.Words for .NET için nereden destek alabilirim?
 Sorularınız veya sorunlarınız için Aspose destek forumunu ziyaret edebilirsiniz.[Burada](https://forum.aspose.com/c/words/8).