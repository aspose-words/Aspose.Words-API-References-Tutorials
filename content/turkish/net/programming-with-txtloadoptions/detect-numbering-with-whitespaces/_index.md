---
title: Boşluklarla Numaralandırmayı Algıla
linktitle: Boşluklarla Numaralandırmayı Algıla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te boşluklu liste numaralarını nasıl tespit edeceğinizi öğrenin. Belgelerinizin yapısını kolaylıkla geliştirin.
type: docs
weight: 10
url: /tr/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
Bu eğitimde Aspose.Words for .NET ile "Boşluklarla numaralandırmanın tespiti" özelliği için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, liste numaralarını ve ardından beyaz boşlukları içeren bir metin belgesinden listeleri algılamanıza ve oluşturmanıza olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce Aspose.Words for .NET ile geliştirme ortamınızı kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## Adım 2: Metin belgesini oluşturma

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

Bu adımda, beyaz boşlukların takip ettiği liste numaralarını içeren bir metin belgesini simüle eden bir metin dizesi oluşturuyoruz. Nokta, sağ köşeli parantez, madde işareti simgesi ve beyaz boşluklar gibi farklı liste sınırlayıcıları kullanıyoruz.

## 3. Adım: Yükleme seçeneklerini yapılandırma

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 Bu adımda belge yükleme seçeneklerini yapılandırıyoruz. Yeni bir tane yaratıyoruz`TxtLoadOptions` nesneyi ayarlayın ve`DetectNumberingWithWhitespaces` mülkiyet`true`. Bu, Aspose.Words'ün, arkasında boşluklar olsa bile liste numaralarını algılamasına olanak tanır.

## Adım 4: Belgeyi yükleme ve kaydetme

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Bu adımda, belirtilen metin dizesini ve yükleme seçeneklerini kullanarak belgeyi yüklüyoruz. Bir kullanıyoruz`MemoryStream` metin dizesini bir bellek akışına dönüştürmek için. Daha sonra ortaya çıkan belgeyi .docx formatında kaydediyoruz.

### Aspose.Words for .NET ile Beyaz Boşluk Numaralandırma Algılama özelliği için örnek kaynak kodu.

```csharp

            
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Liste olarak yorumlanabilecek parçaları içeren bir dize biçiminde düz metin belgesi oluşturun.
// Yükleme sonrasında ilk üç liste her zaman Aspose.Words tarafından algılanacaktır.
// ve yükleme sonrasında onlar için List nesneleri oluşturulacaktır.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// Liste numarası ile liste öğesi içeriği arasında boşluk bulunan dördüncü liste,
// Yalnızca LoadOptions nesnesindeki "DetectNumberingWithWhitespaces" true olarak ayarlandığında liste olarak algılanacaktır,
// Sayılarla başlayan paragrafların yanlışlıkla liste olarak algılanmasını önlemek için.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// LoadOptions'ı parametre olarak uygularken belgeyi yükleyin ve sonucu doğrulayın.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Artık beyaz boşluklu liste numaralarını içeren metin belgesini yüklemek için kaynak kodunu çalıştırabilir ve ardından algılanan listelerle bir .docx belgesi oluşturabilirsiniz. Çıktı dosyası, "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx" adıyla belirtilen dizine kaydedilecektir.

## Çözüm
Bu eğitimde Aspose.Words for .NET'teki boşluk numaralandırma algılama özelliğini inceledik. Liste numaralarını ve ardından boşlukları içeren bir metin belgesinden listelerin nasıl oluşturulacağını öğrendik.

Bu özellik, farklı şekillerde biçimlendirilmiş liste numaralarını içeren belgeleri işlemek için son derece kullanışlıdır. Aspose.Words, uygun yükleme seçeneklerini kullanarak bu liste numaralarını, arkalarında beyaz boşluklar olsa bile algılayabilir ve bunları nihai belgede yapılandırılmış listelere dönüştürebilir.

Bu özelliği kullanmak size zaman kazandırabilir ve iş akışı verimliliğinizi artırabilir. Metin belgelerinden kolayca bilgi çıkarabilir ve bunları uygun listelerle iyi yapılandırılmış belgelere dönüştürebilirsiniz.

İstenilen sonuçları elde etmek için beyaz alan arama algılamasını yapılandırmak gibi yükleme seçeneklerini dikkate almayı unutmayın.

Aspose.Words for .NET, belge işleme ve oluşturma için birçok gelişmiş özellik sunar. Aspose.Words tarafından sağlanan belgeleri ve örnekleri daha fazla inceleyerek bu güçlü kütüphanenin özelliklerinden tam olarak yararlanabileceksiniz.

Bu nedenle, boşluk numaralandırma tespitini Aspose.Words for .NET projelerinize entegre etmekten çekinmeyin ve iyi yapılandırılmış ve okunabilir belgeler oluşturmak için bunun avantajlarından yararlanın.


