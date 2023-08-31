---
title: Active XControl Özelliklerini Word Dosyasından Okuyun
linktitle: Active XControl Özelliklerini Word Dosyasından Okuyun
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word dosyasındaki ActiveX kontrollerinin özelliklerini okuyun.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word dosyasındaki ActiveX kontrollerinin özelliklerini nasıl okuyacağınızı göstereceğiz. Size kaynak kodunun tamamını sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgenin başlatılması

 İlk adım,`Document` ActiveX denetimlerini içeren Word belgesini yükleyerek nesneyi oluşturun. Değiştirdiğinizden emin olun`MyDir` belgeyi içeren dizinin gerçek yolu ile birlikte.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## 2. Adım: ActiveX denetimlerini kurtarın

 Bu adımda, her birini yineleyeceğiz`Shape` ActiveX denetimlerini almak ve özelliklerini okumak için belgenin.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Aspose.Words for .NET kullanarak Active XControl Özelliklerini Okumak için örnek kaynak kodu

Aspose.Words for .NET kullanarak ActiveX kontrollerinin özelliklerini okumak için tam kaynak kodu:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## Çözüm

Bu kılavuz size Aspose.Words for .NET kullanarak bir Word dosyasındaki ActiveX kontrollerinin özelliklerini nasıl okuyacağınızı gösterdi. Açıklanan adımları izleyerek belgeyi başlatabilir, ActiveX kontrollerini alabilir ve özelliklerini okuyabilirsiniz. Başlangıç noktası olarak sağlanan örnek kodu kullanın ve bunu özel ihtiyaçlarınıza göre özelleştirin.

ActiveX denetimlerinin özelliklerini okumak, bu denetimleri içeren Word dosyalarınızdan önemli bilgileri çıkarmanıza olanak tanır. Aspose.Words for .NET, ActiveX kontrolleriyle Kelime İşleme ve belge işlemenizi otomatikleştirme için güçlü özellikler sunar.

### SSS

#### S: Bir Word dosyasındaki ActiveX denetimlerinin özelliklerini okumanın ilk adımı nedir?

 C: İlk adım,`Document` ActiveX denetimlerini içeren Word belgesini yükleyerek nesneyi oluşturun. Değiştirdiğinizden emin olun`MyDir` belgeyi içeren dizinin gerçek yolu ile birlikte.

#### S: ActiveX denetimlerini belgeye nasıl aktarabilirim?

 C: ActiveX denetimlerini almak için her birinde yineleme yapmanız gerekir.`Shape` belgenin bir ActiveX denetimi olup olmadığını kontrol edin. Kullan`OleFormat` mülkiyet`Shape` erişmek için`OleControl` nesneyi açın ve gerekli özellikleri alın.

#### S: ActiveX denetimlerinin hangi özelliklerini okuyabilirim?

C: ActiveX denetimlerinin başlık, değer, etkin veya devre dışı durumu, tür ve denetimle ilişkili childNode'lar gibi çeşitli özelliklerini okuyabilirsiniz.

#### S: Belgedeki ActiveX denetimlerinin toplam sayısını nasıl alabilirim?

 C: Belgedeki ActiveX denetimlerinin toplam sayısını almak için`GetChildNodes` yöntemi`Document` belirten nesne`NodeType.Shape` yazın ve alt düğümleri dahil edin.