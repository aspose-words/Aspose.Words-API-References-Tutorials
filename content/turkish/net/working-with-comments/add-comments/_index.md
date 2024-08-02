---
title: Yorum ekle
linktitle: Yorum ekle
second_title: Aspose.Words Belge İşleme API'si
description: Rehberimizi kullanarak Aspose.Words for .NET'i kullanarak Word belgelerinize nasıl yorum ekleyeceğinizi öğrenin. Belge işbirliği sürecinizi zahmetsizce geliştirin.
type: docs
weight: 10
url: /tr/net/working-with-comments/add-comments/
---
## giriiş

Aspose.Words for .NET kullanarak Word belgelerinize yorum eklemeyle ilgili ayrıntılı kılavuzumuza hoş geldiniz! Yorumları programlı bir şekilde dahil ederek belge inceleme sürecinizi kolaylaştırmak istiyorsanız doğru yere geldiniz. Bu eğitim, ortamınızı ayarlamaktan Word belgelerinize yorum yazmaya ve kaydetmeye kadar bilmeniz gereken her şeyde size yol gösterecektir. Haydi hemen konuya dalalım ve belge işbirliğini çocuk oyuncağı haline getirelim!

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olması gerekir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
2. .NET Framework: Makinenizde .NET Framework'ün kurulu olduğundan emin olun.
3. Geliştirme Ortamı: Kodunuzu yazmak ve yürütmek için Visual Studio benzeri bir IDE.
4. Temel C# Bilgisi: C# programlama diline aşinalık, örnekleri takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını projenize aktarmanız gerekir. Bu, Aspose.Words ile çalışmak için gereken sınıflara ve yöntemlere erişmenizi sağlayacaktır.

```csharp
using System;
using Aspose.Words;
```

Şimdi süreci takip edilmesi kolay adımlara ayıralım. Her adımda mantığı ve işlevselliği anlamanıza yardımcı olacak ayrıntılı bir açıklama yer alacaktır.

## 1. Adım: Belge Dizininizi Kurun

 Öncelikle belgenizin kaydedileceği dizini tanımlamamız gerekiyor. Bir yer tutucu kullanacağız`YOUR DOCUMENT DIRECTORY` bunu gerçek dizin yolunuzla değiştirmeniz gerekir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Başlatın

Daha sonra yeni bir belge ve DocumentBuilder nesnesini başlatacağız. DocumentBuilder belgeyi oluşturmamıza ve değiştirmemize yardımcı olur.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Belgeye Metin Ekleme

DocumentBuilder'ı kullanarak belgeye bir miktar metin ekleyeceğiz. Bu metin yorumumuzu ekleyeceğimiz yer olacaktır.

```csharp
builder.Write("Some text is added.");
```

## 4. Adım: Yorum Oluşturun ve Ekleyin

Şimdi yorum oluşturmanın zamanı geldi. Belgeyi, yazarın adını, baş harflerini ve tarihi belirterek yeni bir Yorum nesnesini başlatacağız.

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

## Adım 5: Yorumu Paragrafa Eklemek

Yorumu metni eklediğimiz mevcut paragrafa eklememiz gerekiyor. Bu, yorumun paragrafa eklenmesiyle yapılır.

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

## 6. Adım: Yoruma İçerik Ekleyin

Son olarak yoruma içerik ekleyeceğiz. Yorum metnini tutmak için yeni bir Paragraf ve Çalıştır oluşturacağız, ardından bunları yoruma ekleyeceğiz.

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Adım 7: Belgeyi Kaydedin

Son adım, belgeyi yorumlarla birlikte kaydetmektir. Dizini ve dosya adını belirteceğiz.

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Çözüm

İşte aldın! Aspose.Words for .NET'i kullanarak bir Word belgesine başarıyla yorum eklediniz. Bu güçlü özellik, belge inceleme sürecinizi büyük ölçüde geliştirebilir, işbirliği yapmayı ve geri bildirimde bulunmayı kolaylaştırabilir. Belge yönetimi görevlerinizi daha da kolaylaştırmak için Aspose.Words'ün diğer özelliklerini keşfetmeyi unutmayın.

## SSS'ler

### Aspose.Words for .NET nedir?

Aspose.Words for .NET, geliştiricilerin .NET dillerini kullanarak Word belgelerini programlı olarak oluşturmasına, yönetmesine ve dönüştürmesine olanak tanıyan güçlü bir API'dir.

### Tek bir belgeye birden fazla yorum ekleyebilir miyim?

Evet, farklı paragraflara veya metin dizilerine yorum oluşturma ve ekleme işlemini tekrarlayarak tek bir belgeye birden fazla yorum ekleyebilirsiniz.

### Yorumların görünümünü nasıl özelleştirebilirim?

Aspose.Words yorumların içeriğine ve yapısına odaklanırken görünüm, Word'ün yerleşik biçimlendirme özellikleri kullanılarak özelleştirilebilir.

### Yorumları programlı olarak kaldırmak mümkün mü?

Evet, belgedeki yorumları yineleyerek ve gerektiğinde kaldırarak yorumları programlı bir şekilde kaldırabilirsiniz.

### Yorumlara yanıt ekleyebilir miyim?

Aspose.Words, zincir halindeki yorumlarla çalışmanıza olanak tanıyarak, daha ayrıntılı tartışmalar için mevcut yorumlara yanıtlar eklemenizi sağlar.