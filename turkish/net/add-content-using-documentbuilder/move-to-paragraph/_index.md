---
title: Paragrafa Taşı
linktitle: Paragrafa Taşı
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'in Paragrafa Taşı özelliğinin Word belgelerindeki paragraflarda programlı olarak gezinmek ve bunları değiştirmek için nasıl kullanılacağını öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-paragraph/
---

Bu adım adım örnekte Aspose.Words for .NET'in Paragrafa Taşı özelliğini inceleyeceğiz. Bu özellik, geliştiricilerin bir Word belgesindeki paragraflarda programlı olarak gezinmesine ve bunları değiştirmesine olanak tanır. Bu kılavuzu izleyerek, Paragrafa Taşı özelliğini etkili bir şekilde nasıl uygulayacağınızı ve kullanacağınızı öğreneceksiniz.

Yukarıdaki kod, Paragrafa Taşı özelliğinin kullanımını gösterir. Her adımı ayrıntılı olarak anlayalım:

## 1. Adım: Belgeyi Yükleme

 Word belgesini bir örneğine yükleyerek başlıyoruz.`Document` sınıf. bu`MyDir`değişken, belgenin bulunduğu dizin yolunu temsil eder. Bunu gerçek dizin yolu ile değiştirmeli veya kodu buna göre değiştirmelisiniz.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
```

## Adım 2: DocumentBuilder'ı Başlatma

 Sonra, bir`DocumentBuilder` nesneyi seçin ve yüklenen belgeyle ilişkilendirin. bu`DocumentBuilder` class, belgenin içeriğini değiştirmek için çeşitli yöntemler ve özellikler sağlar.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Belirli Bir Paragrafa Geçmek

 bu`MoveToParagraph` yöntem, belge oluşturucuyu belge içinde belirli bir paragrafta konumlandırmak için kullanılır. İki parametre alır: hedef paragrafın dizini ve o paragraf içindeki karakter konumu (0, paragrafın başlangıcını temsil eder).

Verilen örnekte, belgenin üçüncü paragrafına (dizin 2) geçiyoruz:

```csharp
builder.MoveToParagraph(2, 0);
```

## 4. Adım: Paragraf İçeriğini Değiştirme

 Oluşturucu istenen paragrafa yerleştirildikten sonra,`Writeln` paragrafın içeriğini ekleme veya değiştirme yöntemi. Bu durumda "Bu 3. paragraftır" metnini ekliyoruz.

```csharp
builder.Writeln("This is the 3rd paragraph.");
```

### Aspose.Words for .NET kullanarak Paragrafa Taşı için Örnek Kaynak Kodu

Aşağıda, Aspose.Words for .NET kullanarak Paragrafa Taşı özelliğini uygulamaya yönelik tam örnek kaynak kodu bulunmaktadır:

```csharp

	Document doc = new Document(MyDir + "Paragraphs.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToParagraph(2, 0);
	builder.Writeln("This is the 3rd paragraph.");
	
```

Bu kılavuzu takip ederek ve Paragrafa Taşı özelliğini kullanarak, Aspose.Words for .NET kullanarak Word belgeleri içindeki paragrafları programlı bir şekilde değiştirebilirsiniz.

