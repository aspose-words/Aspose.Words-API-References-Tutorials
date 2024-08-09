---
title: Metin Giriş Formu Alanını Metin Olarak Dışa Aktar
linktitle: Metin Giriş Formu Alanını Metin Olarak Dışa Aktar
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı, adım adım kılavuzla Aspose.Words for .NET kullanarak metin girişi form alanlarını düz metin olarak nasıl dışa aktaracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## giriiş

Aspose.Words for .NET dünyasına mı dalıyorsunuz? Harika seçim! Bir metin giriş formu alanını metin olarak nasıl dışa aktaracağınızı öğrenmek istiyorsanız doğru yerdesiniz. İster yeni başlıyor olun ister becerilerinizi geliştiriyor olun, bu kılavuz bilmeniz gereken her şeyde size yol gösterecektir. Haydi başlayalım, olur mu?

## Önkoşullar

İşin özüne dalmadan önce, sorunsuz bir şekilde takip etmeniz gereken her şeye sahip olduğunuzdan emin olalım:

-  Aspose.Words for .NET: En son sürümü şuradan indirip yükleyin:[Burada](https://releases.aspose.com/words/net/).
- IDE: Visual Studio veya herhangi bir C# geliştirme ortamı.
- Temel C# Bilgisi: Temel C# sözdizimi ve nesne yönelimli programlama kavramlarının anlaşılması.
- Belge: Örnek bir Word belgesi (`Rendering.docx`) metin girişi form alanları ile.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmanız gerekir. Bunlar her şeyin kusursuz çalışmasını sağlayan yapı taşları gibidir.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

Pekala, artık ad alanlarımızı hazırladığımıza göre harekete geçelim!

## Adım 1: Projeyi Kurun

Koda geçmeden önce projemizin doğru kurulduğundan emin olalım.

## Proje Oluşturma

1. Visual Studio'yu açın: Visual Studio'yu veya tercih ettiğiniz C# geliştirme ortamını açarak başlayın.
2.  Yeni Bir Proje Oluşturun: Şuraya gidin:`File > New > Project` . Seçme`Console App (.NET Core)` veya başka herhangi bir ilgili proje türü.
3.  Projenize Ad Verin: Projenize anlamlı bir ad verin;`AsposeWordsExportExample`.

## Aspose.Words'ü Eklemek

1.  NuGet Paketlerini Yönetin: Çözüm Gezgini'nde projenize sağ tıklayın ve`Manage NuGet Packages`.
2.  Aspose.Words'ü arayın: NuGet Paket Yöneticisi'nde şunu arayın:`Aspose.Words`.
3.  Aspose.Words'ü yükleyin: Tıklayın`Install` Aspose.Words kütüphanesini projenize eklemek için.

## Adım 2: Word Belgesini Yükleyin

Artık projemiz kurulduğuna göre metin giriş form alanlarını içeren Word belgesini yükleyelim.

1. Belge Dizinini Belirtin: Belgenizin saklandığı dizinin yolunu tanımlayın.
2.  Belgeyi Yükleyin: Kullanın`Document` Word belgenizi yüklemek için sınıf.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Dışa Aktarma Dizinini Hazırlayın

Export yapmadan önce ihracat dizinimizin hazır olduğundan emin olalım. Burası HTML dosyamızın ve görsellerimizin kaydedileceği yerdir.

1. Dışa Aktarma Dizinini Tanımlayın: Dışa aktarılan dosyaların kaydedileceği yolu belirtin.
2. Dizini Kontrol Edin ve Temizleyin: Dizinin var olduğundan ve boş olduğundan emin olun.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## 4. Adım: Kaydetme Seçeneklerini Yapılandırın

İşte sihrin gerçekleştiği yer burası. Metin giriş formu alanını düz metin olarak dışa aktarmak için kaydetme seçeneklerimizi ayarlamamız gerekiyor.

1.  Kaydetme Seçenekleri Oluşturun: Yeni bir başlangıç değeri oluşturun`HtmlSaveOptions` nesne.
2.  Metni Dışa Aktarma Seçeneğini Ayarla:`ExportTextInputFormFieldAsText`mülkiyet`true`.
3. Görüntüler Klasörünü Ayarla: Görüntülerin kaydedileceği klasörü tanımlayın.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## Adım 5: Belgeyi HTML olarak kaydedin

Son olarak, yapılandırılmış kaydetme seçeneklerimizi kullanarak Word belgesini HTML dosyası olarak kaydedelim.

1. Çıkış Yolunu Tanımlayın: HTML dosyasının kaydedileceği yolu belirtin.
2.  Belgeyi Kaydet: Kullan`Save` yöntemi`Document`Belgeyi dışa aktarmak için sınıf.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir metin giriş formu alanını başarıyla düz metin olarak dışa aktardınız. Bu kılavuz size bu görevi başarmanız için açık ve adım adım bir yaklaşım sunmuş olmalıdır. Unutmayın, pratik mükemmelleştirir; bu nedenle Aspose.Words ile başka neler yapabileceğinizi görmek için farklı seçenekler ve ayarlarla denemeler yapmaya devam edin.

## SSS'ler

### Aynı yöntemi kullanarak diğer form alanı türlerini dışa aktarabilir miyim?

 Evet, form alanının farklı özelliklerini yapılandırarak diğer form alanı türlerini dışa aktarabilirsiniz.`HtmlSaveOptions` sınıf.

### Belgemde resimler varsa ne olur?

 Resimler belirtilen resimler klasörüne kaydedilecektir. ayarladığınızdan emin olun.`ImagesFolder` içindeki mülk`HtmlSaveOptions`.

### Aspose.Words için lisansa ihtiyacım var mı?

 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/) veya bir lisans satın alın[Burada](https://purchase.aspose.com/buy).

### Dışa aktarılan HTML'yi özelleştirebilir miyim?

 Kesinlikle! Aspose.Words, HTML çıktısını özelleştirmek için çeşitli seçenekler sunar. Şuraya bakın:[dokümantasyon](https://reference.aspose.com/words/net/) daha fazla ayrıntı için.

### Aspose.Words .NET Core ile uyumlu mu?

Evet, Aspose.Words .NET Core, .NET Framework ve diğer .NET platformlarıyla uyumludur.
