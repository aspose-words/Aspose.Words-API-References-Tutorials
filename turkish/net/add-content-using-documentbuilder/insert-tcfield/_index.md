---
title: TCField'i ekle
linktitle: TCField'i ekle
second_title: Aspose.Words for .NET API Referansı
description: Bu adım adım kılavuzda C# ve Aspose.Words for .NET kullanarak Word belgelerine TCFields eklemeyi ve değiştirmeyi öğrenin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-tcfield/
---

Bu örnekte, Aspose.Words for .NET'in Insert TCField özelliğini kullanma sürecinde size rehberlik edeceğiz. TCField, bir Word belgesindeki bir içindekiler tablosu girişini temsil eder. Markdown formatında beklenen çıktıyla birlikte C# kaynak kodunun adım adım açıklamasını sağlayacağız. Başlayalım!

## 1. Adım: Belge ve belge oluşturucuyu başlatma

Başlamak için, belgeyi ve belge oluşturucuyu başlatmamız gerekiyor. Belge oluşturucu, Aspose.Words for .NET tarafından sağlanan ve Word belgelerini programlı olarak oluşturmamıza ve değiştirmemize izin veren güçlü bir araçtır. Bunu şu şekilde yapabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: TCField'in eklenmesi

 Ardından, TCField'i kullanarak belgeye ekleyeceğiz.`InsertField` yöntem. TCField, belirtilen giriş metnine sahip bir içindekiler tablosu girişini temsil eder. İşte bir örnek:

```csharp
builder.InsertField("TC \"Entry Text\" \\f t");
```

Yukarıdaki kod, belgeye "Giriş Metni" giriş metnine sahip bir TCField ekleyecektir.

## 3. Adım: Belgeyi kaydetme

 TCField'ı ekledikten sonra, belgeyi kullanarak belirli bir konuma kaydedebiliriz.`Save` yöntem. Çıktı belgesi için istenen yolu ve dosya adını sağladığınızdan emin olun. İşte bir örnek:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

Yukarıdaki kod, belgeyi TCField ile belirtilen dizine kaydedecektir.

## Çıktı İşaretleme Formatları

Kod başarıyla yürütüldüğünde, çıktı belgesi, belirtilen giriş metniyle bir içindekiler tablosu girişi içerecektir. TCField, Word belgesinde bir alan olarak temsil edilir ve ortaya çıkan işaretleme biçimi, belgenin nasıl işlendiğine bağlı olacaktır.

Çıktı belgesinin doğrudan işaretleme biçiminde değil, Word biçiminde olduğunu lütfen unutmayın. Ancak, uygun araçları veya kitaplıkları kullanarak Word belgesini işaretlemeye dönüştürdüğünüzde, TCField buna göre işlenecektir.

### Aspose.Words for .NET kullanarak TCField Ekleme için Örnek Kaynak Kodu

İşte Aspose.Words for .NET kullanarak bir TCField eklemek için eksiksiz örnek kaynak kodu:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("TC \"Entry Text\" \\f t");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

Kodu gereksinimlerinize göre değiştirmekten ve Aspose.Words for .NET tarafından sağlanan diğer özellikleri keşfetmekten çekinmeyin.

Bu kadar! Aspose.Words for .NET kullanarak bir TCField'in nasıl ekleneceğini başarıyla öğrendiniz.

