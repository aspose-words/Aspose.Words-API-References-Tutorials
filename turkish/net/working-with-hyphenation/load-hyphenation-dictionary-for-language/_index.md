---
title: Dil İçin Heceleme Sözlüğünü Yükle
linktitle: Dil İçin Heceleme Sözlüğünü Yükle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te belirli bir dil için heceleme sözlüğünü nasıl yükleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

Bu adım adım eğitimde, size belirli bir dil için heceleme sözlüğünü Aspose.Words for .NET'e nasıl yükleyeceğinizi göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kütüphaneyi resmi siteden indirip yükleyin.

## 1. Adım: Belgeyi yükleme

İlk olarak, belgenizi belirtilen dizinden yükleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 2. Adım: Tireleme sözlüğünü yükleme

Ardından, heceleme sözlüğü dosyasına bir akış açın ve onu istenen dil için kaydedin. Bu örnekte, İsviçre Almancası (de-CH) için bir sözlük yüklüyoruz:

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Veri dizininizde uygun sözlük dosyasının bulunduğundan emin olun.

## 3. Adım: Değiştirilen belgeyi kaydedin

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Bu yüzden ! Aspose.Words for .NET'te belirli bir dil için heceleme sözlüğünü başarıyla yüklediniz.

### Aspose.Words for .NET kullanan bir dil için heceleme sözlüğü yükleme örneği kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Bu kodu kendi projelerinizde kullanmaktan ve özel ihtiyaçlarınıza uyacak şekilde değiştirmekten çekinmeyin.