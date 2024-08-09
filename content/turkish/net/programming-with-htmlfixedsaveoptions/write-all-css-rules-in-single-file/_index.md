---
title: Tüm Css Kurallarını Tek Dosyaya Yazın
linktitle: Tüm Css Kurallarını Tek Dosyaya Yazın
second_title: Aspose.Words Belge İşleme API'si
description: Daha temiz kod ve daha kolay bakım için Aspose.Words for .NET kullanarak tüm CSS kurallarını tek bir dosyada içeren Word belgelerini HTML'ye nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---
## giriiş

Word belgelerini HTML'ye dönüştürürken hiç kendinizi her yere dağılmış CSS kuralları ağına karışmış halde buldunuz mu? Endişelenme! Bugün Aspose.Words for .NET'in tüm CSS kurallarını tek bir dosyaya yazmanıza olanak tanıyan harika bir özelliğini inceliyoruz. Bu sadece kodunuzu düzenlemekle kalmaz, aynı zamanda hayatınızı da çok kolaylaştırır. Kemerlerinizi bağlayın ve daha temiz, daha verimli HTML çıktısına yönelik bu yolculuğa başlayalım!

## Önkoşullar

İşin özüne dalmadan önce ördeklerimizi sıraya koyalım. Başlamak için ihtiyacınız olan şey:

1.  Aspose.Words for .NET: Aspose.Words for .NET kütüphanesine sahip olduğunuzdan emin olun. Henüz sahip değilseniz, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
2. .NET Geliştirme Ortamı: Makinenizde bir .NET geliştirme ortamının kurulu olması gerekir. Visual Studio popüler bir seçimdir.
3. Temel C# Bilgisi: C# programlamanın temel bir anlayışı faydalı olacaktır.
4. Bir Word Belgesi: Dönüştürmek istediğiniz bir Word belgesini (.docx) hazır bulundurun.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını C# projenize aktaralım. Bu, Aspose.Words işlevlerine kolayca erişmemizi sağlayacaktır.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Peki, süreci takip edilmesi kolay adımlara ayıralım. Her adım, her şeyin sorunsuz ilerlemesini sağlamak için sürecin belirli bir bölümünde size rehberlik edecektir.

## 1. Adım: Belge Dizininizi Kurun

Öncelikle belge dizininizin yolunu tanımlamamız gerekiyor. Burası Word belgenizin saklandığı ve dönüştürülen HTML'nin kaydedileceği yerdir.

```csharp
// Belge dizininize erişim yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Word Belgesini Yükleyin

 Daha sonra HTML’ye dönüştürmek istediğiniz Word belgesini yüklüyoruz. Bu, kullanılarak yapılır.`Document` Aspose.Words kütüphanesinden sınıf.

```csharp
// Word belgesini yükleyin
Document doc = new Document(dataDir + "Document.docx");
```

## 3. Adım: HTML Kaydetme Seçeneklerini Yapılandırın

 Şimdi HTML kaydetme seçeneklerini yapılandırmamız gerekiyor. Özellikle tüm CSS kurallarını tek bir dosyaya yazan özelliği etkinleştirmek istiyoruz. Bu, ayarın ayarlanmasıyla elde edilir.`SaveFontFaceCssSeparately`mülkiyet`false`.

```csharp
// "Tüm CSS kurallarını tek dosyaya yaz" özelliğiyle yedekleme seçeneklerini yapılandırın
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions 
{ 
    SaveFontFaceCssSeparately = false 
};
```

## Adım 4: Belgeyi Sabit HTML'ye Dönüştürün

Son olarak yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi HTML dosyası olarak kaydediyoruz. Bu adım, tüm CSS kurallarının tek bir dosyaya yazılmasını sağlar.

```csharp
//Belgeyi sabit HTML'ye dönüştür
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Çözüm

Ve işte karşınızda! Yalnızca birkaç satır kodla, Word belgenizi, tüm CSS kurallarının tek bir dosyada düzgün bir şekilde organize edildiği şekilde başarıyla HTML'ye dönüştürdünüz. Bu yöntem yalnızca CSS yönetiminizi basitleştirmekle kalmaz, aynı zamanda HTML belgelerinizin sürdürülebilirliğini de artırır. Yani bir dahaki sefere bir Word belgesini dönüştürmekle görevlendirildiğinizde, işleri nasıl düzenli tutacağınızı tam olarak biliyorsunuz!

## SSS'ler

### HTML çıktım için neden tek bir CSS dosyası kullanmalıyım?
Tek bir CSS dosyası kullanmak stillerinizin yönetimini ve bakımını kolaylaştırır. HTML'nizi daha temiz ve daha verimli hale getirir.

### Gerekirse yazı tipi yüzü CSS kurallarını ayırabilir miyim?
 Evet, ayarlayarak`SaveFontFaceCssSeparately` ile`true`yazı tipi yüzü CSS kurallarını farklı bir dosyaya ayırabilirsiniz.

### Aspose.Words for .NET'in kullanımı ücretsiz mi?
 Aspose.Words ücretsiz deneme olanağı sunuyor.[buradan indir](https://releases.aspose.com/) . Sürekli kullanım için bir lisans satın almayı düşünün[Burada](https://purchase.aspose.com/buy).

### Aspose.Words for .NET başka hangi formatlara dönüşebilir?
Aspose.Words for .NET, PDF, TXT dahil olmak üzere çeşitli formatları ve JPEG ve PNG gibi görüntü formatlarını destekler.

### Aspose.Words for .NET'te daha fazla kaynağı nerede bulabilirim?
 Şuna göz atın:[dokümantasyon](https://reference.aspose.com/words/net/) kapsamlı kılavuzlar ve API referansları için.
