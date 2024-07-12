---
title: Oluşturucuyla Belge Ekle
linktitle: Oluşturucuyla Belge Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak iki Word belgesini nasıl birleştireceğinizi öğrenin. DocumentBuilder ile belge eklemek ve biçimlendirmeyi korumak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/insert-document-with-builder/
---
## giriiş

Yani iki Word belgeniz var ve bunları tek bir belgede birleştirmeyi düşünüyorsunuz. "Bunu programlı olarak yapmanın kolay bir yolu var mı?" diye düşünüyor olabilirsiniz. Kesinlikle! Bugün size Aspose.Words for .NET kütüphanesini kullanarak bir belgeyi diğerine ekleme sürecini anlatacağım. Bu yöntem, özellikle büyük belgelerle uğraşırken veya süreci otomatikleştirmeniz gerektiğinde son derece kullanışlıdır. Haydi hemen dalalım!

## Önkoşullar

Başlamadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Henüz yapmadıysanız şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio'nun veya başka bir uygun IDE'nin kurulu olduğundan emin olun.
3. Temel C# Bilgisi: C#'a biraz aşina olmak uzun bir yol kat edecektir.

## Ad Alanlarını İçe Aktar

Aspose.Words kitaplığının işlevlerine erişmek için öncelikle gerekli ad alanlarını içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Artık önkoşullarımızı yerine getirdiğimize göre, süreci adım adım inceleyelim.

## 1. Adım: Belge Dizininizi Ayarlama

Kodlamaya başlamadan önce belge dizininizin yolunu ayarlamanız gerekir. Kaynak ve hedef belgelerinizin saklandığı yer burasıdır.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgelerinizin bulunduğu gerçek yolla. Bu, programın dosyalarınızı kolayca bulmasına yardımcı olacaktır.

## Adım 2: Kaynak ve Hedef Belgelerini Yükleme

Daha sonra çalışmak istediğimiz belgeleri yüklememiz gerekiyor. Bu örnekte bir kaynak belgemiz ve bir hedef belgemiz var.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

 Burada şunu kullanıyoruz:`Document` Belgelerimizi yüklemek için Aspose.Words kütüphanesinden sınıfa gidin. Dosya adlarının dizininizdeki adlarla eşleştiğinden emin olun.

## 3. Adım: DocumentBuilder Nesnesi Oluşturma

`DocumentBuilder` class, Aspose.Words kütüphanesindeki güçlü bir araçtır. Belgede gezinmemize ve düzenlememize olanak tanır.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

 Bu adımda bir oluşturduk`DocumentBuilder` Hedef belgemiz için nesne. Bu, belgeye içerik eklememize yardımcı olacaktır.

## Adım 4: Belgenin Sonuna Gitme

Kaynak belgeyi eklemeden önce oluşturucu imlecini hedef belgenin sonuna taşımamız gerekir.

```csharp
builder.MoveToDocumentEnd();
```

Bu, kaynak belgenin hedef belgenin sonuna eklenmesini sağlar.

## Adım 5: Sayfa Sonu Ekleme

İşleri düzenli tutmak için kaynak belgeyi eklemeden önce bir sayfa sonu ekleyelim. Bu, kaynak belgenin içeriğini yeni bir sayfada başlatacaktır.

```csharp
builder.InsertBreak(BreakType.PageBreak);
```

Sayfa sonu, kaynak belge içeriğinin yeni bir sayfada başlamasını sağlayarak birleştirilmiş belgenin profesyonel görünmesini sağlar.

## Adım 6: Kaynak Belgeyi Ekleme

Şimdi heyecan verici kısım geliyor; aslında kaynak belgeyi hedef belgeye eklemek.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

 Kullanmak`InsertDocument` yöntemiyle kaynak belgenin tamamını hedef belgeye ekleyebiliriz.`ImportFormatMode.KeepSourceFormatting` kaynak belgenin formatının korunmasını sağlar.

## Adım 7: Birleştirilmiş Belgeyi Kaydetme

Son olarak birleştirilmiş belgeyi kaydedelim. Bu, kaynak ve hedef belgeleri tek bir dosyada birleştirecektir.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Belgeyi kaydederek iki belgeyi birleştirme işlemini tamamlamış oluyoruz. Yeni belgeniz artık hazır ve belirtilen dizine kaydedildi.

## Çözüm

İşte buyur! Aspose.Words for .NET'i kullanarak bir belgeyi diğerine başarıyla eklediniz. Bu yöntem yalnızca verimli olmakla kalmaz, aynı zamanda her iki belgenin biçimlendirmesini de koruyarak kusursuz bir birleştirme sağlar. İster tek seferlik bir proje üzerinde çalışıyor olun ister belge işlemeyi otomatikleştirmeye ihtiyacınız olsun, Aspose.Words for .NET ihtiyacınızı karşılar.

## SSS'ler

### Aspose.Words for .NET nedir?  
Aspose.Words for .NET, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, düzenlemesine, dönüştürmesine ve işlemesine olanak tanıyan güçlü bir kitaplıktır.

### Kaynak belgenin biçimlendirmesini koruyabilir miyim?  
 Evet kullanarak`ImportFormatMode.KeepSourceFormatting`, kaynak belgenin biçimlendirmesi hedef belgeye eklendiğinde korunur.

### Aspose.Words for .NET'i kullanmak için lisansa ihtiyacım var mı?  
 Evet, Aspose.Words for .NET tam işlevsellik için lisans gerektirir. Alabilirsin[geçici lisans](https://purchase.aspose.com/temporary-license/) Evrim için.

### Bu işlemi otomatikleştirebilir miyim?  
Kesinlikle! Açıklanan yöntem, belge işleme görevlerini otomatikleştirmek için daha büyük uygulamalara dahil edilebilir.

### Daha fazla kaynak ve desteği nerede bulabilirim?  
Daha fazla bilgi için şurayı kontrol edebilirsiniz:[dokümantasyon](https://reference.aspose.com/words/net/) veya ziyaret edin[destek Forumu](https://forum.aspose.com/c/words/8) yardım için.