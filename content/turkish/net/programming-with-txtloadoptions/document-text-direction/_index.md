---
title: Belge Metni Yönü
linktitle: Belge Metni Yönü
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belgelerinizdeki metin yönünü nasıl belirleyeceğinizi öğrenin. Sağdan sola yazılan diller için ekranı iyileştirin.
type: docs
weight: 10
url: /tr/net/programming-with-txtloadoptions/document-text-direction/
---

Bu eğitimde Aspose.Words for .NET ile "Belge Metni Yönü" özelliği için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgedeki metnin yönünü belirtmenize olanak tanır; bu, özellikle İbranice veya Arapça gibi sağdan sola yazılan diller için kullanışlıdır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce Aspose.Words for .NET ile geliştirme ortamınızı kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## 2. Adım: Yükleme seçeneklerini yapılandırma

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 Bu adımda belge yükleme seçeneklerini yapılandırıyoruz. Yeni bir tane yaratıyoruz`TxtLoadOptions` nesneyi ayarlayın ve`DocumentDirection` mülkiyet`DocumentDirection.Auto`. Bu değer Aspose.Words'e belgenin içeriğine göre metnin yönünü otomatik olarak belirlemesini söyler.

## 3. Adım: Belgeyi yükleme

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Bu adımda belgeyi aşağıdaki komutu kullanarak yüklüyoruz:`Document` yöntemi ve yüklenecek metin dosyasının yolunu iletme. Belirtilen yükleme seçeneklerini de kullanıyoruz.

## Adım 4: Paragrafı düzenleyin ve metnin yönünü görüntüleyin

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 Bu adımda belgenin ilk paragrafına şu komutu kullanarak erişiyoruz:`FirstSection` Ve`Body` özellikler. Daha sonra şuraya erişiyoruz:`ParagraphFormat.Bidi` Paragrafın metin yönünü alma özelliği. Daha sonra bu değeri konsolda gösteriyoruz.

## 5. Adım: Belgeyi kaydedin

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Bu son adımda, ortaya çıkan belgeyi kullanarak .docx formatında kaydediyoruz.`Save` yöntemi ve yolu çıktı dosyasına geçirme.

Artık metin belgesini yüklemek ve metnin yönünü belirlemek için kaynak kodunu çalıştırabilirsiniz. Ortaya çıkan belge, "WorkingWithTxtLoadOptions.DocumentTextDirection.docx" adıyla belirtilen dizine kaydedilecektir.

### Aspose.Words for .NET ile belge metni yönlendirme işlevi için örnek kaynak kodu.


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

Bu eğitimde Aspose.Words for .NET'teki belge metni yönü özelliğini inceledik. Özellikle İbranice veya Arapça gibi sağdan sola yazılan dillerde, bir belgedeki metnin yönünü nasıl belirleyeceğimizi öğrendik.

Bu özellik, metnin çok dilli belgelerde doğru şekilde görüntülenmesini sağlamak için gereklidir. Aspose.Words, uygun yükleme seçeneklerini kullanarak metnin yönünü otomatik olarak algılayabilir ve bunu belgeye uygulayabilir.

Aspose.Words ile belgelerinizdeki metnin yönünü kolayca değiştirebilir, kullanıcılara sorunsuz ve sezgisel bir okuma deneyimi sunabilirsiniz.

Bu özelliğin özellikle belirli metin yönü gerektiren dillerde Kelime İşleme yaparken kullanışlı olduğunu unutmamak önemlidir. Aspose.Words, belgelerinizdeki metnin yönünü yönetmek için güçlü araçlar sağlayarak bu görevi kolaylaştırır.

Belgelerinizde istediğiniz sonuçları elde etmek için otomatik metin yönünü ayarlama gibi uygun yükleme seçeneklerini kullanmayı unutmayın.

Aspose.Words for .NET, belge işleme ve oluşturma için birçok gelişmiş özellik sunar. Aspose.Words tarafından sağlanan belgeleri ve örnekleri daha fazla inceleyerek bu güçlü kütüphanenin özelliklerinden tam olarak yararlanabileceksiniz.

Bu nedenle, belge metni yönünü Aspose.Words for .NET projelerinize entegre etmekten çekinmeyin ve ilgi çekici ve yüksek kalitede çok dilli belgeler oluşturmak için bunun avantajlarından yararlanın.