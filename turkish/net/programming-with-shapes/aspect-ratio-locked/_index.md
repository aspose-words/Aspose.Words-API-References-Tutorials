---
title: En Boy Oranı Kilitli
linktitle: En Boy Oranı Kilitli
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki bir şeklin en boy oranını nasıl kilitleyeceğinizi veya kilidini açacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/aspect-ratio-locked/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesindeki bir şeklin en boy oranının nasıl kilitleneceğini veya kilidinin nasıl açılacağını açıklar. En boy oranını kilitleyerek, yeniden boyutlandırırken şeklin orijinal oranlarını koruyabilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir Görüntü Şekli Ekleyin
 Kullan`InsertImage` yöntemi`DocumentBuilder` belgeye bir görüntü şekli eklemek için nesne. Görüntü dosyasının yolunu bir parametre olarak sağlayın.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 4. Adım: En Boy Oranını Kilitleyin veya Açın
 Yı kur`AspectRatioLocked` şeklin özelliği`true` veya`false` sırasıyla en boy oranını kilitlemek veya kilidini açmak için.

```csharp
shape.AspectRatioLocked = false; //En boy oranının kilidini aç
```

## 5. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte, belgeyi "WorkingWithShapes.AspectRatioLocked.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Aspose.Words for .NET kullanılarak Kilitli En Boy Oranı için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki bir şeklin en boy oranını başarıyla kilitlediniz veya kilidini açtınız.