---
title: Belge Metni Yönü
linktitle: Belge Metni Yönü
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET kullanarak Word'de belge metni yönünü nasıl ayarlayacağınızı öğrenin. Sağdan sola dilleri işlemek için mükemmeldir.
type: docs
weight: 10
url: /tr/net/programming-with-txtloadoptions/document-text-direction/
---
## giriiş

Word belgeleriyle, özellikle de birden fazla dil içeren veya özel biçimlendirme ihtiyaçları içeren belgelerle çalışırken, metin yönünü ayarlamak çok önemli olabilir. Örneğin İbranice veya Arapça gibi sağdan sola yazılan dillerle çalışırken metin yönünü buna göre ayarlamanız gerekebilir. Bu kılavuzda Aspose.Words for .NET'i kullanarak belge metni yönünün nasıl ayarlanacağını açıklayacağız. 

## Önkoşullar

Koda dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET Library: Aspose.Words for .NET'in kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Web sitesi](https://releases.aspose.com/words/net/).
- Visual Studio: C# kodunu yazmak ve yürütmek için bir geliştirme ortamı.
- Temel C# Bilgisi: Bazı kodlar yazacağımız için C# programlamaya aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar

Başlamak için projenizde Aspose.Words ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Words;
using Aspose.Words.Loading;
```

Bu ad alanları, Word belgelerini işlemek için gereken sınıflara ve yöntemlere erişim sağlar.

## 1. Adım: Belge Dizininizin Yolunu Tanımlayın

Öncelikle belgenizin bulunduğu yere giden yolu ayarlayın. Bu, dosyaları doğru şekilde yüklemek ve kaydetmek için çok önemlidir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin saklandığı gerçek yolla.

## Adım 2: Belge Yönü Ayarıyla TxtLoadOptions Oluşturun

 Daha sonra, bir örneğini oluşturmanız gerekecek`TxtLoadOptions` ve onu ayarla`DocumentDirection` mülk. Bu, Aspose.Words'e belgedeki metnin yönünü nasıl işleyeceğini anlatır.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };
```

 Bu örnekte şunu kullanıyoruz:`DocumentDirection.Auto` Aspose.Words'ün içeriğe göre yönü otomatik olarak belirlemesini sağlamak için.

## 3. Adım: Belgeyi Yükleyin

 Şimdi belgeyi kullanarak yükleyin.`Document` sınıf ve önceden tanımlanmış`loadOptions`.

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Burada,`"Hebrew text.txt"` metin dosyanızın adıdır. Bu dosyanın belirttiğiniz dizinde bulunduğundan emin olun.

## Adım 4: Paragrafın Çift Yönlü Biçimlendirmesine Erişin ve Kontrol Edin

Metin yönünün doğru ayarlandığını doğrulamak için belgenin ilk paragrafına erişin ve çift yönlü biçimlendirmesini kontrol edin.

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

Bu adım, hata ayıklamak ve belgenin metin yönünün beklendiği gibi uygulandığını doğrulamak için kullanışlıdır.

## Adım 5: Belgeyi Yeni Ayarlarla Kaydedin

Son olarak, değişiklikleri uygulamak ve sürdürmek için belgeyi kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Burada,`"WorkingWithTxtLoadOptions.DocumentTextDirection.docx"` çıktı dosyasının adıdır. Yaptığınız değişiklikleri yansıtan bir ad seçtiğinizden emin olun.

## Çözüm

Aspose.Words for .NET ile Word belgelerinde metin yönünü ayarlamak basit bir işlemdir. Bu adımları izleyerek belgenizin sağdan sola veya soldan sağa metni nasıl işleyeceğini kolayca yapılandırabilirsiniz. İster çok dilli belgelerle çalışıyor olun ister belirli diller için metin yönünü biçimlendirmeniz gerekiyor olsun, Aspose.Words ihtiyaçlarınızı karşılayacak güçlü bir çözüm sunar.

## SSS'ler

###  Nedir`DocumentDirection` property used for?

`DocumentDirection` mülkiyet`TxtLoadOptions` belgenin metin yönünü belirler. Şu şekilde ayarlanabilir:`DocumentDirection.Auto`, `DocumentDirection.LeftToRight` , veya`DocumentDirection.RightToLeft`.

### Metin yönünü belgenin tamamı yerine belirli paragraflar için ayarlayabilir miyim?

 Evet, belirli paragraflar için metin yönünü ayarlayabilirsiniz.`ParagraphFormat.Bidi` mülkiyet ama`TxtLoadOptions.DocumentDirection` özelliği belgenin tamamı için varsayılan yönü ayarlar.

###  Yükleme için hangi dosya formatları desteklenir?`TxtLoadOptions`?

`TxtLoadOptions` öncelikle metin dosyalarını (.txt) yüklemek için kullanılır. Diğer dosya formatları için aşağıdaki gibi farklı sınıflar kullanın:`DocLoadOptions` veya`DocxLoadOptions`.

### Karışık metin talimatlarına sahip belgeleri nasıl işleyebilirim?

 Karışık metin yönlerine sahip belgeler için biçimlendirmeyi paragraf başına ayrı ayrı ele almanız gerekebilir. Kullan`ParagraphFormat.Bidi` Her paragrafın yönünü gerektiği gibi ayarlama özelliği.

### Aspose.Words for .NET hakkında daha fazla bilgiyi nerede bulabilirim?

 Daha fazla ayrıntı için şuraya göz atın:[Aspose.Words for .NET Belgeleri](https://reference.aspose.com/words/net/) . Ayrıca aşağıdaki gibi ek kaynakları da keşfedebilirsiniz.[İndirme: {link](https://releases.aspose.com/words/net/), [Satın almak](https://purchase.aspose.com/buy), [Ücretsiz deneme](https://releases.aspose.com/), [Geçici lisans](https://purchase.aspose.com/temporary-license/) , Ve[Destek](https://forum.aspose.com/c/words/8).