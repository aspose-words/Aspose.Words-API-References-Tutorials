---
title: Satır İçi Kod
linktitle: Satır İçi Kod
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile satır içi kodu nasıl yapacağınızı öğrenin Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/inline-code/
---

Bu örnekte, satır içi kod özelliğini Aspose.Words for .NET ile nasıl kullanacağınız konusunda size yol göstereceğiz. Satır İçi Kod, bir paragraf içindeki kod parçalarını görsel olarak temsil etmek için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Satır içi kod için stil ekleyin

 Kullanarak satır içi kod için özel bir stil ekleyeceğiz.`Styles.Add` yöntemi`Document` nesne. Bu örnekte, varsayılan ters tik ile satır içi kod için "InlineCode" adlı bir stil yaratıyoruz.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## 3. Adım: Satır içi kod ekleyin

Artık "InlineCode" özel stilini kullanarak satır içi kod ekleyebiliriz. Bu örnekte, farklı sayıda ters tik içeren iki metin parçası ekliyoruz.

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
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Geri tik sayısı kaçırıldı, varsayılan olarak bir geri tik kullanılacak.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// 3 backtick olacak.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Tebrikler! Artık Aspose.Words for .NET ile satır içi kod işlevselliğini nasıl kullanacağınızı öğrendiniz.


### SSS

#### S: Satır içi kodu Aspose.Words'te nasıl kullanabilirim?

 C: Aspose.Words'te satır içi kodu kullanmak için, satır içi kod olarak biçimlendirilecek metni çevreleyen uygun etiketleri kullanabilirsiniz. Örneğin,`<code>` veya`<kbd>` satır içi kod olarak biçimlendirilecek metni çevreleyen etiket.

#### S: Aspose.Words'te satır içi kod yazı tipini veya rengini belirtmek mümkün mü?

 C: Evet, Aspose.Words'te satır içi kodun yazı tipini veya rengini belirtebilirsiniz. kullanabilirsiniz`Font.Name` Ve`Font.Color` özellikleri`Run` Satır içi kodun yazı tipini ve rengini ayarlamak için nesne. Örneğin, kullanabilirsiniz`run.Font.Name = "Courier New"` satır içi kod için yazı tipini belirtmek ve`run.Font.Color = Color.Blue`rengi belirtmek için

#### S: Satır içi kodu diğer metin öğelerini içeren bir paragrafta kullanabilir miyim?

 C: Evet, diğer metin öğelerini içeren bir paragrafta satır içi kodu kullanabilirsiniz. birden fazla oluşturabilirsiniz`Run` Paragrafın farklı bölümlerini temsil edecek nesneleri seçin, ardından yalnızca belirli bölümleri satır içi kod olarak biçimlendirmek için satır içi kod etiketlerini kullanın. Ardından bunları kullanarak paragrafa ekleyebilirsiniz.`Paragraph.AppendChild(run)` yöntem.