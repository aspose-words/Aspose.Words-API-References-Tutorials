---
title: Basit Bul Değiştir
linktitle: Basit Bul Değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesinde basit bir bul ve değiştir işlemini nasıl gerçekleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/simple-find-replace/
---

Bu makalede, Aspose.Words for .NET kitaplığında Basit Bul Değiştirme işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, belirli bir karakter dizisini arayarak ve onu bir Word belgesinde başka bir karakter dizisiyle değiştirerek basit metin değişimi gerçekleştirmenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yeni Belge Oluşturma

 Basit bul ve değiştir özelliğini kullanmaya başlamadan önce Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgemiz olduğunda, bir metin kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde,`Writeln` "Merhaba" ifadesini ekleme yöntemi_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## 3. Adım: Basit Metin Değiştirme

 biz kullanıyoruz`Range.Replace` basit metin değiştirme gerçekleştirme yöntemi. Örneğimizde, " dizesinin tüm oluşumlarını değiştiriyoruz._ClientName_ " kullanarak "James Bond" ile`FindReplaceOptions` ile seçenek`FindReplaceDirection.Forward` arama yönü:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## 4. Adım: Düzenlenen belgeyi kaydetme

 Son olarak, değiştirilmiş belgeyi kullanarak belirtilen bir dizine kaydediyoruz.`Save` yöntem:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Aspose.Words for .NET kullanan Basit Bul Değiştirme için örnek kaynak kodu

Aspose.Words for .NET ile basit arama ve değiştirmenin kullanımını gösteren tam örnek kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Değiştirilen belgeyi kaydet
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Çözüm

Bu makalede, Aspose.Words for .NET'in Basit Bul Değiştirme işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, basit metin değiştirme gerçekleştirmek ve düzenlenen belgeyi kaydetmek için adım adım bir kılavuz izledik.
