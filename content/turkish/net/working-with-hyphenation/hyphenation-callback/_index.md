---
title: Tireleme Geri Çağırma
linktitle: Tireleme Geri Çağırma
second_title: Aspose.Words Belge İşleme API'si
description: Kelime tireleme işlemini gerçekleştirmek için Aspose.Words for .NET'te tireleme geri çağırmanın nasıl kullanılacağını öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-hyphenation/hyphenation-callback/
---

Bu adım adım eğitimde Aspose.Words for .NET'te tireleme geri çağırma özelliğinin nasıl kullanılacağını göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin:[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. Adım: Tireleme Hatırlatıcısını Kaydet

 İlk olarak, tireleme geri çağrısını özel bir kullanarak kaydedeceğiz.`CustomHyphenationCallback` sınıf. Bu, kelime tirelemesini kendi kurallarımıza göre yapmamızı sağlayacaktır:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Aşağıdakileri uyguladığınızdan emin olun:`CustomHyphenationCallback` özel ihtiyaçlarınıza göre sınıf.

## 2. Adım: Belgeyi yükleme ve tireleme uygulama

Daha sonra, belgenizi belirtilen dizinden yükleyin ve Aspose.Words'ü kullanarak sözcükleri tireleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## 3. Adım: Eksik Sözlük Hatalarını Ele Alma

Bir tireleme sözlüğünün eksik olması durumunda, ilgili istisnayı yakalayacağız ve bir hata mesajı görüntüleyeceğiz:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Adım 4: Tireleme Hatırlatıcısını Temizleme ve Devre Dışı Bırakma

Son olarak temizlik ve tireleme hatırlatıcısını kapatmak için aşağıdaki adımları uygulayın:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Bu, işlem tamamlandıktan sonra tireleme hatırlatıcısını temizler ve devre dışı bırakır.

Bu yüzden ! Aspose.Words for .NET'te tireleme geri çağrısını başarıyla kullandınız.

### Aspose.Words for .NET ile Tireleme Geri Çağırma için Örnek Kaynak Kodu

```csharp
try
{
	 // Tireleme geri aramasını kaydedin.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Bu kodu kendi projelerinizde kullanmaktan ve özel ihtiyaçlarınıza uyacak şekilde değiştirmekten çekinmeyin.

### SSS'ler

#### S: Aspose.Words'te heceleme hatırlatıcısı nedir?

C: Aspose.Words'teki Heceleme Hatırlatıcısı, belgelerinizde kelimelerin hecelenme şeklini özelleştirmenize olanak tanıyan bir özelliktir. Bir heceleme hatırlatıcısı kullanarak, kelimelerin hecelenmesi için özel kurallar belirleyebilirsiniz; bu, belirli diller veya varsayılan hecelemenin istenen sonuçları vermediği belirli senaryolar için faydalı olabilir.

#### S: Aspose.Words'te heceleme hatırlatıcısı nasıl ayarlanır?

 C: Aspose.Words'te tireleme geri çağrısı tanımlamak için, bunu uygulayan bir sınıf oluşturmanız gerekir.`HyphenationCallback` arayüzü oluşturun ve uygulayın`HandleWord()` yöntem. Heceleme sırasında karşılaşılan her kelime için bu yöntem çağrılacaktır. Özel heceleme kurallarını ona uygulayabilir ve hecelenmiş kelimeyi döndürebilirsiniz. Daha sonra tireleme geri aramanızı aşağıdaki komutu kullanarak bağlayabilirsiniz:`Document.HyphenationCallback` belgenizin mülkiyetindedir.

#### S: Aspose.Words'te heceleme hatırlatıcısı kullanmanın avantajı nedir?

C: Aspose.Words'te heceleme hatırlatıcısı kullanmanın faydası, belgelerinizde kelimelerin hecelenme şeklini özelleştirebilme yeteneğidir. Bu, özellikle varsayılan hecelemenin istenen sonuçları vermediği belirli diller veya senaryolar için heceleme üzerinde daha fazla kontrol sahibi olmanızı sağlar. İhtiyaçlarınıza göre kesin heceleme elde etmek için her kelimeye özel kurallar uygulayabilirsiniz.

#### S: Heceleme hatırlatıcısı kullanmanın yararlı olabileceği bazı yaygın senaryolar nelerdir?

C: Heceleme güçlendirici kullanmak aşağıdakiler gibi çeşitli senaryolarda faydalı olabilir:
- Belirli heceleme kurallarına sahip belirli dillerdeki kelimelerin hecelenmesi.
- Kısaltmalar veya teknik kelimeler için kişiselleştirilmiş heceleme kurallarının uygulanması.
- Hecelemenin stilistik tercihlere veya tipografik standartlara göre uyarlanması.

#### S: Aspose.Words'te özel hecelemeyi bir heceleme hatırlatıcısıyla nasıl test edebilirim?

 C: Aspose.Words'te özel hecelemeyi bir heceleme hatırlatıcısıyla test etmek için, özel heceleme kurallarını uygulamak istediğiniz kelimeleri içeren bir test belgesi oluşturabilirsiniz. Daha sonra özel heceleme geri aramanızı ayarlayabilir,`Document.Range.Replace()` belgedeki sözcükleri değiştirme yöntemini kullanın ve`Hyphenate()` yöntemi`Hyphenation` Kelimelerin hecelemesini almak için sınıf. Daha sonra hecelenmiş sözcükleri gerektiği gibi biçimlendirebilirsiniz; örneğin hecelerin arasına kısa çizgi ekleyerek.