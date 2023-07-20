---
title: Tireleme Geri Çağırma
linktitle: Tireleme Geri Çağırma
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'te sözcük hecelemesini işlemek için heceleme geri aramasını nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-hyphenation/hyphenation-callback/
---

Bu adım adım öğreticide, size Aspose.Words for .NET'te heceleme geri arama özelliğini nasıl kullanacağınızı göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı adresinden indirip yükleyin.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. Adım: Tireleme Hatırlatıcısını Kaydet

İlk olarak, özel bir kullanarak heceleme geri aramasını kaydedeceğiz.`CustomHyphenationCallback` sınıf. Bu, kelime hecelemesini kendi kurallarımıza göre ele almamıza izin verecektir:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 uyguladığınızdan emin olun.`CustomHyphenationCallback` özel ihtiyaçlarınıza göre sınıflandırın.

## 2. Adım: Belgeyi yükleme ve tireleme uygulama

Ardından, belgenizi belirtilen dizinden yükleyin ve Aspose.Words'ü kullanarak kelimeleri tireleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## 3. Adım: Eksik Sözlük Hatalarını Ele Alma

Bir heceleme sözlüğünün eksik olması durumunda ilgili istisnayı yakalarız ve bir hata mesajı görüntüleriz:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## 4. Adım: Tireleme Hatırlatıcısını Temizleyin ve Devre Dışı Bırakın

Son olarak, temizlik için ve tireleme hatırlatıcısını kapatmak için aşağıdaki adımları gerçekleştirin:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Bu, işlemeyi bitirdikten sonra tireleme hatırlatıcısını temizler ve devre dışı bırakır.

Bu yüzden ! Aspose.Words for .NET'te heceleme geri aramasını başarıyla kullandınız.

### Aspose.Words for .NET ile Tireleme Geri Araması için Örnek Kaynak Kodu

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

### SSS

#### S: Aspose.Words'ta heceleme hatırlatıcısı nedir?

C: Aspose.Words'taki Heceleme Hatırlatıcısı, sözcüklerin belgelerinizde nasıl hecelendiğini özelleştirmenizi sağlayan bir özelliktir. Bir heceleme hatırlatıcısı kullanarak, sözcüklerin hecelenmesi için özel kurallar belirleyebilirsiniz; bu, belirli diller için veya varsayılan hecelemenin istenen sonuçları vermediği belirli senaryolar için yararlı olabilir.

#### S: Aspose.Words'ta bir heceleme hatırlatıcısı nasıl ayarlanır?

 A: Aspose.Words'te bir heceleme geri araması tanımlamak için,`HyphenationCallback` arayüz ve uygulama`HandleWord()` yöntem. Bu yöntem, heceleme sırasında karşılaşılan her kelime için çağrılacaktır. Ona özel heceleme kuralları uygulayabilir ve hecelenmiş kelimeyi geri verebilirsiniz. Ardından, heceleme geri aramanızı kullanarak bağlayabilirsiniz.`Document.HyphenationCallback` belgenizin özelliği.

#### S: Aspose.Words'te bir heceleme hatırlatıcısı kullanmanın avantajı nedir?

C: Aspose.Words'ta bir heceleme hatırlatıcısı kullanmanın yararı, belgelerinizde kelimelerin nasıl hecelendiğini özelleştirme yeteneğidir. Bu, özellikle varsayılan hecelemenin istenen sonuçları vermediği belirli diller veya senaryolar için heceleme üzerinde daha fazla kontrol sağlar. İhtiyaçlarınıza göre kesin heceleme elde etmek için her kelimeye özel kurallar uygulayabilirsiniz.

#### S: Heceleme hatırlatıcı kullanmanın yardımcı olabileceği bazı yaygın senaryolar nelerdir?

C: Bir heceleme artırıcı kullanmak, aşağıdakiler gibi çeşitli senaryolarda yararlı olabilir:
- Belirli heceleme kurallarına sahip belirli dillerdeki sözcüklerin hecelenmesi.
- Kısaltmalar veya teknik kelimeler için kişiselleştirilmiş heceleme kurallarının uygulanması.
- Hecelemenin biçimsel tercihlere veya tipografik standartlara göre uyarlanması.

#### S: Özel hecelemeyi Aspose.Words'ta bir heceleme hatırlatıcısı ile nasıl test edebilirim?

C: Özel hecelemeyi Aspose.Words'ta bir heceleme hatırlatıcısıyla test etmek için özel heceleme kurallarını uygulamak istediğiniz sözcükleri içeren bir test belgesi oluşturabilirsiniz. Ardından, özel heceleme geri aramanızı ayarlayabilir,`Document.Range.Replace()` belgedeki sözcükleri değiştirme yöntemini kullanın ve`Hyphenate()` yöntemi`Hyphenation` kelimelerin hecelemesini almak için sınıf . Daha sonra, örneğin heceler arasına kısa çizgiler ekleyerek hecelenmiş sözcükleri gerektiği gibi biçimlendirebilirsiniz.