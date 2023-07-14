---
title: Şekli Office Matematiğine Dönüştür
linktitle: Şekli Office Matematiğine Dönüştür
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile belgeleri yüklerken şekilleri Office matematik formüllerine nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-loadoptions/convert-shape-to-office-math/
---

Bir C# uygulamasında matematik şekilleri içeren belgelerle Sözcük İşleme yaparken, daha iyi uyumluluk ve sunum için bunları Office matematik formüllerine dönüştürmeniz gerekebilir. .NET için Aspose.Words kitaplığıyla, bir belge yüklerken şekilleri kolayca Office matematik formüllerine dönüştürebilirsiniz. Bu adım adım kılavuzda, LoadOptions kullanarak şekilleri Office matematik formüllerine dönüştüren bir belgeyi yüklemek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## Yükleme Seçeneklerini Yapılandırma

İlk adım, belgemiz için yükleme seçeneklerini yapılandırmaktır. Yükleme parametrelerini belirtmek için LoadOptions sınıfını kullanın. Bizim durumumuzda, şekilleri Office matematik formüllerine dönüştürmek istiyoruz, bu nedenle ConvertShapeToOfficeMath özelliğini true olarak ayarlamamız gerekiyor. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

Yeni bir LoadOptions nesnesi oluşturuyoruz ve belgeyi yüklerken şekilleri Office matematik formüllerine dönüştürmeyi etkinleştirmek için ConvertShapeToOfficeMath özelliğini true olarak ayarlıyoruz.

## Şekilleri Office matematik formüllerine dönüştürerek belge yükleme

Yükleme seçeneklerini yapılandırdığımıza göre, Document sınıfını kullanarak belgeyi yükleyebilir ve yükleme seçeneklerini belirtebiliriz. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

Bu örnekte, belirtilen yükleme seçeneklerini kullanarak belgeler dizininde bulunan "Office math.docx" belgesini yüklüyoruz.

## Belgenin kaydı

Şekilleri Office matematik formüllerine dönüştüren belgeyi yükledikten sonra, Belge sınıfının Kaydet yöntemini kullanarak istediğiniz biçimde kaydedebilirsiniz. Örneğin, belgeyi .docx biçiminde kaydetmek için:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

Belgelerinizin dizin yolu ile "dataDir" değiştirdiğinizden emin olun.

### Aspose.Words for .NET kullanan "Shape'i Office Math'a Dönüştür" işlevine sahip LoadOptions için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "Şekli Dönüştür" işleviyle yükleme seçeneklerinin yapılandırılması

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// Belgeyi belirtilen seçeneklerle yükleyin
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

//Belgeyi istediğiniz biçimde kaydedin
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kitaplığını kullanarak şekilleri Office matematik formüllerine dönüştüren bir belgenin nasıl yükleneceğini açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Şekilleri Office matematik formüllerine dönüştürmek, matematik öğeleri içeren belgelerin daha iyi uyumluluğunu ve sunumunu sağlar.
