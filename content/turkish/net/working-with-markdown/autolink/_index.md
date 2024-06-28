---
title: Otomatik bağlantı
linktitle: Otomatik bağlantı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile otomatik bağlantı eklemeyi öğrenin Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/autolink/
---

Bu örnekte Aspose.Words for .NET ile "Otomatik Bağlantı" özelliğinin nasıl kullanılacağını açıklayacağız. Bu özellik, belgenize otomatik olarak köprüler eklemenizi sağlar.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Köprü ekleme

 kullanarak bir köprü ekleyebiliriz.`InsertHyperlink` belge oluşturucu yöntemi. Bağlantı için görüntülenecek URL'yi ve metni belirtiyoruz.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## 3. Adım: Bağlantı olarak bir e-posta adresi ekleme

Ayrıca "mailto:" önekini kullanarak bağlantı olarak bir e-posta adresi de ekleyebiliriz. Bu, kullanıcıların varsayılan e-posta istemcilerini açmak için bağlantıya tıklamalarına olanak tanır.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## 4. Adım: Belgeyi kaydetme

Son olarak belgeyi istediğimiz formatta kaydedebiliriz.

### Aspose.Words for .NET kullanan Otomatik Bağlantı için Örnek Kaynak Kodu


```csharp
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Köprü ekle.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Tebrikler! Artık Aspose.Words for .NET ile "Otomatik Bağlantı" özelliğini nasıl kullanacağınızı öğrendiniz.


### SSS'ler

#### S: Aspose.Words'te bir URL adresine nasıl otomatik bağlantı oluşturabilirim?

 C: Aspose.Words'te bir URL adresine otomatik bağlantı oluşturmak için`<a>` ile etiketleyin`href` URL adresini içeren özellik. Örneğin şunları kullanabilirsiniz:`<a href="https://www.aspose.com">https://www.aspose.com</a>` "https: //www.aspose.com" adresine otomatik olarak bağlanmak için.

#### S: Aspose.Words'te otomatik bir bağlantının görüntü metnini özelleştirmek mümkün mü?

 C: Evet, Aspose.Words'te otomatik bağlantının görüntü metnini özelleştirebilirsiniz. Görünen metin olarak URL adresini kullanmak yerine, içeriği aşağıdaki metinle değiştirerek başka bir metni kullanabilirsiniz:`<a>` Etiketler. Örneğin şunları kullanabilirsiniz:`<a href="https://www.aspose.com">Click here</a>` "Buraya tıklayın" metnini otomatik bağlantı olarak görüntülemek için.

#### S: Aspose.Words'teki bir otomatik bağlantıya nasıl ek özellikler ekleyebilirim?

C: Aspose.Words'te otomatik bir bağlantıya ek özellikler eklemek için, ek HTML özelliklerini kullanabilirsiniz.`<a>` etiket. Örneğin şunları kullanabilirsiniz:`<a href="https://www.aspose.com" target="_blank">Link</a>` Bağlantıyı yeni bir pencerede veya sekmede açmak için` attribute target="_blank"`.