---
title: Regex ile değiştir
linktitle: Regex ile değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde normal ifade tabanlı metin değiştirmeyi nasıl yapacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/replace-with-regex/
---

Bu makalede, Aspose.Words for .NET kitaplığında Regex ile Değiştir işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, normal bir ifade tarafından tanımlanan belirli kalıplara dayalı olarak metin değiştirme gerçekleştirmenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yeni Belge Oluşturma

 Düzenli ifade değiştirmeyi kullanmaya başlamadan önce Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

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

## 3. Adım: Bul ve Değiştir Seçeneklerini Yapılandırma

 Şimdi bul ve değiştir seçeneklerini bir a kullanarak yapılandıracağız.`FindReplaceOptions` nesne. Örneğimizde, varsayılan seçenekleri kullanıyoruz:

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## 4. Adım: Normal ifadeyle değiştirin

 biz kullanıyoruz`Range.Replace` normal bir ifade kullanarak metin değiştirme gerçekleştirme yöntemi. Örneğimizde, normal ifadeyi kullanıyoruz "[S|m]ad" to find the words "sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## Adım 5: Değiştirilen belgeyi kaydetme

 Son olarak, değiştirilmiş belgeyi kullanarak belirtilen bir dizine kaydediyoruz.`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### Aspose.Words for .NET kullanarak Change With Regex için örnek kaynak kodu

Aspose.Words for .NET ile normal ifade değişiminin kullanımını gösteren tam örnek kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Regex ile Değiştir işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, normal bir ifadeyle değiştirmeyi gerçekleştirmek ve değiştirilen belgeyi kaydetmek için adım adım bir kılavuz izledik.
