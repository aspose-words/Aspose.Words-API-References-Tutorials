---
title: Göreli Yatay veya Dikey Konumu Ayarla
linktitle: Göreli Yatay veya Dikey Konumu Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET kullanarak Word belgelerindeki tablolar için göreceli yatay ve dikey konumların nasıl ayarlanacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---
## giriiş

Hiç Word belgelerinizde tabloları tam istediğiniz gibi nasıl konumlandıracağınız konusunda takılıp kaldığınızı hissettiniz mi? Yalnız değilsin. İster profesyonel bir rapor ister şık bir broşür oluşturuyor olun, masaları hizalamak büyük bir fark yaratabilir. İşte Aspose.Words for .NET'in kullanışlı olduğu yer burasıdır. Bu eğitim, Word belgelerinizdeki tablolar için göreceli yatay veya dikey konumların nasıl ayarlanacağı konusunda size adım adım rehberlik edecektir. Hadi dalalım!

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET: Henüz yapmadıysanız indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya herhangi bir .NET uyumlu IDE.
3. Temel C# Bilgisi: Bu eğitimde C# programlamanın temellerine aşina olduğunuz varsayılmaktadır.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmanız gerekir. Bu, Aspose.Words işlevlerine erişim için gereklidir.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## 1. Adım: Belgenizi Yükleyin

Başlamak için Word belgenizi programa yüklemeniz gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Bu kod parçacığı, belge dizininizin yolunu ayarlar ve üzerinde çalışmak istediğiniz belirli belgeyi yükler. Yükleme sorunlarını önlemek için belge yolunuzun doğru olduğundan emin olun.

## Adım 2: Tabloya Erişin

Daha sonra belge içindeki tabloya erişmemiz gerekiyor. Genellikle gövde bölümündeki ilk tabloyla çalışmak istersiniz.

```csharp
Table table = doc.FirstSection.Body.Tables[0];
```

Bu kod satırı belgenin gövdesinden ilk tabloyu getirir. Belgenizde birden fazla tablo varsa dizini buna göre ayarlayabilirsiniz.

## Adım 3: Yatay Konumu Ayarlayın

Şimdi tablonun yatay konumunu belirli bir öğeye göre ayarlayalım. Bu örnekte onu sütuna göre konumlandıracağız.

```csharp
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
```

 Ayarlayarak`HorizontalAnchor` ile`RelativeHorizontalPosition.Column`, tabloya kendisini bulunduğu sütuna göre yatay olarak hizalamasını söylüyorsunuz.

## Adım 4: Dikey Konumu Ayarlayın

Yatay konumlandırmaya benzer şekilde dikey konumu da ayarlayabilirsiniz. Burada onu sayfaya göre konumlandırıyoruz.

```csharp
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 ayarlamak`VerticalAnchor` ile`RelativeVerticalPosition.Page` tablonun sayfaya göre dikey olarak hizalanmasını sağlar.

## Adım 5: Belgenizi Kaydedin

Son olarak değişikliklerinizi yeni bir belgeye kaydedin. Bu, değişikliklerinizin korunduğundan emin olmak için çok önemli bir adımdır.

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Bu komut, değiştirilen belgeyi yeni bir adla kaydederek orijinal dosyanızın üzerine yazmamanızı sağlar.

## Çözüm

İşte buyur! Aspose.Words for .NET'i kullanarak Word belgesindeki bir tablonun göreceli yatay ve dikey konumlarını başarıyla ayarladınız. Bu yeni keşfedilen beceriyle belgelerinizin düzenini ve okunabilirliğini geliştirebilir, daha profesyonel ve gösterişli görünmelerini sağlayabilirsiniz. Farklı pozisyonları denemeye devam edin ve ihtiyaçlarınıza en uygun olanı görün.

## SSS'ler

### Tabloları diğer öğelere göre konumlandırabilir miyim?  
Evet, Aspose.Words tabloları kenar boşlukları, sayfalar, sütunlar ve daha fazlası gibi çeşitli öğelere göre konumlandırmanıza olanak tanır.

### Aspose.Words for .NET'i kullanmak için lisansa ihtiyacım var mı?  
 Evet, lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy) veya geçici lisans alın[Burada](https://purchase.aspose.com/temporary-license/).

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?  
 Kesinlikle! Ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Words'ü diğer programlama dilleriyle kullanabilir miyim?  
Aspose.Words öncelikli olarak .NET için tasarlanmıştır ancak Java, Python ve diğer platformlar için versiyonları mevcuttur.

### Daha ayrıntılı belgeleri nerede bulabilirim?  
Daha ayrıntılı bilgi için Aspose.Words belgelerine göz atın[Burada](https://reference.aspose.com/words/net/).