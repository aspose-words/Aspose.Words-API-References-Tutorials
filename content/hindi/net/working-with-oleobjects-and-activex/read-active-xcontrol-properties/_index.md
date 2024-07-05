---
title: वर्ड फ़ाइल से Active XControl गुण पढ़ें
linktitle: वर्ड फ़ाइल से Active XControl गुण पढ़ें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ Word फ़ाइल में ActiveX नियंत्रणों के गुण पढ़ें।
type: docs
weight: 10
url: /hi/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Words का उपयोग करके Word फ़ाइल में ActiveX नियंत्रणों के गुणों को कैसे पढ़ा जाए। हम आपको पूरा स्रोत कोड प्रदान करेंगे और आपको दिखाएंगे कि मार्कडाउन आउटपुट को कैसे प्रारूपित किया जाए।

## चरण 1: दस्तावेज़ आरंभीकरण

 पहला कदम आरंभीकरण करना है`Document` ActiveX नियंत्रण वाले Word दस्तावेज़ को लोड करके ऑब्जेक्ट को बदलें।`MyDir` दस्तावेज़ युक्त निर्देशिका के वास्तविक पथ के साथ।

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## चरण 2: ActiveX नियंत्रण पुनर्प्राप्त करें

 इस चरण में, हम प्रत्येक चरण को दोहराएंगे`Shape` ActiveX नियंत्रणों को पुनः प्राप्त करने और उनके गुणों को पढ़ने के लिए दस्तावेज़ के मुख्य भाग पर जाएँ।

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

### .NET के लिए Aspose.Words का उपयोग करके Active XControl गुण पढ़ने के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके ActiveX नियंत्रणों के गुणों को पढ़ने के लिए यहां पूर्ण स्रोत कोड दिया गया है:

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

## निष्कर्ष

इस गाइड में आपको Aspose.Words for .NET का उपयोग करके Word फ़ाइल में ActiveX नियंत्रणों के गुणों को पढ़ने का तरीका दिखाया गया है। वर्णित चरणों का पालन करके, आप दस्तावेज़ को आरंभ कर सकते हैं, ActiveX नियंत्रणों को पुनः प्राप्त कर सकते हैं और उनके गुणों को पढ़ सकते हैं। प्रारंभिक बिंदु के रूप में दिए गए नमूना कोड का उपयोग करें और इसे अपनी विशिष्ट आवश्यकताओं के अनुसार अनुकूलित करें।

ActiveX नियंत्रणों के गुणों को पढ़ने से आप इन नियंत्रणों वाली अपनी Word फ़ाइलों से महत्वपूर्ण जानकारी निकाल सकते हैं। Aspose.Words for .NET ActiveX नियंत्रणों के साथ Words प्रोसेसिंग और आपके दस्तावेज़ प्रोसेसिंग को स्वचालित करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है।

### पूछे जाने वाले प्रश्न

#### प्रश्न: किसी वर्ड फ़ाइल में ActiveX नियंत्रणों के गुणों को पढ़ने के लिए पहला चरण क्या है?

 उत्तर: पहला कदम आरंभीकरण करना है`Document` ActiveX नियंत्रण वाले Word दस्तावेज़ को लोड करके ऑब्जेक्ट को बदलें।`MyDir` दस्तावेज़ युक्त निर्देशिका के वास्तविक पथ के साथ।

#### प्रश्न: मैं दस्तावेज़ में ActiveX नियंत्रण कैसे प्राप्त करूं?

 उत्तर: ActiveX नियंत्रणों को पुनः प्राप्त करने के लिए, आपको प्रत्येक के माध्यम से पुनरावृति करनी होगी`Shape` दस्तावेज़ का चयन करें और जाँचें कि क्या यह ActiveX नियंत्रण है।`OleFormat` की संपत्ति`Shape` तक पहुंचने के लिए`OleControl` ऑब्जेक्ट और आवश्यक गुण पुनः प्राप्त करें.

#### प्रश्न: मैं ActiveX नियंत्रणों के कौन से गुण पढ़ सकता हूँ?

उत्तर: आप ActiveX नियंत्रणों के विभिन्न गुणों को पढ़ सकते हैं, जैसे कैप्शन, मान, सक्षम या अक्षम स्थिति, प्रकार, और नियंत्रण से संबद्ध childNodes.

#### प्रश्न: मैं दस्तावेज़ में ActiveX नियंत्रणों की कुल संख्या कैसे प्राप्त कर सकता हूँ?

 उत्तर: दस्तावेज़ में ActiveX नियंत्रणों की कुल संख्या प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`GetChildNodes` की विधि`Document` वस्तु निर्दिष्ट करना`NodeType.Shape` प्रकार और चाइल्ड नोड्स सहित.