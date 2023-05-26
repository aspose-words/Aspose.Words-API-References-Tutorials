---
title: Boşluklu Numaralandırmayı Algıla
linktitle: Boşluklu Numaralandırmayı Algıla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te beyaz boşluklu liste numaralarının nasıl algılanacağını öğrenin. Belgelerinizin yapısını kolaylıkla iyileştirin.
type: docs
weight: 10
url: /tr/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
Bu öğreticide, Aspose.Words for .NET ile "Beyaz boşluklarla numaralandırmanın algılanması" özelliği için sağlanan C# kaynak kodunu inceleyeceğiz. Bu özellik, liste numaralarını ve ardından beyaz boşlukları içeren bir metin belgesinden listeleri algılamanıza ve oluşturmanıza olanak tanır.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile kurduğunuzdan emin olun. Gerekli referansları eklediğinizden ve uygun ad alanlarını içe aktardığınızdan emin olun.

## 2. Adım: Metin belgesini oluşturma

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

Bu adımda, liste numaralarını ve ardından beyaz boşlukları içeren bir metin belgesini simüle eden bir metin dizesi yaratıyoruz. Nokta, sağ parantez, madde işareti simgesi ve beyaz boşluklar gibi farklı liste sınırlayıcıları kullanıyoruz.

## 3. Adım: Yükleme seçeneklerini yapılandırma

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 Bu adımda, belge yükleme seçeneklerini yapılandırıyoruz. yeni bir tane yaratıyoruz`TxtLoadOptions` nesne ve ayarlayın`DetectNumberingWithWhitespaces` mülkiyet`true`. Bu, Aspose.Words'ün liste numaralarını, ardından beyaz boşluklar gelse bile algılamasını sağlayacaktır.

## 4. Adım: Belgeyi yükleme ve kaydetme

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Bu adımda, belirtilen metin dizisini ve yükleme seçeneklerini kullanarak belgeyi yüklüyoruz. biz bir`MemoryStream` metin dizesini bir bellek akışına dönüştürmek için. Ardından ortaya çıkan belgeyi .docx formatında kaydediyoruz.

### Aspose.Words for .NET ile White Space Numbering Detection özelliği için örnek kaynak kodu.

```csharp

            
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Listeler olarak yorumlanabilecek bölümleri olan bir dize biçiminde bir düz metin belgesi oluşturun.
// Yüklemenin ardından ilk üç liste Aspose.Words tarafından her zaman algılanacaktır,
// ve yüklemeden sonra onlar için Liste nesneleri oluşturulacaktır.
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

// Liste numarası ile liste öğesi içerikleri arasında boşluk bulunan dördüncü liste,
// yalnızca bir LoadOptions nesnesindeki "DetectNumberingWithWhitespaces" true olarak ayarlanmışsa bir liste olarak algılanır,
// sayılarla başlayan paragrafların yanlışlıkla liste olarak algılanmasını önlemek için.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// LoadOptions'ı parametre olarak uygularken belgeyi yükleyin ve sonucu doğrulayın.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Artık liste numaralarını içeren metin belgesini beyaz boşluklarla yüklemek için kaynak kodunu çalıştırabilir, ardından algılanan listelerle bir .docx belgesi oluşturabilirsiniz. Çıktı dosyası belirtilen dizine "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx" adıyla kaydedilecektir.

## Çözüm
Bu öğreticide, Aspose.Words for .NET'teki boşluk numaralandırma algılama özelliğini inceledik. Liste numaralarını ve ardından beyaz boşlukları içeren bir metin belgesinden listelerin nasıl oluşturulacağını öğrendik.

Bu özellik, farklı şekillerde biçimlendirilmiş liste numaraları içeren belgeleri işlemek için son derece kullanışlıdır. Aspose.Words, uygun yükleme seçeneklerini kullanarak, bu liste numaralarını, ardından beyaz boşluklar gelse bile algılayabilir ve bunları nihai belgede yapılandırılmış listelere dönüştürebilir.

Bu özelliği kullanmak size zaman kazandırabilir ve iş akışı verimliliğinizi artırabilir. Metin belgelerinden kolayca bilgi çıkarabilir ve bunları uygun listelerle iyi yapılandırılmış belgelere dönüştürebilirsiniz.

İstenen sonuçları elde etmek için boşluk çevirme algılamayı yapılandırma gibi yükleme seçeneklerini göz önünde bulundurmayı unutmayın.

Aspose.Words for .NET, belge işleme ve oluşturma için birçok gelişmiş özellik sunar. Aspose.Words tarafından sağlanan belgeleri ve örnekleri daha fazla keşfederek, bu güçlü kitaplığın yeteneklerinden tam anlamıyla yararlanabileceksiniz.

Bu nedenle, boşluk numaralandırma tespitini Aspose.Words for .NET projelerinize entegre etmekten çekinmeyin ve iyi yapılandırılmış ve okunabilir belgeler oluşturmak için onun avantajlarından yararlanın.


