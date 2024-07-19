---
title: Kaynak Numaralandırmasını Koruyun
linktitle: Kaynak Numaralandırmasını Koruyun
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak formatı korurken belgeleri nasıl içe aktaracağınızı öğrenin. Kod örnekleri içeren adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/keep-source-numbering/
---
## giriiş

 Aspose.Words for .NET ile çalışırken, formatı koruyarak belgeleri bir kaynaktan diğerine aktarmak,`NodeImporter` sınıf. Bu eğitim size süreç boyunca adım adım rehberlik edecektir.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Makinenizde Visual Studio yüklü.
-  Aspose.Words for .NET kuruldu. Değilse, şuradan indirin:[Burada](https://releases.aspose.com/words/net/).
- Temel C# ve .NET programlama bilgisi.

## Ad Alanlarını İçe Aktar

Öncelikle projenize gerekli ad alanlarını ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## 1. Adım: Projenizi Kurun

Visual Studio'da yeni bir C# projesi oluşturarak başlayın ve Aspose.Words'ü NuGet Paket Yöneticisi aracılığıyla yükleyin.

## 2. Adım: Belgeleri Başlatın
Kaynağın örneklerini oluşturun (`srcDoc`) ve hedef (`dstDoc`) belgeler.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: İçe Aktarma Seçeneklerini Yapılandırın
Numaralandırılmış paragraflar da dahil olmak üzere kaynak biçimlendirmesini korumak için içe aktarma seçeneklerini ayarlayın.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Adım 4: Paragrafları İçe Aktarın
Kaynak belgedeki paragrafları yineleyin ve bunları hedef belgeye aktarın.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Adım 5: Belgeyi Kaydedin
Birleştirilen belgeyi istediğiniz konuma kaydedin.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Çözüm

 Sonuç olarak, formatı korurken belgeleri içe aktarmak için Aspose.Words for .NET'i kullanmak oldukça basittir.`NodeImporter` sınıf. Bu yöntem belgelerinizin orijinal görünüm ve yapısını sorunsuz bir şekilde korumasını sağlar.

## SSS'ler

### Farklı biçimlendirme stillerine sahip belgeleri içe aktarabilir miyim?
 Evet`NodeImporter` class, çeşitli biçimlendirme stillerine sahip belgelerin içe aktarılmasını destekler.

### Belgelerim karmaşık tablolar ve resimler içeriyorsa ne olur?
Aspose.Words for .NET, içe aktarma işlemleri sırasında tablolar ve görüntüler gibi karmaşık yapıları yönetir.

### Aspose.Words .NET'in tüm sürümleriyle uyumlu mu?
Aspose.Words, kusursuz entegrasyon için .NET Framework ve .NET Core sürümlerini destekler.

### Belgeyi içe aktarma sırasındaki hataları nasıl halledebilirim?
İçe aktarma işlemi sırasında oluşabilecek istisnaları işlemek için try-catch bloklarını kullanın.

### Aspose.Words for .NET hakkında daha ayrıntılı belgeleri nerede bulabilirim?
 Ziyaret edin[dokümantasyon](https://reference.aspose.com/words/net/) kapsamlı kılavuzlar ve API referansları için.
