---
title: Css Sınıf Adı Öneki Ekle
linktitle: Css Sınıf Adı Öneki Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini HTML olarak kaydederken CSS sınıfı adı önekini nasıl ekleyeceğinizi öğrenin. Adım adım kılavuz, kod parçacıkları ve SSS'ler dahildir.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## giriiş

Hoş geldin! Aspose.Words for .NET dünyasına dalıyorsanız, sizi bir ziyafet bekliyor. Bugün Aspose.Words for .NET kullanarak bir Word belgesini HTML olarak kaydederken CSS sınıfı adı önekinin nasıl ekleneceğini inceleyeceğiz. Bu özellik, HTML dosyalarınızda sınıf adı çakışmalarını önlemek istediğinizde son derece kullanışlıdır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET: Henüz yüklemediyseniz,[buradan indir](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio veya başka herhangi bir C# IDE.
-  Bir Word Belgesi: Adlı bir belge kullanacağız`Rendering.docx`. Proje dizininize yerleştirin.

## Ad Alanlarını İçe Aktar

Öncelikle C# projenize gerekli ad alanlarının aktarıldığından emin olun. Bunları kod dosyanızın en üstüne ekleyin:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

Şimdi adım adım kılavuza geçelim!

## 1. Adım: Projenizi Kurun

CSS sınıfı adı öneki eklemeye başlamadan önce projemizi oluşturalım.

### Adım 1.1: Yeni Bir Proje Oluşturun

 Visual Studio'nuzu çalıştırın ve yeni bir Konsol Uygulaması projesi oluşturun. Buna akılda kalıcı bir şey söyle`AsposeCssPrefixExample`.

### Adım 1.2: Aspose.Words for .NET'i ekleyin

Henüz yapmadıysanız Aspose.Words for .NET'i NuGet aracılığıyla projenize ekleyin. NuGet Paket Yöneticisi Konsolunu açmanız ve çalıştırmanız yeterlidir:

```bash
Install-Package Aspose.Words
```

Harika! Artık kodlamaya başlamaya hazırız.

## 2. Adım: Belgenizi Yükleyin

Yapmamız gereken ilk şey HTML'ye dönüştürmek istediğimiz Word belgesini yüklemek.

### Adım 2.1: Belge Yolunu Tanımlayın

 Belge dizininizin yolunu ayarlayın. Bu eğitimin amacına uygun olarak, belgenizin adlı bir klasörde olduğunu varsayalım.`Documents` proje dizininizde.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### Adım 2.2: Belgeyi Yükleyin

Şimdi belgeyi Aspose.Words kullanarak yükleyelim:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: HTML Kaydetme Seçeneklerini Yapılandırın

Daha sonra, HTML kaydetme seçeneklerini bir CSS sınıfı adı öneki içerecek şekilde yapılandırmamız gerekiyor.

### Adım 3.1: HTML Kaydetme Seçenekleri Oluşturun

 Örnekleyin`HtmlSaveOptions` nesnesini seçin ve CSS stil sayfası türünü şu şekilde ayarlayın:`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### Adım 3.2: CSS Sınıfı Adı Önekini Ayarlayın

 Şimdi ayarları yapalım`CssClassNamePrefix` özelliği istediğiniz öneke ekleyin. Bu örnek için şunu kullanacağız:`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## Adım 4: Belgeyi HTML olarak kaydedin

Son olarak yapılandırılmış seçeneklerimizle belgeyi HTML dosyası olarak kaydedelim.


Çıkış HTML dosyası yolunu belirtin ve belgeyi kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## Adım 5: Çıktıyı Doğrulayın

 Projenizi çalıştırdıktan sonra şuraya gidin:`Documents` dosya. Adlı bir HTML dosyası bulmalısınız.`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . CSS sınıflarının öneke sahip olduğunu doğrulamak için bu dosyayı bir metin düzenleyicide veya tarayıcıda açın.`pfx_`.

## Çözüm

Ve işte karşınızda! Bu adımları izleyerek Aspose.Words for .NET'i kullanarak HTML çıktınıza başarıyla bir CSS sınıfı adı öneki eklediniz. Bu basit ama güçlü özellik, HTML belgelerinizde temiz ve çakışmayan stiller korumanıza yardımcı olabilir.

## SSS'ler

### Her kaydetme işlemi için farklı bir önek kullanabilir miyim?
 Evet, bir belgeyi her kaydettiğinizde ön eki değiştirerek, öneki özelleştirebilirsiniz.`CssClassNamePrefix` mülk.

### Bu yöntem satır içi CSS'yi destekliyor mu?
`CssClassNamePrefix`özellik harici CSS ile çalışır. Satır içi CSS için farklı bir yaklaşıma ihtiyacınız olacak.

### Diğer HTML kaydetme seçeneklerini nasıl ekleyebilirim?
 Çeşitli özelliklerini yapılandırabilirsiniz`HtmlSaveOptions` HTML çıktınızı özelleştirmek için. Kontrol edin[dokümantasyon](https://reference.aspose.com/words/net/) daha fazla ayrıntı için.

### HTML'yi bir akışa kaydetmek mümkün mü?
 Kesinlikle! Akış nesnesini aktararak belgeyi bir akışa kaydedebilirsiniz.`Save` Yöntem.

### Sorunla karşılaşırsam nasıl destek alabilirim?
 adresinden destek alabilirsiniz.[Forumu aspose](https://forum.aspose.com/c/words/8).