---
title: Dikey Ankraj
linktitle: Dikey Ankraj
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'teki dikey bağlantı özelliğini kullanarak bir şekli belge içinde dikey olarak nasıl konumlandıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/vertical-anchor/
---

Bu eğitimde Aspose.Words for .NET'te bir şeklin belge içinde dikey olarak konumlandırılması için dikey bağlantı özelliğinin nasıl kullanılacağı açıklanmaktadır. Bir şeklin dikey bağlantı özelliğini ayarlayarak, metne veya sayfaya göre dikey hizalamasını kontrol edebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmaya itiraz edin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Şekil Ekleme ve Yapılandırma
 kullanarak belgeye bir şekil ekleyin.`InsertShape` yöntemi`DocumentBuilder` nesne. Şekil için istediğiniz boyutları ayarlayın.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Adım 4: Dikey Bağlantıyı Ayarlayın
Şeklin dikey hizalamasını kontrol etmek için şeklin dikey bağlantı özelliğini ayarlayın. Bu örnekte, şekli metnin veya sayfanın altına sabitlemek için onu "Alt" olarak ayarladık.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Adım 5: Şekle İçerik Ekleme
 Kullan`MoveTo` yöntemi`DocumentBuilder` İmleci şeklin ilk paragrafına taşımak için nesne. Daha sonra şunu kullanın:`Write` Şekle içerik ekleme yöntemi.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Adım 6: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save`yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.VerticalAnchor.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Aspose.Words for .NET kullanan Dikey Bağlantı için örnek kaynak kodu 

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

Bu kadar! Bir şekli bir belge içinde dikey olarak konumlandırmak için Aspose.Words for .NET'teki dikey bağlantı özelliğini başarıyla kullandınız.