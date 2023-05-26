---
title: Altbilgideki Metni Değiştir
linktitle: Altbilgideki Metni Değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinin alt bilgisindeki metni nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-text-in-footer/
---

Bu makalede, Aspose.Words for .NET kitaplığında Alt Bilgide Metin Değiştir işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, Word belgelerinin altbilgilerindeki belirli metni bulmanızı ve değiştirmenizi sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Belgeyi yükleyin

Alt bilgide metin değiştirmeyi kullanmaya başlamadan önce, belgeyi Aspose.Words for .NET'e yüklememiz gerekiyor. Bu, kullanılarak yapılabilir`Document` sınıf ve belge dosyası yolunu belirterek:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

## 2. Adım: Altbilgiye erişin

 Belge yüklendikten sonra, metin değiştirmeyi gerçekleştirmek için alt bilgiye erişmemiz gerekir. Örneğimizde,`HeadersFooters` üstbilgi/altbilgi koleksiyonunu almak için belgenin ilk bölümünün özelliği. Ardından, kullanarak ana altbilgiyi seçiyoruz.`HeaderFooterType.FooterPrimary` dizin:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

## 3. Adım: Arama ve değiştirme seçeneklerini yapılandırın

 Şimdi bul ve değiştir seçeneklerini bir a kullanarak yapılandıracağız.`FindReplaceOptions` nesne. Örneğimizde, ayarladık`MatchCase` ile`false` arama yaparken büyük/küçük harf durumunu yok saymak ve`FindWholeWordsOnly` ile`false` kelime parçalarının aranmasına ve değiştirilmesine izin vermek için:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

## 4. Adım: Altbilgideki metni değiştirin

 biz kullanıyoruz`Range.Replace` alt bilgide metin değiştirme gerçekleştirme yöntemi. Örneğimizde "(C) 2006 Aspose Pty Ltd." ifadesini değiştiriyoruz. "Copyright (C) 2020 by Aspose Pty Ltd." :

```csharp
footer

.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

## 5. Adım: Düzenlenen belgeyi kaydedin

 Son olarak, değiştirilmiş belgeyi kullanarak belirtilen bir dizine kaydediyoruz.`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
```

### Aspose.Words for .NET kullanarak Altbilgideki Metni Değiştirmek için örnek kaynak kodu

Aspose.Words for .NET ile altbilgi metni değiştirmenin kullanımını gösteren tam örnek kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Footer.docx");

	HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
	HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

	FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };

	footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
            
        
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Altbilgideki Metni Değiştir işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belgeyi yüklemek, alt bilgiye erişmek, arama ve değiştirme seçeneklerini yapılandırmak, metin değiştirmeyi gerçekleştirmek ve düzenlenen belgeyi kaydetmek için adım adım bir kılavuz izledik.
