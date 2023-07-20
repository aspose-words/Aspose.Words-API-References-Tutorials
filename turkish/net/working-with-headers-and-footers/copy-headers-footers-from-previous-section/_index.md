---
title: Önceki Bölümden Üstbilgileri Altbilgileri Kopyala
linktitle: Önceki Bölümden Üstbilgileri Altbilgileri Kopyala
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerinin önceki bölümlerinden üst bilgileri ve alt bilgileri nasıl kopyalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

Bu adım adım öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki önceki bölümdeki üst bilgileri ve alt bilgileri nasıl kopyalayacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı adresinden indirip yükleyin.[Aspose.Releases]https://releases.aspose.com/words/net/.

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

### SSS

#### S: Önceki bölümdeki üst bilgileri ve alt bilgileri Aspose.Words'e nasıl kopyalayabilirim?

 C: Önceki bölümden üstbilgileri ve altbilgileri Aspose.Words'e kopyalamak için`CopyHeadersFootersFromPreviousSection()` geçerli yöntem`Section`nesne. Bu, önceki bölümdeki üstbilgileri ve altbilgileri geçerli bölüme kopyalayacaktır.

#### S: Aspose.Words'te bir önceki bölümden sadece üst bilgiyi veya alt bilgiyi kopyalamak mümkün mü?

 C: Evet, Aspose.Words'te önceki bölümden yalnızca üstbilgi veya altbilgi kopyalamak mümkündür. Bunun için kullanabilirsiniz`CopyHeaderFromPreviousSection()` Ve`CopyFooterFromPreviousSection()` geçerli yöntemler`Section` önceki bölümden geçerli bölüme özel olarak üstbilgi veya altbilgi kopyalamak için nesne.

#### S: Önceki bölümden üst bilgileri ve alt bilgileri kopyalamak, geçerli bölümdeki mevcut üst bilgileri ve alt bilgileri değiştirir mi?

C: Evet, önceki bölümdeki üst bilgileri ve alt bilgileri kopyalamak, geçerli bölümdeki mevcut üst bilgileri ve alt bilgileri değiştirir. Mevcut üstbilgi ve altbilgileri korumak ve bunları kopyalanan üstbilgi ve altbilgilere eklemek istiyorsanız, içerikleri birleştirmek için ek bir işlem yapmanız gerekecektir.

#### S: Aspose.Words'te bir bölümün bir önceki bölümden üstbilgi veya altbilgiye sahip olup olmadığını nasıl kontrol edebilirim?

C: Bir bölümün Aspose.Words'teki bir önceki bölümden üstbilgi veya altbilgiye sahip olup olmadığını kontrol etmek için`HasHeader` Ve`HasFooter` üzerindeki özellikler`Section` üst bilgi veya alt bilginin mevcut olup olmadığını belirlemek için nesne. Eğer`HasHeader` veya`HasFooter` İadeler`false`, bu bölümde önceki bölümden üstbilgi veya altbilgi olmadığı anlamına gelir.