---
title: İmleç Konumu
linktitle: İmleç Konumu
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET Adım adım kılavuzunu kullanarak bir Word belgesinde imleç konumunu nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/cursor-position/
---

Bu adım adım örnekte, Aspose.Words for .NET kullanarak bir Word belgesinde imleç konumunu öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, imlecin belgede konumlandırıldığı geçerli düğümü ve paragrafı alabileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Geçerli Düğüme ve Paragrafa Erişin
Ardından, imlecin konumlandırıldığı geçerli düğümü ve paragrafı alın. Bu, DocumentBuilder sınıfının CurrentNode ve CurrentParagraph özellikleri kullanılarak elde edilebilir:

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## 3. Adım: İmleç Konum Bilgisini Alın
Artık imlecin konumu hakkında bilgi alabilirsiniz. Aşağıdaki kod parçacığında, geçerli paragrafın metnini yazdırıyoruz:

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### Aspose.Words for .NET kullanan İmleç Konumu için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak imleç konumunu anlamak için eksiksiz kaynak kodu burada:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesinde imleç konumuyla nasıl çalışacağınızı başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak, artık belgede imlecin konumlandırıldığı geçerli düğümü ve paragrafı alabilirsiniz.

İmleç konumunu anlamak, belge içeriğini imleç konumuna göre değiştirmek veya özel düzenleme özelliklerini uygulamak gibi çeşitli senaryolar için yararlıdır.

