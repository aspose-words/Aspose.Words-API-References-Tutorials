---
title: Ölçü Birimleri Arasında Dönüştür
linktitle: Ölçü Birimleri Arasında Dönüştür
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgede ölçüm birimleri arasında dönüşüm yapmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/convert-between-measurement-units/
---

Bu eğitimde, Aspose.Words for .NET ile ölçüm birimleri arasında dönüştürme yapmak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, farklı ölçü birimlerinde kenar boşluklarını, üst bilgi ve alt bilgi mesafelerini vb. belirlemenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi ve Oluşturucuyu Oluşturma

Bu adımda yeni bir belge oluşturacağız ve yapıcıyı başlatacağız. Aşağıdaki kodu kullanın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Ölçü birimlerini yapılandırın

Şimdi kenar boşlukları, üst bilgi ve alt bilgi mesafeleri vb. için değerleri farklı ölçü birimlerine dönüştüreceğiz. Değerleri belirli ölçü birimlerinde belirtmek için aşağıdaki kodu kullanın:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Bu kod kullanır`ConvertUtil` Aspose.Words sınıfı, belirtilen değerleri inç'e (`InchToPoint` ). Ayrıca diğer dönüştürme yöntemlerini de kullanabilirsiniz.`ConvertUtil` değerleri diğer ölçü birimlerine dönüştürmek için sınıf.

### Aspose.Words for .NET kullanarak Ölçüm Birimleri Arasında Dönüştürme için örnek kaynak kodu

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Artık Aspose.Words for .NET kullanarak bir belgede kenar boşluklarını, üst bilgi ve alt bilgi mesafelerini vb. belirtirken ölçüm birimleri arasında nasıl dönüşüm yapacağınızı öğrendiniz. Bu eğitimde verilen adım adım kılavuzu izleyerek, kendi belgelerinizde istediğiniz ölçü birimlerindeki değerleri kolayca belirtebilirsiniz.