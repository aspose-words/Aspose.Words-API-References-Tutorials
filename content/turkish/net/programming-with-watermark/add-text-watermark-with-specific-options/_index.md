---
title: Belirli Seçeneklerle Metin Filigranı Ekleme
linktitle: Belirli Seçeneklerle Metin Filigranı Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgelerinize belirli seçeneklerle bir metin filigranını nasıl ekleyeceğinizi öğrenin. Yazı tipini, boyutunu, rengini ve düzenini kolayca özelleştirin.
type: docs
weight: 10
url: /tr/net/programming-with-watermark/add-text-watermark-with-specific-options/
---
## giriiş

Filigranlar, belgeleri gizli olarak işaretlemekten kişiselleştirilmiş bir dokunuş eklemeye kadar çeşitli amaçlara hizmet ederek, Word belgelerinize şık ve işlevsel bir eklenti olabilir. Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesine nasıl metin filigranı ekleneceğini inceleyeceğiz. Yazı tipi ailesi, yazı tipi boyutu, renk ve düzen gibi yapılandırabileceğiniz belirli seçenekleri ayrıntılı olarak ele alacağız. Sonunda, belgenizin filigranını tam ihtiyaçlarınıza uyacak şekilde özelleştirebileceksiniz. O halde kod düzenleyicinizi alın ve başlayalım!

## Önkoşullar

Devam etmeden önce aşağıdakilerin yerinde olduğundan emin olun:

1.  Aspose.Words for .NET Library: Aspose.Words kütüphanesinin kurulu olması gerekir. Henüz yapmadıysanız adresinden indirebilirsiniz.[Aspose.Words İndirme Linki](https://releases.aspose.com/words/net/).
2. Temel C# Anlayışı: Bu eğitimde programlama dili olarak C# kullanılacaktır. C# sözdiziminin temel bir kavrayışı faydalı olacaktır.
3. .NET Geliştirme Ortamı: .NET uygulamalarınızı oluşturup çalıştırabileceğiniz bir geliştirme ortamı kurduğunuzdan (Visual Studio gibi) emin olun.

## Ad Alanlarını İçe Aktar

Aspose.Words ile çalışmak için projenize gerekli ad alanlarını eklemeniz gerekir. İçe aktarmanız gerekenler:

```csharp
using Aspose.Words;
using Aspose.Words.Rendering;
using System.Drawing;
```

## 1. Adım: Belgenizi Ayarlayın

 Öncelikle çalışmak istediğiniz belgeyi yüklemeniz gerekir. Bu eğitim için adlı örnek bir belge kullanacağız.`Document.docx`. Bu belgenin belirttiğiniz dizinde bulunduğundan emin olun.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Bu adımda belgenizin bulunduğu dizini tanımlayacak ve onu bir örneğine yükleyeceksiniz.`Document` sınıf.

## 2. Adım: Filigran Seçeneklerini Yapılandırma

Ardından metin filigranınızın seçeneklerini yapılandırın. Yazı tipi ailesi, yazı tipi boyutu, renk ve düzen gibi çeşitli özellikleri özelleştirebilirsiniz. Bu seçenekleri ayarlayalım.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
    FontFamily = "Arial",
    FontSize = 36,
    Color = Color.Black,
    Layout = WatermarkLayout.Horizontal,
    IsSemitrasparent = false
};
```

İşte her seçeneğin yaptığı şey:
- `FontFamily`: Filigran metninin yazı tipini belirtir.
- `FontSize`: Filigran metninin boyutunu ayarlar.
- `Color`: Filigran metninin rengini tanımlar.
- `Layout`Filigranın yönünü (yatay veya çapraz) belirler.
- `IsSemitrasparent`: Filigranın yarı şeffaf olup olmayacağını ayarlar.

## 3. Adım: Filigran Metnini Ekleyin

Şimdi, önceden yapılandırılan seçenekleri kullanarak filigranı belgenize uygulayın. Bu adımda filigran metnini "Test" olarak ayarlayacak ve tanımladığınız seçenekleri uygulayacaksınız.

```csharp
doc.Watermark.SetText("Test", options);
```

Bu kod satırı, belirtilen seçenekleri uygulayarak "Test" metnini içeren filigranı belgeye ekler.

## Adım 4: Belgeyi Kaydedin

Son olarak, belgeyi yeni filigranın uygulandığı şekilde kaydedin. Orijinal belgenin üzerine yazılmasını önlemek için yeni bir adla kaydedebilirsiniz.

```csharp
doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

Bu kod parçacığı, değiştirilen belgeyi yeni bir dosya adıyla aynı dizine kaydeder.

## Çözüm

Aspose.Words for .NET kullanarak Word belgelerinize metin filigranı eklemek, bunu yönetilebilir adımlara böldüğünüzde basit bir işlemdir. Bu öğreticiyi takip ederek yazı tipi, boyut, renk, düzen ve şeffaflık gibi çeşitli filigran seçeneklerini nasıl yapılandıracağınızı öğrendiniz. Bu becerilerle artık belgelerinizi ihtiyaçlarınızı daha iyi karşılayacak veya gizlilik veya markalama gibi önemli bilgileri içerecek şekilde özelleştirebilirsiniz.

 Herhangi bir sorunuz varsa veya daha fazla yardıma ihtiyacınız varsa, şuraya göz atmaktan çekinmeyin:[Aspose.Words Belgeleri](https://reference.aspose.com/words/net/) veya ziyaret edin[Aspose Destek Forumu](https://forum.aspose.com/c/words/8) daha fazla yardım için.

## SSS'ler

### Filigran için farklı yazı tipleri kullanabilir miyim?

 Evet, sisteminizde yüklü olan herhangi bir yazı tipini belirterek seçebilirsiniz.`FontFamily` içindeki mülk`TextWatermarkOptions`.

### Filigranın rengini nasıl değiştiririm?

 Filigranın rengini ayarlayarak değiştirebilirsiniz.`Color` içindeki mülk`TextWatermarkOptions` herhangi birine`System.Drawing.Color` değer.

### Bir belgeye birden fazla filigran eklemek mümkün mü?

Aspose.Words aynı anda bir filigran eklemeyi destekler. Birden fazla filigran eklemek için bunları sırayla oluşturup uygulamanız gerekir.

### Filigranın konumunu ayarlayabilir miyim?

`WatermarkLayout`özelliği yönlendirmeyi belirler ancak hassas konumlandırma ayarları doğrudan desteklenmez. Tam yerleştirme için başka teknikler kullanmanız gerekebilir.

### Yarı şeffaf bir filigrana ihtiyacım olursa ne olur?

 Ayarla`IsSemitrasparent`mülkiyet`true` filigranınızı yarı şeffaf hale getirmek için.