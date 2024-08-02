---
title: İçerik Kontrol Rengini Ayarla
linktitle: İçerik Kontrol Rengini Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word'deki Yapılandırılmış Belge Etiketlerinin rengini kolayca ayarlayın. Bu basit kılavuzla belge görünümünü geliştirmek için SDT'lerinizi özelleştirin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/set-content-control-color/
---
## giriiş

Word belgeleriyle çalışıyorsanız ve Yapılandırılmış Belge Etiketlerinin (SDT'ler) görünümünü özelleştirmeniz gerekiyorsa bunların rengini değiştirmek isteyebilirsiniz. Bu, özellikle öğelerin görsel olarak farklılaştırılmasının önemli olduğu formlar veya şablonlarla çalışırken kullanışlıdır. Bu kılavuzda Aspose.Words for .NET kullanarak bir SDT'nin rengini ayarlama sürecini anlatacağız.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
-  Aspose.Words for .NET: Bu kütüphanenin kurulu olması gerekmektedir. Şuradan indirebilirsiniz[Aspose'un web sitesi](https://releases.aspose.com/words/net/).
- Temel C# anlayışı: Bu eğitimde temel C# programlama kavramlarına aşina olduğunuz varsayılmaktadır.
- Bir Word belgesi: En az bir Yapılandırılmış Belge Etiketi içeren bir Word belgeniz olmalıdır.

## Ad Alanlarını İçe Aktar

Öncelikle C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Kod dosyanızın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
using System.Drawing;
```

## 1. Adım: Belge Yolunuzu Ayarlayın

Belge dizininizin yolunu belirtin ve belgeyi yükleyin:

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleyin

 Oluşturmak`Document` Word dosyanızı yükleyerek nesne:

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
```

## 3. Adım: Yapılandırılmış Belge Etiketine Erişin

Belgeden Yapılandırılmış Belge Etiketini (SDT) alın. Bu örnekte ilk SDT'ye erişiyoruz:

```csharp
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Adım 4: SDT Rengini Ayarlayın

SDT'nin renk özelliğini değiştirin. Burada rengi kırmızı olarak ayarladık:

```csharp
sdt.Color = Color.Red;
```

## Adım 5: Belgeyi Kaydedin

Güncellenen belgeyi yeni bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

## Çözüm

Aspose.Words for .NET kullanarak bir Word belgesindeki Yapılandırılmış Belge Etiketinin rengini değiştirmek çok kolaydır. Yukarıda özetlenen adımları izleyerek SDT'lerinize kolayca görsel değişiklikler uygulayabilir, belgelerinizin görünümünü ve işlevselliğini geliştirebilirsiniz.

## SSS'ler

### SDT'ler için farklı renkler kullanabilir miyim?

 Evet mevcut olan herhangi bir rengi kullanabilirsiniz.`System.Drawing.Color` sınıf. Örneğin şunları kullanabilirsiniz:`Color.Blue`, `Color.Green`, vesaire.

### Bir belgedeki birden çok SDT'nin rengini nasıl değiştiririm?

Belgedeki tüm SDT'ler arasında geçiş yapmanız ve renk değişikliğini her birine uygulamanız gerekir. Bunu, tüm SDT'ler boyunca yinelenen bir döngü kullanarak başarabilirsiniz.

### SDT'lerin renk dışında diğer özelliklerini ayarlamak mümkün müdür?

 Evet`StructuredDocumentTag` sınıfında yazı tipi boyutu, yazı tipi stili ve daha fazlası dahil olmak üzere ayarlayabileceğiniz çeşitli özellikler bulunur. Daha fazla ayrıntı için Aspose.Words belgelerine bakın.

### Tıklama etkinlikleri gibi SDT'lere etkinlikler ekleyebilir miyim?

Aspose.Words, SDT'ler için olay işlemeyi doğrudan desteklemez. Ancak SDT etkileşimlerini form alanları aracılığıyla yönetebilir veya kullanıcı girişlerini ve etkileşimlerini yönetmek için başka yöntemler kullanabilirsiniz.

### Bir SDT'yi belgeden kaldırmak mümkün müdür?

 Evet, SDT'yi arayarak kaldırabilirsiniz.`Remove()` SDT'nin üst düğümündeki yöntem.