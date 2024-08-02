---
title: Word Belgesine Bidi İşaretleri Ekleme
linktitle: Word Belgesine Bidi İşaretleri Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Bu kılavuzla Aspose.Words for .NET kullanarak Word belgelerine çift yönlü (İki yönlü) işaretlerin nasıl ekleneceğini öğrenin. Çok dilli içerik için doğru metin yönünü sağlayın.
type: docs
weight: 10
url: /tr/net/programming-with-txtsaveoptions/add-bidi-marks/
---
## giriiş

Belge işleme dünyasında çift yönlü (İki yönlü) metnin yönetimi genellikle biraz zor olabilir. Bu özellikle Arapça veya İbranice gibi farklı metin yönlerine sahip dillerle uğraşırken geçerlidir. Neyse ki Aspose.Words for .NET bu tür senaryoların üstesinden gelmeyi kolaylaştırıyor. Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesine Bidi işaretlerinin nasıl ekleneceğini açıklayacağız.

## Önkoşullar

Koda dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olması gerekir. adresinden indirebilirsiniz.[İndirilenler sayfasını Aspose](https://releases.aspose.com/words/net/).
2. .NET Framework veya .NET Core: Örnekleri çalıştırmak için uyumlu bir .NET ortamınızın kurulu olduğundan emin olun.
3. Temel C# Bilgisi: C# programlama diline aşinalık ve .NET'teki temel işlemler.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını içe aktarmanız gerekir. Bunları projenize nasıl dahil edebileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Bir Word belgesine Bidi işaretlerini ekleme sürecini net adımlara ayıralım. Her adım size kod ve amacı konusunda rehberlik edecektir.

## 1. Adım: Belgenizi Ayarlayın

 Yeni bir örneğini oluşturarak başlayın`Document` sınıf ve bir`DocumentBuilder` Belgeye içerik eklemek için.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi oluşturun ve içerik ekleyin
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Bu adımda, yeni bir Word belgesini başlatacak ve bir`DocumentBuilder` İçerik eklemeyi kolaylaştırmak için.

## 2. Adım: Belgenize İçerik Ekleyin

Daha sonra belgenize bir miktar metin ekleyin. Burada Bidi metin kullanımını göstermek için farklı dillerdeki metinleri ekleyeceğiz.

```csharp
builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");
```

Burada öncelikle standart bir İngilizce ifade ekliyoruz. Daha sonra İbranice ve Arapça yazılan bir sonraki metin için Bidi metin formatını etkinleştiriyoruz. Bu, çift yönlü metnin nasıl dahil edileceğini gösterir.

## 3. Adım: Bidi İşaretleri için Kaydetme Seçeneklerini Yapılandırın

 Bidi işaretlerinin belgeye doğru şekilde kaydedildiğinden emin olmak için`TxtSaveOptions` ve etkinleştirin`AddBidiMarks` seçenek.

```csharp
// Bidi işaretleri ekleyin
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

 Bu adımda örneğini oluşturuyoruz.`TxtSaveOptions` ve ayarlayın`AddBidiMarks`mülkiyet`true`. Bu, belgeyi metin dosyası olarak kaydederken Bidi işaretlerinin dahil edilmesini sağlar.

## Çözüm

Bidi işaretlerini Word belgelerinize eklemek, farklı metin yönlerine sahip dilleri içeren çok dilli içerikle uğraşırken çok önemli bir adım olabilir. Aspose.Words for .NET ile bu süreç basit ve etkilidir. Yukarıda özetlenen adımları izleyerek belgelerinizin Bidi metnini doğru şekilde temsil etmesini sağlayarak okunabilirliği ve doğruluğu artırabilirsiniz.

## SSS'ler

### Bidi işaretleri nedir ve neden önemlidir?
Bidi işaretleri, belgelerdeki metnin yönünü kontrol etmek için kullanılan özel karakterlerdir. Arapça ve İbranice gibi sağdan sola okunan dillerin düzgün görüntülenmesi için gereklidirler.

### Aspose.Words for .NET'i diğer metin yönü sorunlarını çözmek için kullanabilir miyim?
Evet, Aspose.Words for .NET, sağdan sola ve soldan sağa diller de dahil olmak üzere çeşitli metin yönü ve formatlama ihtiyaçları için kapsamlı destek sağlar.

### Bidi biçimlendirmesini yalnızca belgenin belirli bölümlerine uygulamak mümkün mü?
Evet, Bidi biçimlendirmesini belgenizin belirli paragraflarına veya bölümlerine gerektiği gibi uygulayabilirsiniz.

### Belgeyi Bidi işaretleriyle hangi formatlarda kaydedebilirim?
Verilen örnekte belge bir metin dosyası olarak kaydedilmiştir. Ancak Aspose.Words, Bidi işaretlerini korurken belgelerin çeşitli formatlarda kaydedilmesini de destekler.

### Aspose.Words for .NET hakkında daha fazla bilgiyi nerede bulabilirim?
 Aspose.Words for .NET hakkında daha fazlasını şu adresten keşfedebilirsiniz:[Belgeleri Atayın](https://reference.aspose.com/words/net/) ve erişin[Destek Forumu](https://forum.aspose.com/c/words/8) ek yardım için.