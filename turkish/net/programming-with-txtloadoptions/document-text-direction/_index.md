---
title: Belge Metin Yönü
linktitle: Belge Metin Yönü
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile belgelerinizde metin yönünü nasıl belirleyeceğinizi öğrenin. Sağdan sola yazılan diller için ekranı iyileştirin.
type: docs
weight: 10
url: /tr/net/programming-with-txtloadoptions/document-text-direction/
---

Bu öğreticide, Aspose.Words for .NET ile "Belge Metni Yönü" özelliği için sağlanan C# kaynak kodunu keşfedeceğiz. Bu özellik, özellikle İbranice veya Arapça gibi sağdan sola yazılan diller için kullanışlı olan bir belgedeki metnin yönünü belirlemenizi sağlar.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## 2. Adım: Yükleme seçeneklerini yapılandırma

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 Bu adımda, belge yükleme seçeneklerini yapılandırıyoruz. yeni bir tane yaratıyoruz`TxtLoadOptions` nesne ve ayarlayın`DocumentDirection` mülkiyet`DocumentDirection.Auto`. Bu değer, Aspose.Words'e belgenin içeriğine göre metin yönünü otomatik olarak belirlemesini söyler.

## 3. Adım: Belgeyi yükleme

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Bu adımda, kullanarak belgeyi yüklüyoruz`Document` yöntemi ve yolu yüklenecek metin dosyasına geçirme. Belirtilen yükleme seçeneklerini de kullanıyoruz.

## 4. Adım: Paragrafı değiştirin ve metin yönünü görüntüleyin

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 Bu adımda, kullanarak belgenin ilk paragrafına erişiyoruz.`FirstSection` Ve`Body` özellikler. Ardından,`ParagraphFormat.Bidi` özelliği paragrafın metin yönünü almak için. Daha sonra bu değeri konsolda gösteriyoruz.

## 5. Adım: Belgeyi kaydedin

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Bu son adımda, ortaya çıkan belgeyi kullanarak .docx formatında kaydediyoruz.`Save` yöntemi ve yolu çıktı dosyasına geçirme.

Artık metin belgesini yüklemek ve metin yönünü belirlemek için kaynak kodunu çalıştırabilirsiniz. Elde edilen belge belirtilen dizine "WorkingWithTxtLoadOptions.DocumentTextDirection.docx" adıyla kaydedilecektir.

### Aspose.Words for .NET ile belge metin yönü işlevselliği için örnek kaynak kodu.


```csharp

            
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET'teki belge metni yönü özelliğini inceledik. Özellikle İbranice veya Arapça gibi sağdan sola yazılan diller için bir belgedeki metnin yönünü nasıl belirleyeceğimizi öğrendik.

Bu özellik, metnin çok dilli belgelerde doğru şekilde görüntülenmesini sağlamak için gereklidir. Aspose.Words, uygun yükleme seçeneklerini kullanarak metnin yönünü otomatik olarak algılayabilir ve bunu belgeye uygulayabilir.

Aspose.Words ile belgelerinizdeki metnin yönünü kolayca değiştirebilir, kullanıcılara akıcı ve sezgisel bir okuma deneyimi sunabilirsiniz.

Bu özelliğin, özellikle belirli metin yönü gerektiren dillerle Sözcük İşleme yaparken kullanışlı olduğuna dikkat etmek önemlidir. Aspose.Words, belgelerinizdeki metnin yönünü yönetmek için güçlü araçlar sağlayarak bu görevi kolaylaştırır.

Belgelerinizde istediğiniz sonuçları elde etmek için otomatik metin yönünü ayarlamak gibi uygun yükleme seçeneklerini kullanmayı unutmayın.

Aspose.Words for .NET, belge işleme ve oluşturma için birçok gelişmiş özellik sunar. Aspose.Words tarafından sağlanan belgeleri ve örnekleri daha fazla keşfederek, bu güçlü kitaplığın yeteneklerinden tam anlamıyla yararlanabileceksiniz.

Bu nedenle, belge metni yönünü Aspose.Words for .NET projelerinize entegre etmekten çekinmeyin ve çekici ve yüksek kaliteli çok dilli belgeler oluşturmak için avantajlarından yararlanın.