---
title: Belge Dosya Formatını Algıla
linktitle: Belge Dosya Formatını Algıla
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı, adım adım kılavuzla Aspose.Words for .NET kullanarak belge dosya formatlarını nasıl tespit edeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-fileformat/detect-file-format/
---
## giriiş

Günümüzün dijital dünyasında, farklı belge formatlarını verimli bir şekilde yönetmek çok önemlidir. İster Word, PDF, HTML veya diğer formatları kullanıyor olun, bu dosyaları doğru bir şekilde algılayıp işleyebilmek size çok fazla zaman ve emek tasarrufu sağlayabilir. Bu eğitimde Aspose.Words for .NET kullanarak belge dosya formatlarının nasıl tespit edileceğini inceleyeceğiz. Bu kılavuz, ön koşullardan ayrıntılı adım adım kılavuza kadar bilmeniz gereken her şeyde size yol gösterecektir.

## Önkoşullar

Koda dalmadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

-  Aspose.Words for .NET: Buradan indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/) . Geçerli bir lisansınız olduğundan emin olun. Değilse, bir tane alabilirsiniz[geçici lisans](https://purchase.aspose.com/temporary-license/).
- Visual Studio: Herhangi bir güncel sürüm düzgün çalışacaktır.
- .NET Framework: Doğru sürümün kurulu olduğundan emin olun.

## Ad Alanlarını İçe Aktar

Başlamak için projenize gerekli ad alanlarını içe aktarmanız gerekir:

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

Takip etmeyi kolaylaştırmak için örneği birden fazla adıma ayıralım.

## 1. Adım: Dizinleri Ayarlayın

Öncelikle dosyaların formatlarına göre sıralanacağı dizinleri ayarlamamız gerekiyor.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Henüz mevcut değilse dizinleri oluşturun.
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## Adım 2: Dosya Listesini Alın

Daha sonra, bozuk belgeler hariç, dizindeki dosyaların bir listesini alacağız.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## 3. Adım: Dosya Formatlarını Algılama

Artık her dosyayı yineliyoruz ve Aspose.Words'ü kullanarak formatını tespit ediyoruz.

```csharp
foreach (string fileName in fileList)
{
    string nameOnly = Path.GetFileName(fileName);

    Console.Write(nameOnly);

    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

    // Belge türünü görüntüle
    switch (info.LoadFormat)
    {
        case LoadFormat.Doc:
            Console.WriteLine("\tMicrosoft Word 97-2003 document.");
            break;
        case LoadFormat.Dot:
            Console.WriteLine("\tMicrosoft Word 97-2003 template.");
            break;
        case LoadFormat.Docx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
            break;
        case LoadFormat.Docm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
            break;
        case LoadFormat.Dotx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
            break;
        case LoadFormat.Dotm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
            break;
        case LoadFormat.FlatOpc:
            Console.WriteLine("\tFlat OPC document.");
            break;
        case LoadFormat.Rtf:
            Console.WriteLine("\tRTF format.");
            break;
        case LoadFormat.WordML:
            Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
            break;
        case LoadFormat.Html:
            Console.WriteLine("\tHTML format.");
            break;
        case LoadFormat.Mhtml:
            Console.WriteLine("\tMHTML (Web archive) format.");
            break;
        case LoadFormat.Odt:
            Console.WriteLine("\tOpenDocument Text.");
            break;
        case LoadFormat.Ott:
            Console.WriteLine("\tOpenDocument Text Template.");
            break;
        case LoadFormat.DocPreWord60:
            Console.WriteLine("\tMS Word 6 or Word 95 format.");
            break;
        case LoadFormat.Unknown:
            Console.WriteLine("\tUnknown format.");
            break;
    }

    if (info.IsEncrypted)
    {
        Console.WriteLine("\tAn encrypted document.");
        File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
    }
    else
    {
        switch (info.LoadFormat)
        {
            case LoadFormat.DocPreWord60:
                File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
                break;
            case LoadFormat.Unknown:
                File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
                break;
            default:
                File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
                break;
        }
    }
}
```

## Çözüm

Aspose.Words for .NET kullanarak belge dosya formatlarını tespit etmek basit bir işlemdir. Dizinlerinizi ayarlayarak, dosya listenizi alarak ve dosya formatlarını tespit etmek için Aspose.Words'ü kullanarak belgelerinizi verimli bir şekilde düzenleyebilir ve yönetebilirsiniz. Bu yaklaşım hem zamandan tasarruf etmenizi sağlar hem de çeşitli belge formatlarını doğru şekilde işlemenizi sağlar.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, Word belgeleriyle programlı olarak çalışmak için güçlü bir kütüphanedir. Geliştiricilerin çeşitli formatlarda belgeler oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanır.

### Aspose.Words şifrelenmiş belgeleri tespit edebilir mi?
Evet, Aspose.Words bir belgenin şifreli olup olmadığını tespit edebilir ve siz de bu tür belgeleri buna göre yönetebilirsiniz.

### Aspose.Words hangi formatları algılayabilir?
Aspose.Words, DOC, DOCX, RTF, HTML, MHTML, ODT ve çok daha fazlasını içeren çok çeşitli formatları algılayabilir.

### Aspose.Words için nasıl geçici lisans alabilirim?
 Geçici lisansı şu adresten alabilirsiniz:[Satın Almayı Düşün](https://purchase.aspose.com/temporary-license/) sayfa.

### Aspose.Words belgelerini nerede bulabilirim?
 Aspose.Words belgelerini burada bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).
