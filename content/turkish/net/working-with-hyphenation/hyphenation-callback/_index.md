---
title: Tireleme Geri Çağırma
linktitle: Tireleme Geri Çağırma
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı adım adım kılavuzla belge formatını geliştirmek için Aspose.Words for .NET'te tireleme geri çağırmayı uygulamayı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-hyphenation/hyphenation-callback/
---

## giriiş

Selam! Özellikle tireleme gerektiren dillerle uğraşırken kendinizi hiç metin biçimlendirmenin karmaşıklığı içinde buldunuz mu? Yalnız değilsin. Tireleme, doğru metin düzeni için çok önemli olsa da biraz baş ağrısı olabilir. Ama tahmin et ne oldu? Aspose.Words for .NET arkanızı kolluyor. Bu güçlü kitaplık, bir geri çağırma mekanizması yoluyla tirelemeyi yönetmek de dahil olmak üzere, metin biçimlendirmesini sorunsuz bir şekilde yönetmenize olanak tanır. İlginizi mi çekti? Aspose.Words for .NET'i kullanarak tireleme geri çağrısını nasıl uygulayabileceğinizi en ince ayrıntısına kadar inceleyelim.

## Önkoşullar

Kodlarla elimizi kirletmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1. Aspose.Words for .NET: Kitaplığa sahip olduğunuzdan emin olun. Yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
2. IDE: Visual Studio gibi bir geliştirme ortamı.
3. Temel C# Bilgisi: C# ve .NET çerçevesinin anlaşılması.
4. Tireleme Sözlükleri: Kullanmayı planladığınız diller için tireleme sözlükleri.
5.  Aspose Lisansı: Geçerli bir Aspose lisansı. Alabilirsin[geçici lisans](https://purchase.aspose.com/temporary-license/) eğer sende yoksa.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu, kodumuzun Aspose.Words'ten ihtiyacımız olan tüm sınıflara ve yöntemlere erişebilmesini sağlar.

```csharp
using Aspose.Words;
using System;
using System.IO;
```

## Adım 1: Tireleme Geri Aramasını Kaydedin

Başlamak için tireleme geri çağrımızı kaydetmemiz gerekiyor. Aspose.Words'e özel tireleme mantığımızı kullanmasını söylediğimiz yer burasıdır.

```csharp
try
{
    // Tireleme geri aramasını kaydedin.
    Hyphenation.Callback = new CustomHyphenationCallback();
}
catch (Exception e)
{
    Console.WriteLine($"Error registering hyphenation callback: {e.Message}");
}
```

 Burada özel geri aramamızın bir örneğini oluşturuyoruz ve onu`Hyphenation.Callback`.

## Adım 2: Belge Yolunu Tanımlayın

Daha sonra belgelerimizin saklandığı dizini tanımlamamız gerekiyor. Belgeleri bu yoldan yükleyip kaydedeceğimiz için bu çok önemlidir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgelerinizin gerçek yolu ile.

## 3. Adım: Belgeyi Yükleyin

Şimdi tireleme gerektiren belgeyi yükleyelim.

```csharp
Document document = new Document(dataDir + "German text.docx");
```

Burada Almanca bir metin belgesi yüklüyoruz. Değiştirebilirsin`"German text.docx"` belgenizin dosya adıyla birlikte.

## Adım 4: Belgeyi Kaydedin

Belgeyi yükledikten sonra, süreçte tireleme geri çağrısını uygulayarak onu yeni bir dosyaya kaydediyoruz.

```csharp
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

Bu satır, belgeyi tireleme uygulanmış bir PDF olarak kaydeder.

## Adım 5: Eksik Tireleme Sözlüğü İstisnasını Ele Alın

Bazen tireleme sözlüğünün eksik olduğu bir sorunla karşılaşabilirsiniz. Bunu halledelim.

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
    Console.WriteLine(e.Message);
}
finally
{
    Hyphenation.Callback = null;
}
```

Bu blokta eksik sözlüklerle ilgili özel istisnayı yakalayıp mesajı yazdırıyoruz.

## Adım 6: Özel Tireleme Geri Çağırma Sınıfını Uygulama

 Şimdi işlemleri uygulayalım`CustomHyphenationCallback` Tireleme sözlükleri talebini işleyen sınıf.

```csharp
public class CustomHyphenationCallback : IHyphenationCallback
{
    public void RequestDictionary(string language)
    {
        string dictionaryFolder = MyDir;
        string dictionaryFullFileName;
        switch (language)
        {
            case "en-US":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_en_US.dic");
                break;
            case "de-CH":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_de_CH.dic");
                break;
            default:
                throw new Exception($"Missing hyphenation dictionary for {language}.");
        }
        // İstenilen dil için sözlüğü kaydedin.
        Hyphenation.RegisterDictionary(language, dictionaryFullFileName);
    }
}
```

 Bu sınıfta,`RequestDictionary` bir tireleme sözlüğüne ihtiyaç duyulduğunda yöntem çağrılır. Dili kontrol eder ve uygun sözlüğü kaydeder.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'te tireleme geri çağrısının nasıl uygulanacağını öğrendiniz. Bu adımları izleyerek, dilden bağımsız olarak belgelerinizin güzel bir şekilde biçimlendirilmesini sağlayabilirsiniz. İster İngilizce, Almanca veya başka bir dille çalışıyor olun, bu yöntem tirelemeyi zahmetsizce halletmenize olanak tanır.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin belgeleri programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir belge işleme kitaplığıdır.

### Belge biçimlendirmesinde tireleme neden önemlidir?
Tireleme, kelimeleri uygun yerlerde bölerek metin düzenini iyileştirir, daha okunaklı ve görsel olarak daha çekici bir belge sağlar.

### Aspose.Words'ü ücretsiz kullanabilir miyim?
 Aspose.Words ücretsiz deneme olanağı sunuyor. Alabilirsin[Burada](https://releases.aspose.com/).

### Tireleme sözlüğünü nasıl edinebilirim?
Çeşitli çevrimiçi kaynaklardan tireleme sözlükleri indirebilir veya gerekirse kendinizinkini oluşturabilirsiniz.

### Bir tireleme sözlüğü eksikse ne olur?
 Bir sözlük eksikse,`RequestDictionary`yöntem, kullanıcıyı bilgilendirmek veya bir geri dönüş sağlamak için kullanabileceğiniz bir istisna atar.