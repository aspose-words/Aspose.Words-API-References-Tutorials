---
title: Dize ile Değiştir
linktitle: Dize ile Değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki metni bir dizeyle nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-with-string/
---

Bu makalede, Aspose.Words for .NET kitaplığında replace with String işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir Word belgesindeki belirli bir karakter dizisine dayalı olarak metin değiştirme gerçekleştirmenizi sağlar.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yeni Belge Oluşturma

Dize değiştirmeyi kullanmaya başlamadan önce Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgemiz olduğunda, bir metin kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde,`Writeln` "üzgün, çılgın, kötü" ifadesini ekleme yöntemi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## 3. Adım: Bir dizeyle değiştirin

 biz kullanıyoruz`Range.Replace` metni bir dizeyle değiştirme yöntemi. Örneğimizde, "üzgün" kelimesinin tüm oluşumlarını "kötü" ile değiştiriyoruz.`FindReplaceOptions` ile seçenek`FindReplaceDirection.Forward` arama yönü:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## 4. Adım: Düzenlenen belgeyi kaydetme

 Son olarak, değiştirilmiş belgeyi kullanarak belirtilen bir dizine kaydediyoruz.`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Aspose.Words for .NET kullanan replace with string için örnek kaynak kodu

Aspose.Words for .NET ile bir karakter dizisiyle değiştirmenin kullanımını gösteren tam örnek kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in String ile Değiştir işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, bir dizeyle değiştirmek ve değiştirilen belgeyi kaydetmek için adım adım bir kılavuz izledik.
