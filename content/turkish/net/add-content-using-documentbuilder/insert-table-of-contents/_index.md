---
title: Word Belgesine İçindekiler Tablosu Ekleme
linktitle: Word Belgesine İçindekiler Tablosu Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word'e nasıl İçindekiler ekleyeceğinizi öğrenin. Belgelerde kusursuz gezinme için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-table-of-contents/
---
## giriiş
Bu eğitimde, Aspose.Words for .NET kullanarak Word belgelerinize nasıl etkili bir İçindekiler Tablosu (TOC) ekleyeceğinizi öğreneceksiniz. Bu özellik, uzun belgeleri düzenlemek ve gezinmek, okunabilirliği artırmak ve belge bölümlerine hızlı bir genel bakış sağlamak için gereklidir.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# ve .NET çerçevesine ilişkin temel anlayış.
- Makinenizde Visual Studio yüklü.
-  Aspose.Words for .NET kitaplığı. Henüz yüklemediyseniz adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/).

## Ad Alanlarını İçe Aktar

Başlamak için C# projenize gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Words;
using Aspose.Words.Builder;
using Aspose.Words.Fields;
using Aspose.Words.Tables;
```

Süreci net adımlara ayıralım:

## Adım 1: Aspose.Words Document ve DocumentBuilder'ı başlatın

 Öncelikle yeni bir Aspose.Words başlatın`Document` nesne ve bir`DocumentBuilder` çalışmak için:

```csharp
// Document ve DocumentBuilder'ı Başlat
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: İçindekiler Tablosunu Ekleyin

 Şimdi içindekileri kullanarak İçindekiler'i ekleyin.`InsertTableOfContents` yöntem:

```csharp
// İçindekiler Ekle
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## 3. Adım: Belge İçeriğini Yeni Bir Sayfada Başlatın

Doğru biçimlendirmeyi sağlamak için asıl belge içeriğini yeni bir sayfada başlatın:

```csharp
// Sayfa sonu ekleme
builder.InsertBreak(BreakType.PageBreak);
```

## Adım 4: Belgenizi Başlıklarla Yapılandırın

Uygun başlık stillerini kullanarak belge içeriğinizi düzenleyin:

```csharp
// Başlık stillerini ayarlama
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## 5. Adım: İçindekiler Tablosunu Güncelleyin ve Doldurun

Belge yapısını yansıtacak şekilde İçindekiler Tablosunu güncelleyin:

```csharp
// İçindekiler alanlarını güncelleme
doc.UpdateFields();
```

## Adım 6: Belgeyi Kaydedin

Son olarak belgenizi belirtilen dizine kaydedin:

```csharp
// Belgeyi kaydet
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
doc.Save(dataDir + "InsertTableOfContentsUsingAsposeWords.docx");
```

## Çözüm

Aspose.Words for .NET'i kullanarak İçindekiler Tablosu eklemek basittir ve belgelerinizin kullanılabilirliğini önemli ölçüde artırır. Bu adımları izleyerek karmaşık belgeleri verimli bir şekilde düzenleyebilir ve bunlar arasında gezinebilirsiniz.

## SSS'ler

### İçindekiler Tablosunun görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET API'lerini kullanarak İçindekiler'in görünümünü ve davranışını özelleştirebilirsiniz.

### Aspose.Words alanların otomatik olarak güncellenmesini destekliyor mu?
Evet, Aspose.Words, İçindekiler gibi alanları belge değişikliklerine göre dinamik olarak güncellemenize olanak tanır.

### Tek bir belgede birden fazla İçindekiler Tablosu oluşturabilir miyim?
Aspose.Words, tek bir belgede farklı ayarlarla birden fazla İçindekiler oluşturmayı destekler.

### Aspose.Words Microsoft Word'ün farklı sürümleriyle uyumlu mu?
Evet, Aspose.Words, Microsoft Word formatlarının çeşitli sürümleriyle uyumluluk sağlar.

### Aspose.Words için nerede daha fazla yardım ve destek bulabilirim?
 Daha fazla yardım için şu adresi ziyaret edin:[Aspose.Words Forumu](https://forum.aspose.com/c/words/8) veya şuraya göz atın[resmi belgeler](https://reference.aspose.com/words/net/).