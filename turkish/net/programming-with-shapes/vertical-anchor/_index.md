---
title: Dikey Çapa
linktitle: Dikey Çapa
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'teki dikey bağlantı özelliğini kullanarak bir şekli bir belge içinde dikey olarak konumlandırmayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/vertical-anchor/
---

Bu öğretici, bir şekli belge içinde dikey olarak konumlandırmak için Aspose.Words for .NET'teki dikey bağlantı özelliğinin nasıl kullanılacağını açıklar. Bir şeklin dikey bağlantı özelliğini ayarlayarak, metne veya sayfaya göre dikey hizalamasını kontrol edebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir Şekil Ekleyin ve Yapılandırın
 kullanarak belgeye bir şekil ekleyin.`InsertShape` yöntemi`DocumentBuilder` nesne. Şekil için istenen boyutları ayarlayın.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Adım 4: Dikey Bağlantıyı Ayarlayın
Dikey hizalamasını kontrol etmek için şeklin dikey bağlantı özelliğini ayarlayın. Bu örnekte, şekli metnin veya sayfanın altına tutturmak için "Alt" olarak ayarladık.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Adım 5: Şekle İçerik Ekleyin
 Kullan`MoveTo` yöntemi`DocumentBuilder` İmleci şeklin ilk paragrafına taşımak için nesne. Ardından,`Write` şekle içerik ekleme yöntemi.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## 6. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.VerticalAnchor.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Aspose.Words for .NET kullanan Vertical Anchor için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Bu kadar! Bir şekli belge içinde dikey olarak konumlandırmak için Aspose.Words for .NET'teki dikey bağlantı özelliğini başarıyla kullandınız.