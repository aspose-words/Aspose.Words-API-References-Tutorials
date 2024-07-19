---
title: Üstbilgi Altbilgilerinin Bağlantısını Kaldır
linktitle: Üstbilgi Altbilgilerinin Bağlantısını Kaldır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki üstbilgi ve altbilgilerin bağlantısını nasıl kaldıracağınızı öğrenin. Belge manipülasyonunda ustalaşmak için ayrıntılı, adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/unlink-headers-footers/
---
## giriiş

Belge işleme dünyasında üstbilgileri ve altbilgileri tutarlı tutmak bazen zor olabilir. İster belgeleri birleştiriyor olun ister yalnızca farklı bölümler için farklı üstbilgiler ve altbilgiler arıyor olun, bunların bağlantısını nasıl kaldıracağınızı bilmek çok önemlidir. Bugün bunu Aspose.Words for .NET kullanarak nasıl başarabileceğinizi ele alacağız. Kolayca takip edebilmeniz için adım adım anlatacağız. Belge manipülasyonunda ustalaşmaya hazır mısınız? Başlayalım!

## Önkoşullar

İşin özüne dalmadan önce ihtiyacınız olacak birkaç şey var:

-  Aspose.Words for .NET Kütüphanesi: Buradan indirebilirsiniz.[Aspose sürümler sayfası](https://releases.aspose.com/words/net/).
- .NET Framework: Uyumlu bir .NET framework'ün kurulu olduğundan emin olun.
- IDE: Visual Studio veya herhangi bir .NET uyumlu Tümleşik Geliştirme Ortamı.
- Temel C# Anlayışı: C# programlama dili hakkında temel bir anlayışa ihtiyacınız olacak.

## Ad Alanlarını İçe Aktar

Başlamak için projenize gerekli ad alanlarını içe aktardığınızdan emin olun. Bu, Aspose.Words kütüphanesine ve özelliklerine erişmenizi sağlayacaktır.

```csharp
using Aspose.Words;
```

Word belgelerinizdeki üstbilgi ve altbilgilerin bağlantısını kaldırmanıza yardımcı olmak için süreci yönetilebilir adımlara ayıralım.

## 1. Adım: Projenizi Kurun

Öncelikle proje ortamınızı ayarlamanız gerekir. IDE'nizi açın ve yeni bir .NET projesi oluşturun. Daha önce indirdiğiniz Aspose.Words kütüphanesine bir referans ekleyin.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynak Belgeyi Yükleyin

Daha sonra değiştirmek istediğiniz kaynak belgeyi yüklemeniz gerekir. Bu belgenin üstbilgileri ve altbilgilerinin bağlantısı kaldırılacak.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## 3. Adım: Hedef Belgesini Yükleyin

Şimdi, hedef belgeyi, üstbilgi ve altbilgilerin bağlantısını kaldırdıktan sonra kaynak belgenin ekleneceği yere yükleyin.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 4. Adım: Üstbilgilerin ve Altbilgilerin Bağlantısını Kaldırma

 Bu adım çok önemlidir. Kaynak belgenin üstbilgileri ve altbilgileri ile hedef belgenin bağlantısını kaldırmak için,`LinkToPrevious` yöntem. Bu yöntem, üstbilgilerin ve altbilgilerin eklenen belgeye taşınmamasını sağlar.

```csharp
// Bunu durdurmak için kaynak belgedeki üstbilgi ve altbilgilerin bağlantısını kaldırın
//hedef belgenin üstbilgilerine ve altbilgilerine devam etmekten.
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Adım 5: Kaynak Belgeyi Ekleyin

 Üstbilgi ve altbilgilerin bağlantısını kaldırdıktan sonra kaynak belgeyi hedef belgeye ekleyebilirsiniz. Kullan`AppendDocument` yöntemini seçin ve içe aktarma formatı modunu şu şekilde ayarlayın:`KeepSourceFormatting` kaynak belgenin orijinal biçimlendirmesini korumak için.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 6: Son Belgeyi Kaydedin

Son olarak yeni oluşturulan belgeyi kaydedin. Bu belgede, kaynak belgenin içeriği hedef belgeye eklenecek ve üstbilgiler ile altbilgilerin bağlantısı kaldırılacaktır.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

## Çözüm

İşte buyur! Bu adımları izleyerek, kaynak belgenizdeki üstbilgi ve altbilgilerin bağlantısını başarıyla kaldırdınız ve bunu Aspose.Words for .NET kullanarak hedef belgenize eklediniz. Bu teknik, farklı bölümler için farklı üstbilgiler ve altbilgiler gerektiren karmaşık belgelerle çalışırken özellikle yararlı olabilir. Mutlu kodlama!

## SSS'ler

### Aspose.Words for .NET nedir?  
Aspose.Words for .NET, .NET uygulamalarında Word belgeleriyle çalışmak için güçlü bir kütüphanedir. Geliştiricilerin belgeleri programlı olarak oluşturmasına, değiştirmesine, dönüştürmesine ve yazdırmasına olanak tanır.

### Yalnızca belirli bölümlere ait üstbilgi ve altbilgilerin bağlantısını kaldırabilir miyim?  
 Evet, belirli bölümlere ilişkin üstbilgi ve altbilgilerin bağlantısını şuraya erişerek kaldırabilirsiniz:`HeadersFooters` İstenilen bölümün özelliği ve kullanımı`LinkToPrevious` yöntem.

### Kaynak belgenin orijinal formatını korumak mümkün mü?  
 Evet, kaynak belgeyi eklerken şunu kullanın:`ImportFormatMode.KeepSourceFormatting` Orijinal biçimlendirmeyi koruma seçeneği.

### Aspose.Words for .NET'i C#'ın yanı sıra diğer .NET dilleriyle de kullanabilir miyim?  
Kesinlikle! Aspose.Words for .NET, VB.NET ve F# da dahil olmak üzere herhangi bir .NET diliyle kullanılabilir.

### Aspose.Words for .NET için daha fazla belge ve desteği nerede bulabilirim?  
 Hakkında kapsamlı belgeler bulabilirsiniz.[Aspose.Words for .NET dokümantasyon sayfası](https://reference.aspose.com/words/net/) ve şu adreste destek mevcuttur:[Forumu aspose](https://forum.aspose.com/c/words/8).
