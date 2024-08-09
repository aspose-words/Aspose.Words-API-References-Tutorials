---
title: Çitle çevrili kod
linktitle: Çitle çevrili kod
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgelerine çitlerle çevrili kod ve bilgi dizelerini nasıl ekleyeceğinizi öğrenin. Adım adım kılavuz dahildir. Belge biçimlendirme becerilerinizi geliştirin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/fenced-code/
---
## giriiş

Merhaba kodlayıcı arkadaşım! Bugün Aspose.Words for .NET dünyasına dalıyoruz ve Word belgelerinize bilgi dizeleri içeren çitli kod ve çitli kod ekleme sanatında ustalaşıyoruz. Word belgenizi bir tuval olarak hayal edin ve sanatçı olarak siz de deneyimli bir geliştiricinin hassasiyetiyle resim yapmak üzeresiniz. Aspose.Words ile belgelerinizi yapılandırılmış, formatlanmış kod bloklarıyla programlı olarak geliştirme gücüne sahip olur, teknik belgelerinizin profesyonellik ve netlikle parlamasını sağlarsınız.

## Önkoşullar

Eğiticiye geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

- Temel C# bilgisi: C# hakkında genel bir anlayış, kavramları hızlı bir şekilde kavramanıza yardımcı olacaktır.
-  Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olması gerekir. Henüz almadıysanız mutlaka alın[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio veya sizin için uygun olan herhangi bir C# IDE.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmanız gerekir. Bu, bir projeye başlamadan önce tüm araçlarınızı toplamaya benzer.

```csharp
using Aspose.Words;
using Aspose.Words.Style;
```

Şimdi süreci adım adım inceleyelim.

## 1. Adım: Projenizi Kurma

Word belgemizde güzel, biçimlendirilmiş kod blokları oluşturabilmemiz için önce Visual Studio'da yeni bir proje kurmamız gerekiyor.

1. Yeni Bir Proje Oluşturun: Visual Studio'yu açın ve yeni bir C# Konsol Uygulaması oluşturun.
2. Aspose.Words Referansı Ekle: Aspose.Words'ü NuGet Paket Yöneticisi aracılığıyla yükleyin. Bunu, Solution Explorer'da projenize sağ tıklayarak, "NuGet Paketlerini Yönet" seçeneğini seçip Aspose.Words'ü arayarak yapabilirsiniz.

## Adım 2: DocumentBuilder'ı başlatın

Artık projeniz ayarlandığına göre, Word belgesine içerik eklemek için ana aracımız olacak DocumentBuilder'ı başlatalım.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 3. Adım: Sınırlandırılmış Kod için Stil Oluşturun

Sınırlandırılmış kod eklemek için öncelikle bir stil oluşturmamız gerekir. Bunu kod bloğumuzun temasını ayarlamak olarak düşünün.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
fencedCode.Font.Name = "Courier New";
fencedCode.Font.Size = 10;
fencedCode.ParagraphFormat.LeftIndent = 20;
fencedCode.ParagraphFormat.RightIndent = 20;
fencedCode.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## 4. Adım: Belgeye Korumalı Kod Ekleme

Stilimiz hazır olduğundan artık belgeye çitlerle çevrili bir kod bloğu ekleyebiliriz.

```csharp
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is a fenced code block");
```

## Adım 5: Bilgi Dizesi ile Korumalı Kod için Stil Oluşturun

Bazen programlama dilini belirtmek veya kod bloğunuza ekstra bilgi eklemek isteyebilirsiniz. Bunun için bir stil oluşturalım.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
fencedCodeWithInfo.Font.Name = "Courier New";
fencedCodeWithInfo.Font.Size = 10;
fencedCodeWithInfo.ParagraphFormat.LeftIndent = 20;
fencedCodeWithInfo.ParagraphFormat.RightIndent = 20;
fencedCodeWithInfo.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Adım 6: Belgeye Bilgi Dizesi İçeren Korumalı Kod Ekleme

Şimdi bunun C# kodu olduğunu belirtmek için bilgi dizesi içeren çitlerle çevrili bir kod bloğu ekleyelim.

```csharp
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code block with info string - C#");
```

## Çözüm

Tebrikler! Aspose.Words for .NET'i kullanarak Word belgelerinize çitle çevrilmiş kod blokları ve bilgi dizeleri içeren çitle çevrilmiş kod eklediniz. Bu buzdağının sadece görünen kısmı. Aspose.Words ile belge işlemenizi otomatikleştirebilir ve yeni boyutlara taşıyabilirsiniz. Keşfetmeye ve mutlu kodlamaya devam edin!

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır.

### Aspose.Words'ü diğer programlama dilleriyle kullanabilir miyim?
Aspose.Words öncelikli olarak .NET dillerini destekler ancak Java, Python ve diğer diller için sürümler mevcuttur.

### Aspose.Words'ün kullanımı ücretsiz mi?
 Aspose.Words ticari bir üründür ancak ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/)özelliklerini keşfetmek için.

### Aspose.Words için nasıl destek alabilirim?
 Aspose topluluğundan ve geliştiricilerden destek alabilirsiniz[Burada](https://forum.aspose.com/c/words/8).

### Aspose.Words başka hangi özellikleri sunuyor?
Aspose.Words, belge dönüştürme, şablon tabanlı belge oluşturma, raporlama ve çok daha fazlasını içeren çok çeşitli özellikler sunar.