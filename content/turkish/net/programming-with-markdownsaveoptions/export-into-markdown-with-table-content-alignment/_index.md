---
title: Tablo İçeriği Hizalamasıyla Markdown'a Aktarma
linktitle: Tablo İçeriği Hizalamasıyla Markdown'a Aktarma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini hizalanmış tablolarla Markdown'a nasıl aktaracağınızı öğrenin. Mükemmel Markdown tabloları için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
## giriiş

Selam! Mükemmel hizalanmış tablolarla Word belgenizi Markdown formatına nasıl aktaracağınızı hiç merak ettiniz mi? İster dokümantasyon üzerinde çalışan bir geliştirici olun, ister yalnızca Markdown'u seven biri olun, bu kılavuz tam size göre. Bunu başarmak için Aspose.Words for .NET'i kullanmanın en ince ayrıntısına kadar inceleyeceğiz. Word tablolarınızı düzgünce hizalanmış Markdown tablolarına dönüştürmeye hazır mısınız? Başlayalım!

## Önkoşullar

Kodun ayrıntılarına girmeden önce, uygulamanız gereken birkaç şey var:

1.  Aspose.Words for .NET Kütüphanesi: Aspose.Words for .NET kütüphanesine sahip olduğunuzdan emin olun. adresinden indirebilirsiniz.[Aspose Sürümler Sayfası](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Geliştirme ortamınızı ayarlayın. Visual Studio, .NET geliştirme için popüler bir seçimdir.
3. Temel C# Bilgisi: Bu dilde kod yazacağımız için C#'ı anlamak çok önemlidir.
4. Örnek Word Belgesi: Test amaçlı kullanabileceğiniz bir Word belgeniz olsun.

## Ad Alanlarını İçe Aktar

Kodlamaya başlamadan önce gerekli ad alanlarını içe aktaralım. Bunlar bize kullanacağımız Aspose.Words sınıflarına ve yöntemlerine erişim sağlayacak.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1. Adım: Document ve DocumentBuilder'ı başlatın

Öncelikle yeni bir Word belgesi oluşturmamız ve bir başlangıç başlatmamız gerekiyor.`DocumentBuilder` belgemizi oluşturmaya başlamak için nesne.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir belge oluşturun.
Document doc = new Document();

// DocumentBuilder'ı başlatın.
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Hücreleri Ekleme ve İçeriği Hizalama

Daha sonra belgemize bazı hücreler ekleyeceğiz ve bunların hizalamasını ayarlayacağız. Bu, Markdown aktarımının doğru hizalamayı korumasını sağlamak için çok önemlidir.

```csharp
// Bir hücre ekleyin ve hizalamayı sağa ayarlayın.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");

// Başka bir hücre ekleyin ve hizalamayı merkeze ayarlayın.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

## 3. Adım: Markdown Dışa Aktarımı için Tablo İçeriği Hizalamasını Ayarlayın

 Şimdi yapılandırma zamanı`MarkdownSaveOptions` Dışa aktarılan Markdown dosyasındaki tablo içeriğinin hizalamasını kontrol etmek için. Nasıl çalıştığını görmek için belgeyi farklı hizalama ayarlarıyla kaydedeceğiz.

```csharp
// MarkdownSaveOptions nesnesini oluşturun.
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    TableContentAlignment = TableContentAlignment.Left
};

// Belgeyi sola hizalayarak kaydedin.
doc.Save(dataDir + "LeftTableContentAlignment.md", saveOptions);

// Hizalamayı sağa değiştirin ve kaydedin.
saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "RightTableContentAlignment.md", saveOptions);

// Hizalamayı merkeze değiştirin ve kaydedin.
saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "CenterTableContentAlignment.md", saveOptions);
```

## 4. Adım: Otomatik Tablo İçeriği Hizalamasını Kullanın

`Auto`hizalama seçeneği, hizalamayı ilgili tablo sütunundaki ilk paragraftan alır. Tek bir tabloda karışık hizalamalarınız olduğunda bu kullanışlı olabilir.

```csharp
// Hizalamayı Otomatik olarak ayarlayın.
saveOptions.TableContentAlignment = TableContentAlignment.Auto;

// Belgeyi otomatik hizalamayla kaydedin.
doc.Save(dataDir + "AutoTableContentAlignment.md", saveOptions);
```

## Çözüm

İşte buyur! Aspose.Words for .NET kullanarak Word belgelerini hizalanmış tablolarla Markdown'a aktarmak, nasıl yapılacağını öğrendikten sonra çok kolaydır. Bu güçlü kitaplık, tablolarınızın biçimlendirmesini ve hizalamasını kontrol etmenizi kolaylaştırarak Markdown belgelerinizin tam istediğiniz gibi görünmesini sağlar. Mutlu kodlama!

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, değiştirmesine, dönüştürmesine ve dışa aktarmasına olanak tanıyan güçlü bir kitaplıktır.

### Aynı tablodaki farklı sütunlar için farklı hizalamalar ayarlayabilir miyim?
 Evet, kullanarak`Auto` hizalama seçeneğini kullanarak, her sütundaki ilk paragrafa göre farklı hizalamalara sahip olabilirsiniz.

### Aspose.Words for .NET'i kullanmak için lisansa ihtiyacım var mı?
 Evet, Aspose.Words for .NET tam işlevsellik için lisans gerektirir. Alabilirsin[geçici lisans](https://purchase.aspose.com/temporary-license/) Evrim için.

### Aspose.Words kullanarak diğer belge öğelerini Markdown'a aktarmak mümkün müdür?
Evet, Aspose.Words başlıklar, listeler ve resimler gibi çeşitli öğelerin Markdown formatına aktarılmasını destekler.

### Sorunla karşılaşırsam nereden destek alabilirim?
 adresinden destek alabilirsiniz.[Aspose.Words Destek Forumu](https://forum.aspose.com/c/words/8).
