---
title: Önceki Bölümden Üstbilgileri Altbilgileri Kopyala
linktitle: Önceki Bölümden Üstbilgileri Altbilgileri Kopyala
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinin önceki bölümlerinden üst bilgileri ve alt bilgileri nasıl kopyalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

Bu adım adım öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki önceki bölümdeki üst bilgileri ve alt bilgileri nasıl kopyalayacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Önceki Bölüme Erişim

 İlk olarak, erişerek önceki bölümü alın.`PreviousSibling` geçerli bölümün özelliği:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## 2. Adım: Önceki Bölümü Kontrol Etme

Ardından, önceki bir bölümün olup olmadığını kontrol edin. Önceki bölüm yoksa, basitçe geri döneriz:

```csharp
if (previousSection == null)
    return;
```

## 3. Adım: Üstbilgileri ve Altbilgileri Temizleme ve Kopyalama

Önceki bölümden geçerli bölüme üstbilgileri ve altbilgileri kopyalamak için, geçerli bölümdeki mevcut üstbilgileri ve altbilgileri temizleriz ve ardından mevcut bölüme klonlanmış kopyalar eklemek için önceki bölümün üstbilgileri ve altbilgilerini yineleriz:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## 4. Adım: Belgeyi Kaydetme

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
doc.Save("OutputDocument.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesindeki önceki bölümden geçerli bölüme üst bilgileri ve alt bilgileri başarıyla kopyaladınız.

### Aspose.Words for .NET kullanarak Önceki Bölümden Başlıkları Altbilgileri Kopyalamak için örnek kaynak kodu

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.