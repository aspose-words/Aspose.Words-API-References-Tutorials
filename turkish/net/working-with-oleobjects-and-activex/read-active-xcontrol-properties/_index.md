---
title: Active XControl Özelliklerini Oku
linktitle: Active XControl Özelliklerini Oku
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki ActiveX kontrollerinin özelliklerini okuyun.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki ActiveX kontrollerinin özelliklerini nasıl okuyacağınızı göstereceğiz. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

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

