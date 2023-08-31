---
title: Ms Word Sürümünü Ayarla
linktitle: Ms Word Sürümünü Ayarla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeyi belirli bir MS Word sürümüyle nasıl yükleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-loadoptions/set-ms-word-version/
---
Bir C# uygulamasında Word ile Kelime İşleme belgeleri hazırlanırken, belge yüklenirken kullanılacak Microsoft Word sürümünün belirtilmesi gerekebilir. .NET için Aspose.Words kitaplığıyla, LoadOptions'ı kullanarak hangi MS Word sürümünün kullanılacağını kolayca ayarlayabilirsiniz. Bu adım adım kılavuzda, LoadOptions yükleme seçeneklerini kullanarak MS Word'ün belirli bir sürümünü içeren bir belgeyi yüklemek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## Yükleme Seçeneklerini Yapılandırma

İlk adım, belgemiz için yükleme seçeneklerini yapılandırmaktır. Yükleme parametrelerini belirtmek için LoadOptions sınıfını kullanın. Bizim durumumuzda, MswVersion özelliğini MS Word'ün istenen sürümüne ayarlamamız gerekiyor. Örneğin Microsoft Word 2010 sürümünü kullanıyoruz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Yeni bir LoadOptions nesnesi oluşturuyoruz ve MS Word 2010 sürümünü belirtmek için MswVersion özelliğini MsWordVersion.Word2010 olarak ayarlıyoruz.

## Belirtilen MS Word sürümüyle belge yükleme

Yükleme seçeneklerini yapılandırdığımıza göre, Document sınıfını kullanarak belgeyi yükleyebilir ve yükleme seçeneklerini belirtebiliriz. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Bu örnekte, belirtilen yükleme seçeneklerini kullanarak belgeler dizininde bulunan "Document.docx" belgesini yüklüyoruz.

### Aspose.Words for .NET kullanan "Set MS Word Version" işlevine sahip LoadOptions için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "MS Word Versiyonunu Ayarla" özelliği ile yükleme seçeneklerini yapılandırın
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Belgeyi belirtilen MS Word sürümüyle yükleyin
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// belgeyi kaydet
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Çözüm

Bu kılavuzda, MS Word'ün belirli bir sürümünü belirten bir belgenin Aspose.Words .NET kitaplığı kullanılarak nasıl yükleneceğini açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynağını kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Bir belgeyi MS Word'ün belirli bir sürümüyle yüklemek, uygulamanızda belgenin uygun uyumluluğunu ve işlenmesini sağlamanıza olanak tanır.


### SSS

#### S: Bir C# uygulamasına belge yüklerken neden MS Word sürümünü belirtmem gerekiyor?

MS Word sürümünün belirtilmesi, özellikle farklı sürümler arasında farklılık gösterebilen belirli biçimlendirme veya özelliklerle uğraşırken belgenin doğru şekilde yüklenmesini ve işlenmesini sağlar.

#### S: Aspose.Words MS Word'ün hangi sürümlerini destekliyor?

C: Aspose.Words for .NET, Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 ve daha fazlası dahil olmak üzere MS Word'ün çeşitli sürümlerini destekler.

#### S: Sistemimde kurulu olandan farklı bir MS Word sürümüne sahip bir belge yükleyebilir miyim?

C: Evet, Aspose.Words, belgeyi yüklerken MS Word'ün farklı bir sürümünü belirtmenize izin vererek, hedef sistem farklı bir MS Word sürümüne sahip olsa bile uyumluluğu garanti eder.

#### S: MS Word sürümünü ayarlamak C# uygulamama nasıl yarar sağlar?

Y: MS Word sürümünün ayarlanması, belgenin söz konusu belirli sürümün amaçlanan biçimlendirmesine ve özelliklerine göre işlenmesini sağlayarak tutarlı çıktı sağlar.

#### S: Aspose.Words yalnızca DOCX belgelerini işlemekle mi sınırlı?

C: Hayır, Aspose.Words, DOC, RTF, HTML, PDF ve daha fazlasını içeren çeşitli belge formatlarını destekler ve bu da onu farklı türdeki belgeleri işlemek için çok yönlü bir araç haline getirir.