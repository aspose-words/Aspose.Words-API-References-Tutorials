---
title: Dillerin Tireli Kelimeleri
linktitle: Dillerin Tireli Kelimeleri
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinde farklı dillerdeki sözcükleri nasıl heceleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-hyphenation/hyphenate-words-of-languages/
---

Bu adım adım öğreticide, Aspose.Words for .NET kullanarak Word belgelerinde farklı dillerdeki sözcükleri nasıl heceleyeceğiniz konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kütüphaneyi resmi siteden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` farklı dillerde metin içeren kaynak belgenizin yolunu belirterek itiraz edin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 2. Adım: Tireleme Sözlüklerini Kaydetme

Ardından, işlemek istediğiniz farklı diller için heceleme sözlüklerini kaydedin. Bu örnekte, Amerikan İngilizcesi ve İsviçre Almancası için sözlükleri kaydediyoruz:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Veri dizininizde uygun sözlük dosyalarının bulunduğundan emin olun.

## 3. Adım: Kelimeleri tireleme yoluyla işleme

 Artık farklı dillerdeki sözcükleri işlemek için heceleme özelliklerini kullanabilirsiniz. farklı yöntemler kullanabilirsiniz`Document` veya`DocumentBuilder`özel ihtiyaçlarınıza bağlı olarak.

```csharp
// Örnek: DocumentBuilder'ın Tireleme yöntemini kullanma
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## 4. Adım: Belgeyi kaydedin

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Bu yüzden ! Aspose.Words for .NET kullanarak bir Word belgesinde kelimeleri farklı dillerde heceleyerek başarılı bir şekilde işlediniz.

### Aspose.Words for .NET kullanarak kelime tireleme için örnek kaynak kodu

	```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "German text.docx");

	Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
	Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

	doc.Save(dataDir + "TreatmentByCesure.pdf");
	```

Bu kodu kendi projelerinizde kullanmaktan ve özel ihtiyaçlarınıza uyacak şekilde değiştirmekten çekinmeyin.
