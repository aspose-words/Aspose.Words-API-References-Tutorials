---
title: Önceki Bölümden Üstbilgi Altbilgilerini Kopyala
linktitle: Önceki Bölümden Üstbilgi Altbilgilerini Kopyala
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki önceki bölümdeki üstbilgileri ve altbilgileri nasıl kopyalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

Bu adım adım eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde önceki bölümdeki üstbilgileri ve altbilgileri nasıl kopyalayacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve kurulu olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin.[Aspose.Releases]https://releases.aspose.com/words/net/.

## Adım 1: Önceki Bölüme Erişim

 Öncelikle, şuraya erişerek önceki bölümü alın:`PreviousSibling` geçerli bölümün özelliği:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Adım 2: Önceki Bölümün Kontrol Edilmesi

Daha sonra, önceki bölümün mevcut olup olmadığını kontrol edin. Önceki bölüm yoksa, basitçe geri döneriz:

```csharp
if (previousSection == null)
    return;
```

## 3. Adım: Üstbilgileri ve Altbilgileri Temizleme ve Kopyalama

Önceki bölümdeki üstbilgileri ve altbilgileri geçerli bölüme kopyalamak için, geçerli bölümdeki mevcut üstbilgileri ve altbilgileri temizleriz ve ardından geçerli bölüme klonlanmış kopyalar eklemek için önceki bölümün üstbilgileri ve altbilgilerini yineleriz:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Adım 4: Belgeyi Kaydetme

Son olarak değiştirilen belgeyi kaydedin:

```csharp
doc.Save("OutputDocument.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak önceki bölümdeki üstbilgileri ve altbilgileri bir Word belgesindeki geçerli bölüme başarıyla kopyaladınız.

### Aspose.Words for .NET kullanarak Önceki Bölümden Başlık Alt Bilgilerini Kopyalamak için örnek kaynak kodu

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Bu kodu kendi projelerinizde kullanmaktan ve özel gereksinimlerinize göre değiştirmekten çekinmeyin.

### SSS'ler

#### S: Önceki bölümdeki üstbilgileri ve altbilgileri Aspose.Words'e nasıl kopyalayabilirim?

 C: Önceki bölümdeki üstbilgileri ve altbilgileri Aspose.Words'e kopyalamak için`CopyHeadersFootersFromPreviousSection()` mevcut yöntem`Section`nesne. Bu, önceki bölümdeki üstbilgileri ve altbilgileri geçerli bölüme kopyalayacaktır.

#### S: Aspose.Words'te önceki bölümden yalnızca üstbilgi veya altbilgiyi kopyalamak mümkün mü?

 C: Evet, Aspose.Words'te önceki bölümden yalnızca üstbilgi veya altbilgiyi kopyalamak mümkündür. Bunun için şunları kullanabilirsiniz:`CopyHeaderFromPreviousSection()` Ve`CopyFooterFromPreviousSection()` mevcut yöntemler`Section` Üstbilgiyi veya altbilgiyi önceki bölümden geçerli bölüme özel olarak kopyalamak için nesneyi kullanın.

#### S: Önceki bölümdeki üstbilgi ve altbilgilerin kopyalanması, geçerli bölümdeki mevcut üstbilgi ve altbilgilerin yerine geçer mi?

C: Evet, önceki bölümdeki üstbilgilerin ve altbilgilerin kopyalanması, geçerli bölümdeki mevcut üstbilgilerin ve altbilgilerin yerine geçer. Mevcut üstbilgi ve altbilgileri korumak ve bunları kopyalanan üstbilgi ve altbilgilere eklemek istiyorsanız, içerikleri birleştirmek için ek bir işlem yapmanız gerekecektir.

#### S: Aspose.Words'te bir bölümün önceki bölümden üstbilgi veya altbilgiye sahip olup olmadığını nasıl kontrol edebilirim?

C: Bir bölümün Aspose.Words'teki önceki bölümden üstbilgi veya altbilgiye sahip olup olmadığını kontrol etmek için,`HasHeader` Ve`HasFooter` üzerindeki özellikler`Section` Üstbilginin veya altbilginin mevcut olup olmadığını belirlemek için nesne. Eğer`HasHeader` veya`HasFooter` İadeler`false`, bu bölümde önceki bölüme ait üstbilgi veya altbilgi olmadığı anlamına gelir.