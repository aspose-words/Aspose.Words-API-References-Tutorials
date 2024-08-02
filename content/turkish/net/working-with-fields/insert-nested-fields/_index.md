---
title: İç İçe Alanlar Ekle
linktitle: İç İçe Alanlar Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Adım adım kılavuzumuzla Aspose.Words for .NET kullanarak Word belgelerine yuvalanmış alanları nasıl ekleyeceğinizi öğrenin. Belge oluşturmayı otomatikleştirmek isteyen geliştiriciler için mükemmeldir.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-nested-fields/
---
## giriiş

Hiç Word belgelerinize programlı olarak iç içe geçmiş alanlar eklemeye ihtiyaç duyduğunuzu fark ettiniz mi? Belki sayfa numarasına göre farklı metinleri koşullu olarak görüntülemek istersiniz? Şanslısın! Bu eğitim, Aspose.Words for .NET'i kullanarak iç içe alanlar ekleme sürecinde size rehberlik edecektir. Hadi dalalım!

## Önkoşullar

Başlamadan önce ihtiyacınız olacak birkaç şey var:

1.  Aspose.Words for .NET: Aspose.Words for .NET kitaplığına sahip olduğunuzdan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio benzeri bir IDE.
3. Temel C# Bilgisi: C# programlama dilinin anlaşılması.

## Ad Alanlarını İçe Aktar

Öncelikle projenize gerekli ad alanlarını içe aktardığınızdan emin olun. Bu ad alanları Aspose.Words ile etkileşime geçmek için ihtiyaç duyacağınız sınıfları içerir.

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
using Aspose.Words.HeaderFooter;
```

## 1. Adım: Belgeyi Başlatın

İlk adım, yeni bir belge ve DocumentBuilder nesnesi oluşturmaktır. DocumentBuilder sınıfı, Word belgelerinin oluşturulmasına ve değiştirilmesine yardımcı olur.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi ve DocumentBuilder'ı oluşturun.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Sayfa Sonlarını Ekle

Daha sonra belgeye birkaç sayfa sonu ekleyeceğiz. Bu, iç içe geçmiş alanları etkili bir şekilde göstermemize olanak sağlayacaktır.

```csharp
// Sayfa sonları ekleyin.
for (int i = 0; i < 5; i++)
{
    builder.InsertBreak(BreakType.PageBreak);
}
```

## 3. Adım: Alt Bilgiye Taşı

Sayfa sonlarını ekledikten sonra belgenin altbilgisine gitmemiz gerekiyor. Burası iç içe alanımızı ekleyeceğimiz yer.

```csharp
// Altbilgiye git.
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Adım 4: İç İçe Alan Ekle

Şimdi iç içe alanı ekleyelim. Geçerli sayfa numarasına göre metni koşullu olarak görüntülemek için IF alanını kullanacağız.

```csharp
// İç içe alan ekleyin.
Field field = builder.InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder.InsertField("PAGE");
builder.Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

Bu adımda öncelikle IF alanını ekliyoruz, ayırıcısına geçiyoruz ve ardından PAGE ve NUMPAGES alanlarını ekliyoruz. IF alanı, geçerli sayfa numarasının (PAGE) toplam sayfa sayısına (NUMPAGES) eşit olup olmadığını kontrol eder. Doğruysa “Sonraki sayfaya bakın”, aksi takdirde “Son sayfa” görüntülenir.

## 5. Adım: Alanı Güncelleyin

Son olarak, doğru metni gösterdiğinden emin olmak için alanı güncelliyoruz.

```csharp
// Alanı güncelleyin.
field.Update();
```

## Adım 6: Belgeyi Kaydedin

Son adım, belgeyi belirttiğiniz dizine kaydetmektir.

```csharp
doc.Save(dataDir + "InsertNestedFields.docx");
```

## Çözüm

İşte buyur! Aspose.Words for .NET'i kullanarak iç içe geçmiş alanları bir Word belgesine başarıyla eklediniz. Bu güçlü kitaplık, Word belgelerini programlı olarak yönetmeyi inanılmaz derecede kolaylaştırır. İster rapor oluşturuyor olun, ister şablon oluşturuyor olun, ister belge iş akışlarını otomatikleştiriyor olun, Aspose.Words yanınızdadır.

## SSS'ler

### Word belgelerinde iç içe alan nedir?
Yuvalanmış alan, içinde başka alanlar içeren bir alandır. Belgelerde daha karmaşık ve koşullu içeriğe izin verir.

### IF alanı içindeki diğer alanları kullanabilir miyim?
Evet, dinamik içerik oluşturmak için IF alanının içine DATE, TIME ve AUTHOR gibi çeşitli alanları iç içe yerleştirebilirsiniz.

### Aspose.Words for .NET ücretsiz mi?
 Aspose.Words for .NET ticari bir kütüphanedir, ancak[ücretsiz deneme](https://releases.aspose.com/) denemek için.

### Aspose.Words'ü diğer .NET dilleriyle kullanabilir miyim?
Evet, Aspose.Words, VB.NET ve F# dahil tüm .NET dillerini destekler.

### Aspose.Words for .NET hakkında daha fazla belgeyi nerede bulabilirim?
 Ayrıntılı belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).