---
title: Farklı Sayfa Düzeni
linktitle: Farklı Sayfa Düzeni
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken farklı sayfa yapılandırmalarını nasıl ayarlayacağınızı öğrenin. Adım adım kılavuz dahildir.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/different-page-setup/
---
## giriiş

Selam! Aspose.Words for .NET ile belge manipülasyonunun büyüleyici dünyasına dalmaya hazır mısınız? Bugün oldukça güzel bir şeyle uğraşıyoruz: Word belgelerini birleştirirken farklı sayfa düzenleri ayarlamak. İster raporları birleştiriyor olun, ister bir roman hazırlayın, ister sadece eğlence olsun diye belgelerle uğraşıyor olun, bu kılavuz size adım adım yol gösterecektir. Hadi başlayalım!

## Önkoşullar

Ellerimizi kirletmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olduğundan emin olun. Yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
2. .NET Framework: Aspose.Words for .NET'i destekleyen herhangi bir sürüm.
3. Geliştirme Ortamı: Visual Studio veya herhangi bir .NET uyumlu IDE.
4. Temel C# Bilgisi: Sözdizimi ve yapıyı anlamak için yalnızca temel bilgiler.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını C# projenize aktaralım. Bu ad alanları Aspose.Words'ün özelliklerine erişim için çok önemlidir.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Words.Tables;
```

Neyse gelelim konunun özüne. Tüm süreci takip edilmesi kolay adımlara ayıracağız.

## 1. Adım: Projenizi Kurun

### Adım 1.1: Yeni Bir Proje Oluşturun

Visual Studio'yu çalıştırın ve yeni bir C# Konsol Uygulaması oluşturun. "DifferentPageSetupExample" gibi harika bir ad verin.

### Adım 1.2: Aspose.Words Referansını Ekleyin

Aspose.Words'ü kullanmak için projenize eklemeniz gerekir. Henüz yapmadıysanız Aspose.Words for .NET paketini indirin. NuGet Paket Yöneticisi aracılığıyla aşağıdaki komutla yükleyebilirsiniz:

```bash
Install-Package Aspose.Words
```

## Adım 2: Belgeleri Yükleyin

 Şimdi birleştirmek istediğimiz belgeleri yükleyelim. Bu örnek için iki Word belgesine ihtiyacınız olacak:`Document source.docx`Ve`Northwind traders.docx`. Bu dosyaların proje dizininizde olduğundan emin olun.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: Kaynak Belge için Sayfa Yapısını Yapılandırma

Kaynak belgenin sayfa düzeninin hedef belgeyle eşleştiğinden emin olmamız gerekir. Sorunsuz bir birleştirme için bu adım çok önemlidir.

### Adım 3.1: Hedef Belgesinden Sonra Devam Edin

Kaynak belgeyi, hedef belgeden hemen sonra devam edecek şekilde ayarlayın.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

### Adım 3.2: Sayfa Numaralandırmayı Yeniden Başlatın

Sayfa numaralandırmasını kaynak belgenin başlangıcından yeniden başlatın.

```csharp
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
```

## 4. Adım: Sayfa Yapısı Ayarlarını Eşleştirin

Düzen tutarsızlıklarını önlemek için kaynak belgenin ilk bölümünün sayfa düzeni ayarlarının hedef belgenin son bölümününkilerle eşleştiğinden emin olun.

```csharp
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## 5. Adım: Paragraf Biçimlendirmesini Ayarlayın

Sorunsuz bir akış sağlamak için kaynak belgedeki paragraf formatını ayarlamamız gerekir.

 Kaynak belgedeki tüm paragrafları yineleyin ve`KeepWithNext` mülk.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Adım 6: Kaynak Belgeyi Ekleyin

Son olarak, orijinal biçimlendirmenin korunduğundan emin olarak kaynak belgeyi hedef belgeye ekleyin.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 7: Birleştirilmiş Belgeyi Kaydedin

Şimdi güzelce birleştirilmiş belgenizi kaydedin.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak farklı sayfa düzenlerine sahip iki Word belgesini birleştirdiniz. Bu güçlü kitaplık, belgeleri programlı olarak düzenlemeyi son derece kolaylaştırır. İster karmaşık raporlar oluşturuyor olun, ister kitapları bir araya getiriyor olun, ister çok bölümlü belgeleri yönetiyor olun, Aspose.Words arkanızdadır.

## SSS'ler

### Bu yöntemi ikiden fazla belge için kullanabilir miyim?
Kesinlikle! Birleştirmek istediğiniz her ek belge için adımları tekrarlamanız yeterlidir.

### Belgelerimin kenar boşlukları farklıysa ne olur?
Sayfa genişliğini, yüksekliğini ve yönünü nasıl eşleştirdiğimize benzer şekilde kenar boşluğu ayarlarını da eşleştirebilirsiniz.

### Aspose.Words .NET Core ile uyumlu mu?
Evet, Aspose.Words for .NET, .NET Core ile tamamen uyumludur.

### Her iki belgedeki stilleri de koruyabilir miyim?
 Evet,`ImportFormatMode.KeepSourceFormatting` seçeneği kaynak belgedeki stillerin korunmasını sağlar.

### Aspose.Words ile ilgili nereden daha fazla yardım alabilirim?
 Şuna göz atın:[Aspose.Words belgeleri](https://reference.aspose.com/words/net/) veya onları ziyaret edin[destek forumu](https://forum.aspose.com/c/words/8) Daha fazla yardım için.
