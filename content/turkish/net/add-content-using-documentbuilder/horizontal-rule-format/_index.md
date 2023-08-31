---
title: Word Belgesinde Yatay Kural Formatı
linktitle: Word Belgesinde Yatay Kural Formatı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki yatay kuralların nasıl formatlanacağını öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/horizontal-rule-format/
---
Bu kapsamlı örnekte, Aspose.Words for .NET kullanarak bir Word belgesinde yatay bir kuralın nasıl formatlanacağını öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda yatay bir kuralın hizalamasını, genişliğini, yüksekliğini, rengini ve diğer özelliklerini özelleştirebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## Adım 1: DocumentBuilder Oluşturun ve Yatay Kural Ekleyin
Başlamak için bir DocumentBuilder nesnesi oluşturun ve yatay bir kural eklemek için InsertHorizontalRule yöntemini kullanın:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Adım 2: Yatay Kural Formatına Erişin
Daha sonra, biçimlendirme seçeneklerini almak için Shape nesnesinin HorizontalRuleFormat özelliğine erişin:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## 3. Adım: Biçimlendirme Seçeneklerini Özelleştirin
Artık yatay kural için çeşitli biçimlendirme seçeneklerini özelleştirebilirsiniz. Örneğin hizalamayı, genişliği, yüksekliği, rengi ve gölgeyi ayarlayabilirsiniz:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Adım 4: Belgeyi Kaydedin
Yatay kuralı biçimlendirdikten sonra, Belge nesnesinin Kaydet yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Aspose.Words for .NET kullanılarak Yatay Kural Formatı için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yatay bir kuralı biçimlendirmek için tam kaynak kodu:

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
Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesinde yatay bir kuralın nasıl biçimlendirileceğini başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve verilen kaynak kodunu kullanarak, artık belgenizin görsel düzenini geliştirmek için yatay kuralların görünümünü özelleştirebilirsiniz.

Yatay kurallarınızda istediğiniz stili ve efekti elde etmek için farklı biçimlendirme seçeneklerini deneyin.

### Word belgesinde yatay kural formatı için SSS

#### S: Yatay cetvele farklı renkler uygulayabilir miyim?

C: Kesinlikle! Aspose.Words for .NET ile Color özelliğini istediğiniz renk değerine ayarlayarak yatay kuralın rengini kolayca özelleştirebilirsiniz. Bu, yatay kuralı belgenizin genel tasarımıyla eşleştirmenize olanak tanır.

#### S: Yatay cetvelin genişliğini ve yüksekliğini ayarlamak mümkün müdür?

C: Evet, yatay cetvelin genişliği ve yüksekliği üzerinde tam kontrole sahipsiniz. WidthPercent ve Height özelliklerini değiştirerek yatay kural için istediğiniz boyutları elde edebilirsiniz.

#### S: Belgedeki yatay kuralın hizalamasını değiştirebilir miyim?

C: Kesinlikle! Aspose.Words for .NET, Hizalama özelliğini kullanarak yatay kuralın hizalamasını belirtmenize olanak tanır. Orta, Sol, Sağ ve Yaslanmış gibi çeşitli seçenekler arasından seçim yapabilirsiniz.

#### S: Yatay çizgiye gölgeleme veya arka plan rengi uygulayabilir miyim?

C: Evet, yatay kurala gölgeleme veya arka plan rengi ekleyebilirsiniz. Varsayılan olarak NoShade özelliği true değerine ayarlanmıştır ancak bunu false değerine ayarlayabilir ve uygun yöntemleri kullanarak gölgelendirmeyi tanımlayabilirsiniz.

#### S: Tek bir belgeye birden fazla yatay kural ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET'i kullanarak bir Word belgesine birden fazla yatay kural ekleyebilirsiniz. İstediğiniz kadar yatay kural eklemek için eğitimdeki adımları gerektiği kadar tekrarlayın.