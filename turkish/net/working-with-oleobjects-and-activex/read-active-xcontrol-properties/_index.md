---
title: Active XControl Özelliklerini Word Dosyasından Okuyun
linktitle: Active XControl Özelliklerini Word Dosyasından Okuyun
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word dosyasındaki ActiveX kontrollerinin özelliklerini okuyun.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word dosyasındaki ActiveX kontrollerinin özelliklerini nasıl okuyacağınızı göstereceğiz. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belge başlatma

 İlk adım,`Document` ActiveX denetimlerini içeren Word belgesini yükleyerek nesne. değiştirdiğinizden emin olun`MyDir` belgeyi içeren dizinin gerçek yolu ile.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## 2. Adım: ActiveX denetimlerini kurtarın

 Bu adımda, her birini yineleyeceğiz`Shape` ActiveX denetimlerini almak ve özelliklerini okumak için belgenin

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

### Aspose.Words for .NET kullanarak Active XControl Properties'i Okumak için örnek kaynak kodu

Aspose.Words for .NET kullanarak ActiveX kontrollerinin özelliklerini okumak için eksiksiz kaynak kodu burada:

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

Bu kılavuz, Aspose.Words for .NET kullanarak bir Word dosyasındaki ActiveX kontrollerinin özelliklerini nasıl okuyacağınızı gösterdi. Açıklanan adımları izleyerek belgeyi başlatabilir, ActiveX denetimlerini alabilir ve özelliklerini okuyabilirsiniz. Sağlanan örnek kodu başlangıç noktası olarak kullanın ve kendi özel ihtiyaçlarınıza göre özelleştirin.

ActiveX denetimlerinin özelliklerini okumak, bu denetimleri içeren Word dosyalarınızdan önemli bilgileri ayıklamanıza olanak tanır. Aspose.Words for .NET, ActiveX kontrolleriyle çalışmak ve belge işlemenizi otomatikleştirmek için güçlü özellikler sunar.

### SSS

#### S: Bir Word dosyasındaki ActiveX denetimlerinin özelliklerini okumanın ilk adımı nedir?

 C: İlk adım,`Document` ActiveX denetimlerini içeren Word belgesini yükleyerek nesne. değiştirdiğinizden emin olun`MyDir` belgeyi içeren dizinin gerçek yolu ile.

#### S: ActiveX denetimlerini belgeye nasıl alabilirim?

 C: ActiveX denetimlerini almak için her birini yinelemeniz gerekir.`Shape` belgenin bir ActiveX denetimi olup olmadığını kontrol edin. Kullan`OleFormat` mülkiyet`Shape` erişmek için`OleControl` nesne ve gerekli özellikleri alın.

#### S: ActiveX denetimlerinin hangi özelliklerini okuyabilirim?

Y: ActiveX denetimlerinin başlık, değer, etkin veya devre dışı durum, tür ve denetimle ilişkili childNodes gibi çeşitli özelliklerini okuyabilirsiniz.

#### S: Belgedeki toplam ActiveX denetimi sayısını nasıl alabilirim?

 Y: Belgedeki toplam ActiveX denetimi sayısını elde etmek için,`GetChildNodes` yöntemi`Document` belirten nesne`NodeType.Shape` alt düğümleri yazın ve dahil edin.