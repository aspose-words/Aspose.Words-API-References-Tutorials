---
title: Web Uzantısı Görev Bölmelerini Kullanma
linktitle: Web Uzantısı Görev Bölmelerini Kullanma
second_title: Aspose.Words Belge İşleme API'si
description: Bu ayrıntılı, adım adım eğitimde Aspose.Words for .NET kullanarak Word belgelerinde Web Uzantısı Görev Bölmelerini nasıl ekleyeceğinizi ve yapılandıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-webextension/using-web-extension-task-panes/
---
## giriiş

Aspose.Words for .NET kullanarak bir Word belgesinde Web Uzantısı Görev Bölmelerinin kullanımına ilişkin bu ayrıntılı eğitime hoş geldiniz. Word belgelerinizi etkileşimli görev bölmeleriyle geliştirmek istiyorsanız doğru yerdesiniz. Bu kılavuz, bunu sorunsuz bir şekilde başarmanız için her adımda size yol gösterecektir.

## Önkoşullar

Konuya dalmadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

-  Aspose.Words for .NET: İndirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
- .NET Geliştirme Ortamı: Visual Studio veya tercih ettiğiniz başka bir IDE.
- Temel C# Bilgisi: Bu, kod örneklerini takip etmenize yardımcı olacaktır.
-  Aspose.Words Lisansı: Bir tane satın alabilirsiniz[Burada](https://purchase.aspose.com/buy) veya geçici lisans alın[Burada](https://purchase.aspose.com/temporary-license/).

## Ad Alanlarını İçe Aktar

Kodlamaya başlamadan önce projenizde aşağıdaki ad alanlarının içe aktarıldığından emin olun:

```csharp
using Aspose.Words;
using Aspose.Words.WebExtensions;
```

## Adım adım rehber

Şimdi süreci takip edilmesi kolay adımlara ayıralım.

### 1. Adım: Belge Dizininizi Ayarlama

Öncelikle belgeler dizininizin yolunu ayarlamamız gerekiyor. Burası Word belgenizin kaydedileceği yerdir.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile.

### Adım 2: Yeni Bir Belge Oluşturma

Daha sonra Aspose.Words'ü kullanarak yeni bir Word belgesi oluşturacağız.

```csharp
Document doc = new Document();
```

 Bu satır yeni bir örneğini başlatır.`Document` Bir Word belgesini temsil eden sınıf.

### 3. Adım: Görev Bölmesi Ekleme

Şimdi belgemize bir Görev Bölmesi ekleyeceğiz. Görev Bölmeleri, bir Word belgesinde ek işlevler ve araçlar sağlamak için kullanışlıdır.

```csharp
TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);
```

 Burada yeni bir tane oluşturuyoruz`TaskPane` nesneyi seçin ve onu belgenin`WebExtensionTaskPanes` Toplamak.

### Adım 4: Görev Bölmesini Yapılandırma

Görev Panomuzu görünür kılmak ve özelliklerini ayarlamak için aşağıdaki kodu kullanıyoruz:

```csharp
taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

- `DockState` Görev Bölmesinin nerede görüneceğini ayarlar. Bu durumda sağdadır.
- `IsVisible` Görev Bölmesinin görünür olmasını sağlar.
- `Width` Görev Bölmesinin genişliğini ayarlar.

### Adım 5: Web Uzantısı Referansını Ayarlama

Daha sonra kimliği, sürümü, mağaza türünü ve mağazayı içeren Web Uzantısı Referansını ayarlıyoruz.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

- `Id`web uzantısı için benzersiz bir tanımlayıcıdır.
- `Version` Uzantının sürümünü belirtir.
- `StoreType` mağazanın türünü belirtir (bu durumda OMEX).
- `Store` mağazanın dilini/kültür kodunu belirtir.

### Adım 6: Web Uzantısına Özellikler Ekleme

Davranışını veya içeriğini tanımlamak için web uzantınıza özellikler ekleyebilirsiniz.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
```

 Burada adında bir özellik ekliyoruz.`mailchimpCampaign`.

### Adım 7: Web Uzantısını Bağlama

Son olarak web uzantımıza bağlamalar ekliyoruz. Bağlantılar, uzantıyı belgenin belirli bölümlerine bağlamanıza olanak tanır.

```csharp
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545", WebExtensionBindingType.Text, "194740422"));
```

- `UnnamedBinding_0_1506535429545` bağlamanın adıdır.
- `WebExtensionBindingType.Text` ciltlemenin metin türünde olduğunu gösterir.
- `194740422` Uzantının bağlı olduğu belgenin kısmının kimliğidir.

### Adım 8: Belgeyi Kaydetme

Her şeyi ayarladıktan sonra belgenizi kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

Bu satır, belgeyi belirtilen dosya adıyla belirtilen dizine kaydeder.

### Adım 9: Görev Bölmesi Bilgilerini Yükleme ve Görüntüleme

Görev bölmesi bilgilerini doğrulamak ve görüntülemek için belgeyi yükler ve görev bölmeleri arasında yineleniriz.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");

Console.WriteLine("Task panes sources:\n");

foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
    WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
    Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
}
```

Bu kod belgeyi yükler ve konsoldaki her görev bölmesinin sağlayıcısını, sürümünü ve katalog tanımlayıcısını yazdırır.

## Çözüm

Ve bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesine Web Uzantısı Görev Bölmesini başarıyla eklediniz ve yapılandırdınız. Bu güçlü özellik, doğrudan belgenin içinde ek işlevler sağlayarak Word belgelerinizi önemli ölçüde geliştirebilir. 

## SSS'ler

### Word'de Görev Bölmesi nedir?
Görev Bölmesi, bir Word belgesi içinde ek araçlar ve işlevler sağlayan, kullanıcı etkileşimini ve üretkenliğini artıran bir arayüz öğesidir.

### Görev Bölmesinin görünümünü özelleştirebilir miyim?
 Evet, aşağıdaki gibi özellikleri ayarlayarak Görev Bölmesinin görünümünü özelleştirebilirsiniz:`DockState`, `IsVisible` , Ve`Width`.

### Web Uzantısı Özellikleri Nedir?
Web Uzantısı Özellikleri, bir web uzantısının davranışını veya içeriğini tanımlamak için ekleyebileceğiniz özel özelliklerdir.

### Bir Web Uzantısını belgenin bir bölümüne nasıl bağlarım?
 Web Uzantısını kullanarak belgenin bir bölümüne bağlayabilirsiniz.`WebExtensionBinding` bağlama türünü ve hedef kimliğini belirten sınıf.

### Aspose.Words for .NET hakkında daha fazla bilgiyi nerede bulabilirim?
 Ayrıntılı belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).