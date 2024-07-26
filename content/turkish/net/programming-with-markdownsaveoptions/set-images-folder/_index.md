---
title: Görüntüler Klasörünü Ayarla
linktitle: Görüntüler Klasörünü Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgelerini uygun tablo hizalaması ile Markdown'a dönüştürün. Mükemmel sonuçlar için ayrıntılı kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-markdownsaveoptions/set-images-folder/
---
## giriiş

Tabloların ve içeriğin mükemmel şekilde hizalanmasını sağlarken Word belgenizi Markdown formatına aktarmak hiç istediniz mi? Aspose.Words for .NET bu görev için başvuracağınız çözümdür. Bu makalede Aspose.Words'ü kurma, belgenizi hazırlama ve uygun tablo içeriği hizalaması ile onu Markdown'a aktarma sürecinde size yol göstereceğiz. Takip edilmesini ve anlaşılmasını kolaylaştırmak için her adımı parçalara ayıracağız. Öyleyse gelin, Word belgelerinizi güzelce hizalanmış Markdown dosyalarına dönüştürelim!

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET: İndirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
-  Geçerli bir lisans: Ücretsiz deneme sürümü edinin[Burada](https://releases.aspose.com/) veya geçici lisans[Burada](https://purchase.aspose.com/temporary-license/).
- Visual Studio: Veya .NET geliştirmeyi destekleyen başka bir IDE.
- Temel C# bilgisi: C# programlama dilinin anlaşılması.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını C# projenize aktarmanız gerekir. Bu ad alanları Aspose.Words işlevselliğine erişmenizi sağlayacaktır.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System.IO;
```

## 1. Adım: Projenizi Kurun

İlk olarak IDE'nizde .NET projenizi kurun. Yeni bir konsol uygulaması oluşturun ve Aspose.Words for .NET'e bir referans ekleyin.

### 1.1 Yeni Bir Proje Oluşturun

Visual Studio'yu açın ve yeni bir Konsol Uygulaması projesi oluşturun. Bunu "MarkdownExporter" veya benzeri bir adla adlandırın.

### 1.2 Aspose.Words Referansını Ekle

 Aspose.Words'ü projenize eklemek için DLL'yi şuradan indirebilirsiniz:[Web sitesi](https://releases.aspose.com/words/net/) ve manuel olarak ekleyin veya NuGet Paket Yöneticisini kullanın:

```bash
Install-Package Aspose.Words
```

## Adım 2: Markdown Olarak Dışa Aktarılacak Kodu Yazın

Şimdi Word belgesini okuyabilecek kodu yazalım ve uygun tablo hizalaması ile Markdown dosyası olarak kaydedelim.

### 2.1 Belgenizin Yolunu Tanımlayın

Word belgenizin yolunu ve görüntüleri kaydetmek istediğiniz klasörü ayarlayın.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
```

### 2.2 Belgeyi Yükleyin

Aspose.Words'ü kullanarak Word belgenizi yükleyin.

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

### 2.3 Markdown Kaydetme Seçeneklerini Yapılandırma

 Yapılandır`MarkdownSaveOptions` görüntülerin nerede saklanacağını belirtmek için.

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    ImagesFolder = dataDir + "Images"
};
```

### 2.4 Belgeyi Markdown Olarak Kaydetme

 Kullanın`MemoryStream` Belgeyi Markdown formatında kaydetmek için.

```csharp
using (MemoryStream stream = new MemoryStream())
{
    doc.Save(stream, saveOptions);
}
```

## Çözüm

Bu adımları takip ettiğinizde Aspose.Words for .NET kullanarak bir Word belgesini tablo içeriği hizalamayla Markdown'a aktarmak çok kolaydır. Birkaç satır kodla dönüştürme sürecini otomatikleştirebilir ve içeriğinizin iyi biçimlendirildiğinden emin olabilirsiniz. Artık harika görüneceklerini ve yapılarını koruyacaklarını bilerek belgelerinizi Markdown formatında kolayca paylaşabilirsiniz.

## SSS'ler

### Aspose.Words for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?

Evet, Aspose.Words for .NET, VB.NET, F# ve daha fazlası gibi .NET uyumlu herhangi bir dille kullanılabilir.

### Aspose.Words için nasıl geçici lisans alabilirim?

 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### Ne tür belgeleri Markdown'a dönüştürebilirim?

.doc, .docx, .rtf ve daha fazlasını içeren çeşitli Word belgelerini dönüştürebilirsiniz.

### Aspose.Words'ün deneme sürümünde herhangi bir sınırlama var mı?

Deneme sürümünün çıktı dosyalarındaki filigranlar gibi bazı sınırlamaları vardır. Ücretsiz deneme alabilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Words için daha fazla örnek ve belgeyi nerede bulabilirim?

 Ayrıntılı belgeleri ve örnekleri şurada bulabilirsiniz:[Web sitesi](https://reference.aspose.com/words/net/).
