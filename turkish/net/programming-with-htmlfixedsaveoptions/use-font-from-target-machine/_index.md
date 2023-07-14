---
title: Hedef Makineden Yazı Tipi Kullan
linktitle: Hedef Makineden Yazı Tipi Kullan
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile hedef makinenin yazı tiplerini kullanarak bir Word belgesini sabit HTML'ye nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Bir C# uygulamasında bir Word belgesini sabit HTML'ye dönüştürürken, işlenen HTML'nin belgenin orijinal görünümünü ve stilini koruduğundan emin olmak için hedef makinenin yazı tiplerini kullanmak isteyebilirsiniz. .NET için Aspose.Words kitaplığıyla, HtmlFixedSaveOptions kaydetme seçeneklerini kullanarak bu işlevselliği kolayca belirleyebilirsiniz. Bu adım adım kılavuzda, HtmlFixedSaveOptions kullanarak hedef makinenin yazı tiplerini kullanarak bir Word belgesini sabit HTML'ye dönüştürmek için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## Word belgesini yükleme

İlk adım, sabit HTML'ye dönüştürmek istediğiniz Word belgesini yüklemektir. Belgeyi kaynak dosyadan yüklemek için Document sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

Bu örnekte, belgeler dizininde bulunan "Alternatif font.docx ile madde işaretleri" belgesini yüklüyoruz.

## Yedekleme seçeneklerini yapılandırma

Bir sonraki adım, sabit HTML'ye dönüştürmek için kaydetme seçeneklerini yapılandırmaktır. Aspose.Words'e hedef makineden yazı tiplerini kullanmasını söylemek için HtmlFixedSaveOptions sınıfını kullanın ve UseTargetMachineFonts özelliğini true olarak ayarlayın. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Yeni bir HtmlFixedSaveOptions nesnesi oluşturuyoruz ve dönüştürme sırasında hedef makinenin yazı tiplerini kullanmak için UseTargetMachineFonts özelliğini true olarak ayarlıyoruz.

## Sabit HTML belgesi dönüştürme

Artık kaydetme seçeneklerini yapılandırdığımıza göre, belgeyi sabit HTML'ye dönüştürmeye devam edebiliriz. Kaydetme seçeneklerini belirterek dönüştürülen belgeyi sabit HTML biçiminde kaydetmek için Document sınıfının Save yöntemini kullanın. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

Bu örnekte, dönüştürülen belgeyi belirtilen kaydetme seçeneklerini kullanarak "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" olarak kaydediyoruz.

### Aspose.Words for .NET kullanan "Hedef makinedeki yazı tiplerini kullan" özelliğine sahip HtmlFixedSaveOptions için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word belgesini yükleyin
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// "Hedef makinedeki yazı tiplerini kullan" özelliğiyle yedekleme seçeneklerini yapılandırın
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Belgeyi sabit HTML'ye dönüştürün
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kitaplığı ile hedef makinenin yazı tiplerini kullanarak bir Word belgesini sabit HTML'ye nasıl dönüştüreceğinizi açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Hedef makinenin yazı tipleriyle sabit HTML'ye dönüştürme, belgenin bir HTML biçiminde aslına uygun ve tutarlı bir şekilde oluşturulmasını garanti eder.
