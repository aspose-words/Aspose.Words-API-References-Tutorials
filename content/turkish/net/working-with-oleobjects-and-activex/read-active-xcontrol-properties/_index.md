---
title: Active XControl Özelliklerini Word Dosyasından Okuyun
linktitle: Active XControl Özelliklerini Word Dosyasından Okuyun
second_title: Aspose.Words Belge İşleme API'si
description: Adım adım kılavuzdan Aspose.Words for .NET kullanarak ActiveX kontrol özelliklerini Word dosyalarından nasıl okuyacağınızı öğrenin. Belge otomasyon becerilerinizi geliştirin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## giriiş

Günümüzün dijital çağında otomasyon verimliliği artırmanın anahtarıdır. ActiveX denetimleri içeren Word belgeleriyle çalışıyorsanız çeşitli amaçlarla bunların özelliklerini okumanız gerekebilir. Onay kutuları ve düğmeler gibi ActiveX denetimleri önemli verileri tutabilir. Aspose.Words for .NET'i kullanarak bu verileri programlı bir şekilde verimli bir şekilde çıkarabilir ve değiştirebilirsiniz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET Kütüphanesi: Buradan indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/).
2. Visual Studio veya herhangi bir C# IDE: Kodunuzu yazmak ve yürütmek için.
3. ActiveX denetimlerine sahip bir Word belgesi: Örneğin, "ActiveX denetimleri.docx".
4. Temel C# bilgisi: Devam etmek için C# programlamaya aşinalık gereklidir.

## Ad Alanlarını İçe Aktar

Öncelikle Aspose.Words for .NET ile çalışmak için gerekli ad alanlarını içe aktaralım.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## Adım 1: Word Belgesini Yükleyin

Başlamak için ActiveX denetimlerini içeren Word belgesini yüklemeniz gerekir.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## Adım 2: Özellikleri Tutmak için Bir Dize Başlatın

Daha sonra, ActiveX denetimlerinin özelliklerini depolamak için boş bir dize başlatın.

```csharp
string properties = "";
```

## Adım 3: Belgedeki Şekilleri Yineleyin

ActiveX denetimlerini bulmak için belgedeki tüm şekilleri yinelememiz gerekir.

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        // ActiveX kontrolünü işle
    }
}
```

## Adım 4: Özellikleri ActiveX Denetimlerinden Çıkarın

Döngü içinde kontrolün bir Forms2OleControl olup olmadığını kontrol edin. Eğer öyleyse, yayınlayın ve özellikleri çıkarın.

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## Adım 5: Toplam ActiveX Denetimlerini Sayma

Tüm şekilleri yineledikten sonra bulunan ActiveX denetimlerinin toplam sayısını sayın.

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## Adım 6: Özellikleri Görüntüleyin

Son olarak, çıkarılan özellikleri konsola yazdırın.

```csharp
Console.WriteLine("\n" + properties);
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET kullanarak bir Word belgesinden ActiveX kontrol özelliklerini nasıl okuyacağınızı başarıyla öğrendiniz. Bu eğitimde bir belgenin yüklenmesi, şekiller arasında yineleme yapılması ve ActiveX denetimlerinden özelliklerin çıkarılması konuları yer alıyordu. Bu adımları izleyerek, önemli verilerin Word belgelerinizden çıkarılmasını otomatikleştirerek iş akışı verimliliğinizi artırabilirsiniz.

## SSS'ler

### Word belgelerindeki ActiveX denetimleri nelerdir?
ActiveX denetimleri, formlar oluşturmak ve görevleri otomatikleştirmek için kullanılan, onay kutuları, düğmeler ve metin alanları gibi Word belgelerine gömülü etkileşimli nesnelerdir.

### Aspose.Words for .NET kullanarak ActiveX kontrollerinin özelliklerini değiştirebilir miyim?
Evet, Aspose.Words for .NET, ActiveX kontrollerinin özelliklerini programlı olarak değiştirmenize olanak tanır.

### Aspose.Words for .NET'in kullanımı ücretsiz mi?
 Aspose.Words for .NET ücretsiz deneme sürümü sunar ancak sürekli kullanım için bir lisans satın almanız gerekir. Ücretsiz deneme alabilirsiniz[Burada](https://releases.aspose.com/).

### Aspose.Words for .NET'i C#'ın yanı sıra diğer .NET dilleriyle de kullanabilir miyim?
Evet, Aspose.Words for .NET, VB.NET ve F# da dahil olmak üzere herhangi bir .NET diliyle kullanılabilir.

### Aspose.Words for .NET hakkında daha fazla belgeyi nerede bulabilirim?
 Ayrıntılı belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).