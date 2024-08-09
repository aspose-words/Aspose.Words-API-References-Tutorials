---
title: Word Belgesinde Yatay Kural Formatı
linktitle: Word Belgesinde Yatay Kural Formatı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerine özelleştirilebilir yatay kuralların nasıl eklendiğini öğrenin. Belge otomasyonunuzu geliştirin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/horizontal-rule-format/
---
## giriiş

.NET geliştirme alanında, Word belgelerini programlı olarak değiştirmek ve biçimlendirmek göz korkutucu bir görev olabilir. Neyse ki Aspose.Words for .NET, geliştiricilerin belge oluşturma, düzenleme ve yönetimi kolaylıkla otomatikleştirmesine olanak tanıyan güçlü bir çözüm sunuyor. Bu makale temel özelliklerden birini ele alıyor: Word belgelerine yatay kurallar eklemek. İster deneyimli bir geliştirici olun ister Aspose.Words'e yeni başlıyor olun, bu yeteneğe hakim olmak belge oluşturma sürecinizi geliştirecektir.

## Önkoşullar

Aspose.Words for .NET'i kullanarak yatay kuralları uygulamaya başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Visual Studio: .NET geliştirme için Visual Studio IDE'yi yükleyin.
- Aspose.Words for .NET: Aspose.Words for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/words/net/).
- Temel C# Bilgisi: C# programlama dilinin temellerine aşinalık.
-  DocumentBuilder Sınıfı: Anlaşılması`DocumentBuilder` Aspose.Words'te belge işleme için sınıf.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını C# projenize aktarın:

```csharp
using Aspose.Words;
using System.Drawing;
```

Bu ad alanları, belge işleme için Aspose.Words sınıflarına ve renklerin işlenmesi için standart .NET sınıflarına erişim sağlar.

Aspose.Words for .NET kullanarak bir Word belgesine yatay kural ekleme sürecini kapsamlı adımlara ayıralım:

## Adım 1: DocumentBuilder'ı Başlatın ve Dizini Ayarlayın

 İlk olarak, bir başlat`DocumentBuilder` nesneyi seçin ve belgenin kaydedileceği dizin yolunu ayarlayın.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
DocumentBuilder builder = new DocumentBuilder();
```

## Adım 2: Yatay Cetvel Ekle

 Kullanın`InsertHorizontalRule()` yöntemi`DocumentBuilder` Yatay bir kural eklemek için sınıf.

```csharp
Shape shape = builder.InsertHorizontalRule();
```

## 3. Adım: Yatay Kural Formatını Özelleştirin

 Erişim`HorizontalRuleFormat` Yatay kuralın görünümünü özelleştirmek için eklenen şeklin özelliği.

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

- Hizalama: Yatay kuralın hizalamasını belirtir (`HorizontalRuleAlignment.Center` bu örnekte).
- WidthPercent: Yatay kuralın genişliğini sayfa genişliğinin yüzdesi olarak ayarlar (bu örnekte %70).
- Yükseklik: Yatay kuralın yüksekliğini nokta cinsinden tanımlar (bu örnekte 3 nokta).
- Renk: Yatay kuralın rengini ayarlar (`Color.Blue` bu örnekte).
- NoShade: Yatay kuralın gölgesinin olup olmayacağını belirtir (`true` bu örnekte).

## Adım 4: Belgeyi Kaydet

 Son olarak, değiştirilen belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
builder.Document.Save(dataDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

## Çözüm

Aspose.Words for .NET kullanarak Word belgelerine yatay kurallar ekleme konusunda uzmanlaşmak, belge otomasyon yeteneklerinizi geliştirir. Aspose.Words'ün esnekliğinden ve gücünden yararlanan geliştiriciler, belge oluşturma ve biçimlendirme süreçlerini verimli bir şekilde düzenleyebilir.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, .NET uygulamalarında Word belgeleriyle programlı olarak çalışmak için güçlü bir kütüphanedir.

### Aspose.Words for .NET'i nasıl indirebilirim?
 Aspose.Words for .NET'i şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/words/net/).

### Aspose.Words'te yatay kuralların görünümünü özelleştirebilir miyim?
Evet, Aspose.Words'ü kullanarak yatay kuralların hizalaması, genişliği, yüksekliği, rengi ve gölgelenmesi gibi çeşitli özellikleri özelleştirebilirsiniz.

### Aspose.Words kurumsal düzeyde belge işlemeye uygun mu?
Evet, Aspose.Words, güçlü belge işleme yetenekleri nedeniyle kurumsal ortamlarda yaygın olarak kullanılmaktadır.

### Aspose.Words for .NET için nereden destek alabilirim?
 Destek ve topluluk katılımı için şu adresi ziyaret edin:[Aspose.Words forumu](https://forum.aspose.com/c/words/8).
