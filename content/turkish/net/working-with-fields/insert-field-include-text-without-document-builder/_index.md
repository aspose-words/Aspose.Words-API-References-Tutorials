---
title: Alan Ekle Belge Oluşturucu Olmadan Metni Ekle
linktitle: Belge Oluşturucu Olmadan FieldIncludeText Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Ayrıntılı, adım adım kılavuzumuzla Aspose.Words for .NET'te DocumentBuilder'ı kullanmadan FieldIncludeText'i nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-field-include-text-without-document-builder/
---
## giriiş

Belge otomasyonu ve manipülasyonu dünyasında Aspose.Words for .NET güçlü bir araç olarak duruyor. Bugün, DocumentBuilder'ı kullanmadan FieldIncludeText'in nasıl ekleneceğine dair ayrıntılı bir kılavuza geçiyoruz. Bu eğitim, kodun her bir bölümünü ve amacını anlamanızı sağlayacak şekilde süreç boyunca size adım adım yol gösterecektir.

## Önkoşullar

Koda dalmadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: En son sürümün kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
2. .NET Geliştirme Ortamı: Visual Studio gibi .NET uyumlu herhangi bir IDE.
3. Temel C# Bilgisi: C# programlamaya aşinalık, takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmamız gerekiyor. Bu ad alanları, Word belgelerini işlemek için gereken sınıflara ve yöntemlere erişim sağlar.

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

Şimdi örneği birden çok adıma ayıralım. Netliği sağlamak için her adım ayrıntılı olarak açıklanacaktır.

## 1. Adım: Dizin Yolunu Ayarlayın

İlk adım, belgeler dizininizin yolunu tanımlamaktır. Burası Word belgelerinizin saklanacağı ve erişileceği yerdir.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi ve Paragrafı Oluşturun

Daha sonra yeni bir belge ve o belgenin içinde bir paragraf oluşturuyoruz. Bu paragraf FieldIncludeText alanını tutacaktır.

```csharp
// Belgeyi ve paragrafı oluşturun.
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 3. Adım: FieldIncludeText Alanını Ekle

Şimdi FieldIncludeText alanını paragrafın içine ekliyoruz. Bu alan başka bir belgedeki metni eklemenizi sağlar.

```csharp
// FieldIncludeText alanını ekleyin.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

## 4. Adım: Alan Özelliklerini Ayarlayın

FieldIncludeText alanına ait özellikleri belirtmemiz gerekiyor. Buna yer imi adının ve kaynak belgenin tam yolunun ayarlanması da dahildir.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = dataDir + "IncludeText.docx";
```

## Adım 5: Belgeye Paragraf Ekleme

Alan ayarlandığında paragrafı belgenin ilk bölüm gövdesine ekleriz.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Adım 6: Alanı Güncelleyin

Belgeyi kaydetmeden önce, kaynak belgeden doğru içeriği aldığından emin olmak için FieldIncludeText'i güncellememiz gerekir.

```csharp
fieldIncludeText.Update();
```

## Adım 7: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydediyoruz.

```csharp
doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

## Çözüm

Ve işte karşınızda! Bu adımları izleyerek Aspose.Words for .NET'te DocumentBuilder'ı kullanmadan FieldIncludeText'i kolayca ekleyebilirsiniz. Bu yaklaşım, içeriği bir belgeden diğerine eklemek için kolaylaştırılmış bir yol sağlayarak belge otomasyonu görevlerinizi çok daha basit hale getirir.

## SSS'ler

### Aspose.Words for .NET nedir?  
Aspose.Words for .NET, .NET uygulamalarında Word belgeleriyle çalışmak için güçlü bir kütüphanedir. Belgelerin programlı olarak oluşturulmasına, düzenlenmesine ve dönüştürülmesine olanak tanır.

### FieldIncludeText'i neden kullanmalıyım?  
FieldIncludeText, içeriğin bir belgeden diğerine dinamik olarak dahil edilmesi ve daha modüler ve bakımı kolay belgeler sağlanması açısından kullanışlıdır.

### Bu yöntemi diğer dosya biçimlerinden metin eklemek için kullanabilir miyim?  
FieldIncludeText özellikle Word belgeleriyle çalışır. Diğer formatlar için Aspose.Words tarafından sağlanan farklı yöntemlere veya sınıflara ihtiyacınız olabilir.

### Aspose.Words for .NET, .NET Core ile uyumlu mu?  
Evet, Aspose.Words for .NET; .NET Framework, .NET Core ve .NET 5/6'yı destekler.

### Aspose.Words for .NET'in ücretsiz deneme sürümünü nasıl edinebilirim?  
 Şu adresten ücretsiz deneme alabilirsiniz:[Burada](https://releases.aspose.com/).