---
title: Word Belgesinde Yatay Kural Biçimi
linktitle: Word Belgesinde Yatay Kural Biçimi
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerinde yatay kuralları nasıl biçimlendireceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/horizontal-rule-format/
---
Bu kapsamlı örnekte, Aspose.Words for .NET kullanarak bir Word belgesindeki yatay bir kuralı nasıl biçimlendireceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, bir yatay kuralın hizalama, genişlik, yükseklik, renk ve diğer özelliklerini özelleştirebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Bir DocumentBuilder Oluşturun ve Yatay Bir Kural Ekleyin
Başlamak için bir DocumentBuilder nesnesi oluşturun ve InsertHorizontalRule yöntemini kullanarak yatay bir kural ekleyin:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## 2. Adım: Yatay Kural Biçimine Erişin
Ardından, biçimlendirme seçeneklerini almak için Shape nesnesinin HorizontalRuleFormat özelliğine erişin:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## 3. Adım: Biçimlendirme Seçeneklerini Özelleştirin
Artık yatay kural için çeşitli biçimlendirme seçeneklerini özelleştirebilirsiniz. Örneğin, hizalamayı, genişliği, yüksekliği, rengi ve gölgelemeyi ayarlayabilirsiniz:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## 4. Adım: Belgeyi Kaydedin
Yatay kuralı biçimlendirdikten sonra, Belge nesnesinin Kaydet yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Aspose.Words for .NET kullanan Yatay Kural Biçimi için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yatay bir kuralı biçimlendirmek için eksiksiz kaynak kodu burada:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesinde yatay bir kuralı nasıl biçimlendireceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, artık belgenizin görsel düzenini geliştirmek için yatay kuralların görünümünü özelleştirebilirsiniz.

Yatay kurallarınız için istediğiniz stili ve efekti elde etmek için farklı biçimlendirme seçeneklerini deneyin.

### Word belgesinde yatay kural formatı için SSS

#### S: Yatay kurala farklı renkler uygulayabilir miyim?

C: Kesinlikle! Aspose.Words for .NET ile Color özelliğini istediğiniz renk değerine ayarlayarak yatay kuralın rengini kolayca özelleştirebilirsiniz. Bu, yatay kuralı belgenizin genel tasarımıyla eşleştirmenizi sağlar.

#### S: Yatay kuralın genişliğini ve yüksekliğini ayarlamak mümkün mü?

C: Evet, yatay kuralın genişliği ve yüksekliği üzerinde tam kontrole sahipsiniz. WidthPercent ve Height özelliklerini değiştirerek yatay kural için istediğiniz ölçüleri elde edebilirsiniz.

#### S: Belgedeki yatay kuralın hizalamasını değiştirebilir miyim?

C: Kesinlikle! Aspose.Words for .NET, Hizalama özelliğini kullanarak yatay kuralın hizalamasını belirlemenizi sağlar. Orta, Sol, Sağ ve Yaslanmış gibi çeşitli seçenekler arasından seçim yapabilirsiniz.

#### S: Yatay kurala gölgelendirme veya arka plan rengi uygulayabilir miyim?

C: Evet, yatay kurala gölgelendirme veya arka plan rengi ekleyebilirsiniz. NoShade özelliği varsayılan olarak true olarak ayarlanmıştır, ancak siz bunu false olarak ayarlayabilir ve uygun yöntemleri kullanarak gölgelemeyi tanımlayabilirsiniz.

#### S: Tek bir belgeye birden çok yatay kural ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET'i kullanarak bir Word belgesine birden fazla yatay kural ekleyebilirsiniz. Gerektiği kadar yatay kural eklemek için eğitimdeki adımları gerektiği kadar tekrarlamanız yeterlidir.