---
title: En Boy Oranı Kilitli
linktitle: En Boy Oranı Kilitli
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir Word belgesindeki bir şeklin en boy oranını nasıl kilitleyeceğinizi veya kilidini açacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/aspect-ratio-locked/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesindeki bir şeklin en boy oranının nasıl kilitleneceği veya kilidinin açılacağı açıklanmaktadır. En boy oranını kilitleyerek, şekli yeniden boyutlandırırken şeklin orijinal oranlarını koruyabilirsiniz.

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

## 3. Adım: Bir Görüntü Şekli Ekleme
 Kullan`InsertImage` yöntemi`DocumentBuilder` Belgeye bir görüntü şekli eklemek için nesne. Görüntü dosyasının yolunu parametre olarak belirtin.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 4. Adım: En Boy Oranını Kilitleyin veya Kilidini Açın
 Yı kur`AspectRatioLocked` şeklin özelliği`true` veya`false` En boy oranını sırasıyla kilitlemek veya kilidini açmak için.

```csharp
shape.AspectRatioLocked = false; //En boy oranının kilidini açın
```

## Adım 5: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithShapes.AspectRatioLocked.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Aspose.Words for .NET kullanılarak Kilitlenen En Boy Oranı için örnek kaynak kodu 

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