---
title: Word Belgesinde Tercih Edilen Kontrol Türü
linktitle: Word Belgesinde Tercih Edilen Kontrol Türü
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesine nasıl birleşik giriş kutusu form alanı ekleyeceğinizi öğrenin. Sorunsuz HTML içerik entegrasyonu için bu adım adım kılavuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-htmlloadoptions/preferred-control-type/
---
## giriiş

Aspose.Words for .NET'te HTML yükleme seçenekleriyle nasıl çalışılacağına dair heyecan verici bir eğitime dalıyoruz; özellikle bir Word belgesine birleşik giriş kutusu form alanı eklerken tercih edilen kontrol tipini ayarlamaya odaklanıyoruz. Bu adım adım kılavuz, Aspose.Words for .NET kullanarak Word belgelerinizdeki HTML içeriğini etkili bir şekilde nasıl değiştireceğinizi ve oluşturacağınızı anlamanıza yardımcı olacaktır.

## Önkoşullar

Koda geçmeden önce, yerine getirmeniz gereken birkaç şey var:

1.  Aspose.Words for .NET: Aspose.Words for .NET kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi bir geliştirme ortamına sahip olmalısınız.
3. Temel C# Bilgisi: Öğreticiyi takip etmek için C# programlamaya ilişkin temel bir anlayış gereklidir.
4. HTML İçeriği: Bu örnekte HTML içeriğiyle çalışacağımız için temel HTML bilgisi faydalıdır.

## Ad Alanlarını İçe Aktar

Öncelikle başlamak için gerekli ad alanlarını içe aktaralım:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Words;
using Aspose.Words.Loading;
```

Şimdi netlik ve anlayış sağlamak için örneği birden fazla adıma ayıralım.

## 1. Adım: HTML İçeriğinizi Ayarlayın

Öncelikle Word belgesine eklemek istediğimiz HTML içeriğini tanımlamamız gerekiyor. İşte kullanacağımız HTML pasajı:

```csharp
const string html = @"
    <html>
        <select name='ComboBox' size='1'>
            <option value='val1'>item1</option>
            <option value='val2'></option>                        
        </select>
    </html>
";
```

Bu HTML, iki seçenekli basit bir açılır kutu içerir. Bu HTML'yi bir Word belgesine yükleyeceğiz ve nasıl oluşturulması gerektiğini belirleyeceğiz.

## Adım 2: Belge Dizinini Tanımlayın

Daha sonra Word belgenizin kaydedileceği dizini belirtin. Bu, dosyalarınızı düzenlemenize ve yol yönetimini temiz tutmanıza yardımcı olur.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Word belgenizi kaydetmek istediğiniz asıl yolla.

## 3. Adım: HTML Yükleme Seçeneklerini Yapılandırma

 Burada, özellikle HTML yükleme seçeneklerini yapılandırıyoruz.`PreferredControlType`mülk. Bu, birleşik giriş kutusunun Word belgesinde nasıl işlenmesi gerektiğini belirler.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

 Ayarlayarak`PreferredControlType` ile`HtmlControlType.StructuredDocumentTag`, birleşik giriş kutusunun Word belgesinde yapılandırılmış belge etiketi (SDT) olarak görüntülenmesini sağlıyoruz.

## Adım 4: HTML İçeriğini Belgeye Yükleyin

Yapılandırılmış yükleme seçeneklerini kullanarak HTML içeriğini yeni bir Word belgesine yüklüyoruz.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

Burada HTML dizesini bir bayt dizisine dönüştürüyoruz ve bir bellek akışı kullanarak belgeye yüklüyoruz. Bu, HTML içeriğinin Aspose.Words tarafından doğru şekilde yorumlanmasını ve işlenmesini sağlar.

## Adım 5: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine DOCX formatında kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

Bu, oluşturulan birleşik giriş kutusu denetimiyle birlikte Word belgesini belirtilen konuma kaydeder.

## Çözüm

İşte buyur! Aspose.Words for .NET kullanarak, HTML yükleme seçeneklerini kullanarak bir Word belgesine başarılı bir şekilde birleşik giriş kutusu form alanı ekledik. Bu adım adım kılavuz, süreci anlamanıza ve projelerinize uygulamanıza yardımcı olacaktır. İster belge oluşturmayı otomatikleştiriyor olun ister HTML içeriğini yönetiyor olun, Aspose.Words for .NET, hedeflerinize ulaşmanız için güçlü araçlar sağlar.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, düzenlemesine, dönüştürmesine ve işlemesine olanak tanıyan güçlü bir belge işleme kitaplığıdır.

### Aspose.Words for .NET ile diğer HTML kontrol türlerini kullanabilir miyim?
Evet, Aspose.Words for .NET çeşitli HTML kontrol türlerini destekler. Word belgesinde farklı denetimlerin nasıl işleneceğini özelleştirebilirsiniz.

### Aspose.Words for .NET'te karmaşık HTML içeriğini nasıl yönetirim?
 Aspose.Words for .NET, karmaşık öğeler de dahil olmak üzere HTML için kapsamlı destek sağlar. yapılandırdığınızdan emin olun`HtmlLoadOptions`özel HTML içeriğinizi uygun şekilde işlemek için.

### Daha fazla örnek ve belgeyi nerede bulabilirim?
 Ayrıntılı belgeleri ve örnekleri şurada bulabilirsiniz:[Aspose.Words for .NET dokümantasyon sayfası](https://reference.aspose.com/words/net/).

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Web sitesi](https://releases.aspose.com/).
