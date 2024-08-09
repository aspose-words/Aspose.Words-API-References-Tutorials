---
title: Kelime Türlerinin Revizyonunu Alın
linktitle: Kelime Türlerinin Revizyonunu Alın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesindeki kelimelerin revizyon türlerini nasıl alacağınızı öğrenin. Bu adım adım kılavuz, belge revizyonlarını verimli bir şekilde gerçekleştirmenize yardımcı olur.
type: docs
weight: 10
url: /tr/net/working-with-revisions/get-revision-types/
---
## giriiş

Hiç kendinizi diz boyu belge revizyonları denizinde buldunuz mu, kimin neyi, ne zaman taşıdığını merak ettiniz mi? Yalnız değilsin. Belge revizyonlarıyla uğraşmak, özellikle kapsamlı belgelerle uğraşırken sıkıcı bir iş olabilir. Ama endişelenme! Aspose.Words for .NET ile bu revizyonları kolaylıkla tanımlayıp yönetebilirsiniz. Bu kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki kelimelerin revizyon türlerinin nasıl elde edileceği konusunda size adım adım yol göstereceğiz. O halde kemerinizi bağlayın ve dalmaya başlayalım!

## Önkoşullar

Bazı kodlarla elimizi kirletmeden önce ihtiyacınız olacak birkaç şey var:

1.  Aspose.Words for .NET Kütüphanesi: Henüz yapmadıysanız şu adresten indirin:[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya herhangi bir .NET uyumlu IDE.
3. Temel C# Bilgisi: C# programlama dilini anlamak faydalı olacaktır.
4.  Düzeltmeleri Olan Bir Word Belgesi: Bir Word Belgesine sahip olduğunuzdan emin olun.`.docx`Kodu test etmek için izlenen değişiklikleri içeren dosya.

## Ad Alanlarını İçe Aktar

Başlamak için C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu, Aspose.Words for .NET tarafından sağlanan işlevlere erişmenizi sağlayacaktır.

```csharp
using Aspose.Words;
using Aspose.Words.Revision;
using System;
```

Daha iyi anlaşılması ve uygulanması için örneği birden fazla adıma ayıralım.

## 1. Adım: Belge Dizininizi Kurun

Öncelikle belgeler dizininizin yolunu tanımlamanız gerekir. Revizyonları olan Word belgenizin bulunacağı yer burasıdır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile.

## Adım 2: Word Belgenizi Yükleyin

Daha sonra Word belgesini projenize yüklemeniz gerekir. Bu belgede analiz etmek istediğiniz revizyonlar bulunmalıdır.

```csharp
Document doc = new Document(dataDir + "Revisions.docx");
```

 Dosyanın olduğundan emin olun`Revisions.docx` Belirtilen dizinde mevcut.

## 3. Adım: Paragraf Koleksiyonuna Erişin

Artık belgeniz yüklendiğine göre belge gövdesinin ilk bölümündeki paragraflara erişmeniz gerekiyor. Bu, revizyonları kontrol etmek için her paragrafı yinelemenize yardımcı olacaktır.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
```

## Adım 4: Paragrafları Yineleyin ve Düzeltmeleri Kontrol Edin

İşte sihrin gerçekleştiği yer burası. Her paragrafı tekrarlayacak ve taşınıp taşınmadığını (silindiğini veya eklendiğini) kontrol edeceksiniz.

```csharp
for (int i = 0; i < paragraphs.Count; i++)
{
    if (paragraphs[i].IsMoveFromRevision)
        Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
    if (paragraphs[i].IsMoveToRevision)
        Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

 Bu döngü her paragraftan geçer ve`IsMoveFromRevision`Ve`IsMoveToRevision` paragrafın taşındığını (silindiğini) veya taşındığını (eklendiğini) belirleyen özellikler.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak yalnızca birkaç satır kodla Word belgenizdeki revizyon türlerini kolayca belirleyebilirsiniz. Bu güçlü kitaplık, belge revizyonlarını yönetmeyi kolaylaştırarak daha önemli görevlere odaklanmanıza olanak tanır. 

## SSS'ler

### Aspose.Words for .NET'i belirli kullanıcılar tarafından yapılan değişiklikleri takip etmek için kullanabilir miyim?

Evet, Aspose.Words for .NET, değişikliklerin yazarı da dahil olmak üzere revizyon ayrıntılarına erişme işlevselliği sağlar.

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?

 Kesinlikle! Ücretsiz deneme alabilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Words for .NET için nasıl geçici lisans başvurusunda bulunabilirim?

 Geçici lisans talebinde bulunabilir ve başvurabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).

### Aspose.Words for .NET için daha ayrıntılı belgeleri nerede bulabilirim?

 Ayrıntılı belgeler şu adreste mevcuttur:[Web sitesi](https://reference.aspose.com/words/net/).

### Aspose.Words for .NET'i ticari olmayan bir projede kullanabilir miyim?

Evet, Aspose.Words for .NET hem ticari hem de ticari olmayan projelerde kullanılabilir ancak lisans koşullarını kontrol ettiğinizden emin olun.