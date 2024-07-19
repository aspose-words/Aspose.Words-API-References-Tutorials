---
title: Kaynak Üstbilgileri Altbilgilerini Kaldır
linktitle: Kaynak Üstbilgileri Altbilgilerini Kaldır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki üstbilgileri ve altbilgileri nasıl kaldıracağınızı öğrenin. Adım adım kılavuzumuzla belge yönetiminizi basitleştirin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/remove-source-headers-footers/
---
## giriiş

Bu kapsamlı kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki üstbilgileri ve altbilgileri etkili bir şekilde nasıl kaldırabileceğinizi inceleyeceğiz. Üstbilgiler ve altbilgiler genellikle sayfa numaralandırma, belge başlıkları veya Word belgelerinde yinelenen diğer içerik için kullanılır. İster belgeleri birleştiriyor ister biçimlendirmeyi temizliyor olun, bu süreçte uzmanlaşmak belge yönetimi görevlerinizi kolaylaştırabilir. Aspose.Words for .NET'i kullanarak bunu başarmak için adım adım süreci inceleyelim.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:

1. Geliştirme Ortamı: Visual Studio'nun veya başka herhangi bir .NET geliştirme ortamının kurulu olmasını sağlayın.
2.  Aspose.Words for .NET: Aspose.Words for .NET'i indirip yüklediğinizden emin olun. Değilse şuradan alabilirsiniz[Burada](https://releases.aspose.com/words/net/).
3. Temel Bilgi: C# programlamaya ve .NET framework temellerine aşinalık.

## Ad Alanlarını İçe Aktar

Kodlamaya başlamadan önce gerekli ad alanlarını C# dosyanıza aktardığınızdan emin olun:

```csharp
using Aspose.Words;
```

## 1. Adım: Kaynak Belgeyi Yükleyin

Öncelikle üstbilgileri ve altbilgileri kaldırmak istediğiniz kaynak belgeyi yüklemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` kaynak belgenin bulunduğu belge dizininizin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Adım 2: Hedef Belgesini Oluşturun veya Yükleyin

 Değiştirilen içeriği yerleştirmek istediğiniz hedef belgeyi henüz oluşturmadıysanız yeni bir belge oluşturabilirsiniz.`Document` nesneyi kullanın veya mevcut olanı yükleyin.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: Bölümlerdeki Üstbilgileri ve Altbilgileri Temizleyin

Kaynak belgedeki her bölümü yineleyin (`srcDoc`) ve üstbilgilerini ve altbilgilerini temizleyin.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## 4. Adım: LinkToÖnceki Ayarı Yönetin

Üstbilgilerin ve altbilgilerin hedef belgede devam etmesini önlemek için (`dstDoc` ), olduğundan emin olun`LinkToPrevious` Üstbilgiler ve altbilgiler için ayar şu şekilde ayarlandı:`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Adım 5: Değiştirilen Belgeyi Hedef Belgeye Ekle

Son olarak, değiştirilen içeriği kaynak belgeden ekleyin (`srcDoc`) hedef belgeye (`dstDoc`) kaynak biçimlendirmesini korurken.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 6: Ortaya Çıkan Belgeyi Kaydedin

Kaldırılan üstbilgiler ve altbilgilerle birlikte son belgeyi belirttiğiniz dizine kaydedin.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

## Çözüm

Aspose.Words for .NET kullanarak bir Word belgesinden üstbilgileri ve altbilgileri kaldırmak, belge yönetimi görevlerini büyük ölçüde geliştirebilecek basit bir işlemdir. Yukarıda özetlenen adımları izleyerek belgelerinizi parlak, profesyonel bir görünüm için etkili bir şekilde temizleyebilirsiniz.

## SSS'ler

### Üstbilgileri ve altbilgileri yalnızca belirli bölümlerden kaldırabilir miyim?
Evet, bölümler arasında geçiş yapabilir ve gerektiğinde üstbilgileri ve altbilgileri seçerek temizleyebilirsiniz.

### Aspose.Words for .NET birden fazla belgedeki üstbilgi ve altbilgilerin kaldırılmasını destekliyor mu?
Aspose.Words for .NET'i kullanarak birden fazla belgedeki üstbilgileri ve altbilgileri kesinlikle değiştirebilirsiniz.

###  Ayarlamayı unutursam ne olur?`LinkToPrevious` to `false`?
Kaynak belgedeki üstbilgiler ve altbilgiler hedef belgede devam edebilir.

### Üstbilgileri ve altbilgileri diğer biçimlendirmeyi etkilemeden programlı olarak kaldırabilir miyim?
Evet, Aspose.Words for .NET, belgenin geri kalan formatını korurken üstbilgileri ve altbilgileri kaldırmanıza olanak tanır.

### Aspose.Words for .NET için daha fazla kaynağı ve desteği nerede bulabilirim?
 Ziyaret edin[Aspose.Words for .NET belgeleri](https://reference.aspose.com/words/net/) ayrıntılı API referansları ve örnekleri için.
