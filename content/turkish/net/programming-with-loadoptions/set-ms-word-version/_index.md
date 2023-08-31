---
title: Ms Word Sürümünü Ayarla
linktitle: Ms Word Sürümünü Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak belirli bir MS Word sürümüne sahip bir belgeyi nasıl yükleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-loadoptions/set-ms-word-version/
---
Bir C# uygulamasında Word belgeleriyle Kelime İşleme yapılırken, belge yüklenirken kullanılacak Microsoft Word sürümünün belirtilmesi gerekebilir. .NET için Aspose.Words kütüphanesi ile LoadOptions'ı kullanarak MS Word'ün hangi sürümünü kullanacağınızı kolayca ayarlayabilirsiniz. Bu adım adım kılavuzda, LoadOptions yükleme seçeneklerini kullanarak belirli bir MS Word sürümüne sahip bir belgeyi yüklemek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgelerini .NET dahil farklı platformlarda oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kütüphanedir. Metin ekleme, biçimlendirmeyi değiştirme, bölüm ekleme ve çok daha fazlası gibi belgeleri değiştirmek için birçok özellik sunar.

## Yükleme Seçeneklerini Yapılandırma

İlk adım belgemiz için yükleme seçeneklerini yapılandırmaktır. Yükleme parametrelerini belirtmek için LoadOptions sınıfını kullanın. Bizim durumumuzda MswVersion özelliğini istenen MS Word sürümüne ayarlamamız gerekiyor. Mesela Microsoft Word 2010 versiyonunu kullanıyoruz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Yeni bir LoadOptions nesnesi oluşturuyoruz ve MS Word 2010 sürümünü belirtmek için MswVersion özelliğini MsWordVersion.Word2010 olarak ayarlıyoruz.

## Belirtilen MS Word sürümüyle belge yükleme

Yükleme seçeneklerini yapılandırdığımıza göre artık Document sınıfını kullanarak belgeyi yükleyebilir ve yükleme seçeneklerini belirtebiliriz. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Bu örnekte, belgeler dizininde bulunan "Document.docx" belgesini belirtilen yükleme seçeneklerini kullanarak yüklüyoruz.

### Aspose.Words for .NET kullanan "MS Word Sürümünü Ayarla" işlevine sahip LoadOptions için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "MS Word Sürümünü Ayarla" özelliğiyle yükleme seçeneklerini yapılandırma
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Belgeyi MS Word'ün belirtilen sürümüyle yükleyin
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Belgeyi kaydet
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kütüphanesini kullanarak MS Word'ün belirli bir sürümünü belirten bir belgenin nasıl yükleneceğini açıkladık. Verilen adımları takip ederek ve verilen C# kaynağını kullanarak bu işlevselliği C# uygulamanıza kolayca uygulayabilirsiniz. Bir belgeyi MS Word'ün belirli bir sürümüyle yüklemek, belgenin uygulamanızda uygun şekilde uyumluluğunu ve işlenmesini sağlamanıza olanak tanır.


### SSS'ler

#### S: Bir C# uygulamasına belge yüklerken neden MS Word sürümünü belirtmem gerekiyor?

MS Word sürümünün belirtilmesi, özellikle belirli biçimlendirme veya farklı sürümler arasında farklılık gösterebilecek özelliklerle uğraşırken belgenin doğru şekilde yüklenmesini ve işlenmesini sağlar.

#### S: Aspose.Words MS Word'ün hangi sürümlerini destekliyor?

C: Aspose.Words for .NET, Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 ve daha fazlası dahil olmak üzere MS Word'ün çeşitli sürümlerini destekler.

#### S: Sistemimde yüklü olandan farklı bir MS Word sürümüne sahip bir belge yükleyebilir miyim?

C: Evet, Aspose.Words, belgeyi yüklerken MS Word'ün farklı bir sürümünü belirtmenize olanak tanır ve hedef sistemin farklı bir MS Word sürümü olsa bile uyumluluğu garanti eder.

#### S: MS Word sürümünün ayarlanması C# uygulamama nasıl fayda sağlar?

C: MS Word sürümünün ayarlanması, belgenin amaçlanan biçimlendirmeye ve söz konusu sürümün özelliklerine göre işlenmesini ve tutarlı çıktı sağlanmasını sağlar.

#### S: Aspose.Words yalnızca DOCX belgeleriyle mi sınırlı?

C: Hayır, Aspose.Words, DOC, RTF, HTML, PDF ve daha fazlası dahil olmak üzere çeşitli belge formatlarını destekler ve bu da onu farklı türde belgelerin işlenmesi için çok yönlü bir araç haline getirir.