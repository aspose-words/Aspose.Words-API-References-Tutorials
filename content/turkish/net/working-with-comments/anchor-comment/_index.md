---
title: Bağlantı Yorumu
linktitle: Bağlantı Yorumu
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerine nasıl bağlantı yorumları ekleyeceğinizi öğrenin. Verimli belge işbirliği için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/working-with-comments/anchor-comment/
---
## giriiş

Hiç kendinizi bir Word belgesindeki belirli metin bölümlerine programlı olarak yorum eklemeniz gereken bir durumda buldunuz mu? Ekibinizle bir belge üzerinde işbirliği yaptığınızı ve diğerlerinin incelemesi için belirli bölümleri yorumlarla vurgulamanız gerektiğini düşünün. Bu eğitimde, Aspose.Words for .NET kullanarak Word belgelerine bağlantı yorumlarının nasıl ekleneceğini derinlemesine inceleyeceğiz. Süreci basit adımlara bölerek takip etmenizi ve projelerinizde uygulamanızı kolaylaştıracağız.

## Önkoşullar

Başlamadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

-  Aspose.Words for .NET: Aspose.Words kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio gibi herhangi bir .NET geliştirme ortamı.
- Temel C# Anlayışı: C# programlamaya aşinalık, adımları kolayca takip etmenize yardımcı olacaktır.

Şimdi bu görev için içe aktarmanız gereken ad alanlarına bakalım.

## Ad Alanlarını İçe Aktar

Başlangıç olarak projenize gerekli ad alanlarını içe aktardığınızdan emin olun. Gerekli ad alanları şunlardır:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.CommentRangeStart;
using Aspose.Words.CommentRangeEnd;
```

Önkoşulları ve ad alanlarını bir kenara bırakın, hadi işin eğlenceli kısmına geçelim: Süreci adım adım parçalara ayıralım.

## 1. Adım: Yeni Bir Belge Oluşturun

Öncelikle yeni bir Word belgesi oluşturalım. Bu bizim yorumlarımız için tuval görevi görecek.

```csharp
// Belgenin kaydedileceği dizini tanımlayın
string dataDir = "YOUR DOCUMENT DIRECTORY";        

// Document sınıfının bir örneğini oluşturun
Document doc = new Document();
```

 Bu adımda yeni bir başlangıç başlatıyoruz.`Document` Yorumlarımızı eklemek için kullanılacak nesne.

## 2. Adım: Belgeye Metin Ekleme

Daha sonra belgeye bir miktar metin ekleyeceğiz. Bu metin yorumlarımızın hedefi olacaktır.

```csharp
// İlk paragrafı oluşturun ve çalıştırın
Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

// İkinci paragrafı oluşturun ve çalıştırın
Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

 Burada, bir miktar metin içeren iki paragraf oluşturuyoruz. Her metin parçası bir kapsül içine alınır`Run` daha sonra paragraflara eklenen nesne.

## 3. Adım: Yorum Oluşturun

Şimdi metnimize ekleyeceğimiz bir yorum oluşturalım.

```csharp
// Yeni bir Yorum oluştur
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

 Bu adımda bir oluşturuyoruz.`Comment` nesneyi seçin ve yorum metniyle birlikte bir paragraf ve bir çalıştırma ekleyin.

## Adım 4: Yorum Aralığını Tanımlayın

Yorumu belirli bir metne bağlamak için yorum aralığının başlangıcını ve bitişini tanımlamamız gerekir.

```csharp
// CommentRangeStart ve CommentRangeEnd'i tanımlayın
CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

// CommentRangeStart ve CommentRangeEnd'i belgeye ekleyin
run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);

// Yorumu belgeye ekleyin
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

 Burada, yaratıyoruz`CommentRangeStart`Ve`CommentRangeEnd` nesneleri, bunları kimliğine göre yoruma bağlar. Daha sonra bu aralıkları belgeye ekleyerek yorumumuzu belirtilen metne etkili bir şekilde sabitliyoruz.

## Adım 5: Belgeyi Kaydedin

Son olarak belgemizi belirtilen dizine kaydedelim.

```csharp
// Belgeyi kaydet
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

Bu adım, bağlantılı yorumu içeren belgeyi belirttiğiniz dizine kaydeder.

## Çözüm

İşte buyur! Aspose.Words for .NET'i kullanarak bir Word belgesindeki belirli metin bölümlerine bağlantı yorumlarının nasıl ekleneceğini başarıyla öğrendiniz. Bu teknik, belge işbirliği için son derece kullanışlıdır ve metnin belirli bölümlerini kolayca vurgulamanıza ve bunlara yorum yapmanıza olanak tanır. İster ekibinizle birlikte bir proje üzerinde çalışıyor olun ister belgeleri inceliyor olun, bu yöntem üretkenliğinizi artıracak ve iş akışınızı kolaylaştıracaktır.

## SSS'ler

### Word belgelerinde bağlantı yorumlarını kullanmanın amacı nedir?
Bağlantı yorumları, metnin belirli bölümlerini vurgulamak ve bunlara yorum yapmak için kullanılır; böylece geri bildirim sağlamayı ve belgeler üzerinde işbirliği yapmayı kolaylaştırır.

### Aynı metin bölümüne birden fazla yorum ekleyebilir miyim?
Evet, birden fazla yorum aralığı tanımlayarak aynı metin bölümüne birden fazla yorum ekleyebilirsiniz.

### Aspose.Words for .NET'in kullanımı ücretsiz mi?
Aspose.Words for .NET, indirebileceğiniz ücretsiz bir deneme sürümü sunuyor[Burada](https://releases.aspose.com/) . Tüm özellikler için lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).

### Yorumların görünümünü özelleştirebilir miyim?
Aspose.Words işlevselliğe odaklanırken, Word belgelerindeki yorumların görünümü genellikle Word'ün kendisi tarafından kontrol edilir.

### Aspose.Words for .NET hakkında daha fazla belgeyi nerede bulabilirim?
 Ayrıntılı belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).