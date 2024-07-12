---
title: Satır İçi Kod
linktitle: Satır İçi Kod
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile satır içi kodun nasıl yazılacağını öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/inline-code/
---

Bu örnekte, Aspose.Words for .NET ile satır içi kod özelliğinin nasıl kullanılacağı konusunda size yol göstereceğiz. Satır İçi Kod, bir paragraf içindeki kod parçalarını görsel olarak temsil etmek için kullanılır.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Satır içi kod için stil ekleyin

 Satır içi kod için özel bir stil ekleyeceğiz.`Styles.Add` yöntemi`Document` nesne. Bu örnekte, satır içi kod için varsayılan geri işaretli "InlineCode" adlı bir stil oluşturuyoruz.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## 3. Adım: Satır içi kod ekleyin

Artık "InlineCode" özel stilini kullanarak satır içi kod ekleyebiliriz. Bu örnekte, farklı sayıda geri tıklama içeren iki metin parçası ekliyoruz.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Aspose.Words for .NET ile Satır İçi Kod için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Geri tıklama sayısı atlanır, varsayılan olarak bir geri tıklama kullanılacaktır.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// 3 geri tepme olacak.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Tebrikler! Artık Aspose.Words for .NET ile satır içi kod işlevini nasıl kullanacağınızı öğrendiniz.


### SSS'ler

#### S: Aspose.Words'te satır içi kodu nasıl kullanabilirim?

 C: Aspose.Words'te satır içi kod kullanmak için satır içi kod olarak formatlanacak metni çevreleyecek uygun etiketleri kullanabilirsiniz. Örneğin, şunları kullanabilirsiniz:`<code>` veya`<kbd>` Satır içi kod olarak biçimlendirilecek metni çevreleyen etiket.

#### S: Aspose.Words'te satır içi kod yazı tipini veya rengini belirtmek mümkün mü?

 C: Evet, Aspose.Words'te satır içi kodun yazı tipini veya rengini belirleyebilirsiniz. Şunu kullanabilirsiniz:`Font.Name`Ve`Font.Color` özellikleri`Run` Satır içi kodun yazı tipini ve rengini ayarlamak için nesne. Örneğin, kullanabilirsiniz`run.Font.Name = "Courier New"` satır içi kod için yazı tipini belirtmek ve`run.Font.Color = Color.Blue`Rengi belirtmek için.

#### S: Satır içi kodu başka metin öğeleri içeren bir paragrafta kullanabilir miyim?

 C: Evet, satır içi kodu diğer metin öğelerini içeren bir paragrafta kullanabilirsiniz. Birden fazla oluşturabilirsiniz`Run` paragrafın farklı bölümlerini temsil edecek nesneler kullanın, ardından yalnızca belirli bölümleri satır içi kod olarak biçimlendirmek için satır içi kod etiketlerini kullanın. Daha sonra bunları kullanarak paragrafa ekleyebilirsiniz.`Paragraph.AppendChild(run)` yöntem.