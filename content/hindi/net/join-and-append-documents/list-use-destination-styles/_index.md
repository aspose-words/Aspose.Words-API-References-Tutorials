---
title: गंतव्य शैलियों का उपयोग सूची
linktitle: गंतव्य शैलियों का उपयोग सूची
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words का उपयोग करके गंतव्य दस्तावेज़ की सूची शैलियों को संरक्षित करते हुए Word दस्तावेज़ों को जोड़ना और जोड़ना सीखें।
type: docs
weight: 10
url: /hi/net/join-and-append-documents/list-use-destination-styles/
---

यह ट्यूटोरियल आपको .NET के लिए Aspose.Words की सूची उपयोग गंतव्य शैलियाँ सुविधा का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा। यह सुविधा आपको गंतव्य दस्तावेज़ की सूची शैलियों का उपयोग करते हुए Word दस्तावेज़ों को जोड़ने और जोड़ने की अनुमति देती है।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. Aspose.Words for .NET इंस्टॉल किया गया है। आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं या NuGet के माध्यम से इंस्टॉल कर सकते हैं।
2. विजुअल स्टूडियो या कोई अन्य C# विकास वातावरण।

## चरण 1: दस्तावेज़ निर्देशिकाएँ आरंभ करें

 सबसे पहले, आपको अपने दस्तावेज़ निर्देशिका का पथ सेट करना होगा।`dataDir` चर को उस पथ पर जोड़ें जहां आपके दस्तावेज़ स्थित हैं.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: स्रोत और गंतव्य दस्तावेज़ लोड करें

इसके बाद, आपको Aspose.Words का उपयोग करके स्रोत और गंतव्य दस्तावेज़ों को लोड करना होगा`Document` क्लास में फ़ाइल नाम अपडेट करें.`Document` अपने दस्तावेज़ के नाम के अनुसार कन्स्ट्रक्टर का चयन करें।

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## चरण 3: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ के बाद जारी रखने के लिए सेट करें

 यह सुनिश्चित करने के लिए कि स्रोत दस्तावेज़ की सामग्री गंतव्य दस्तावेज़ के अंत के बाद भी जारी रहे, आपको सेट करना होगा`SectionStart` स्रोत दस्तावेज़ में पहले खंड की संपत्ति`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## चरण 4: सूची स्वरूपण संभालें

सूची स्वरूपण को संभालने के लिए, आप स्रोत दस्तावेज़ में प्रत्येक पैराग्राफ़ को दोहराएँगे और जाँचेंगे कि क्या यह एक सूची आइटम है। यदि यह है, तो आप गंतव्य दस्तावेज़ में मौजूदा सूचियों के साथ सूची आईडी की तुलना करेंगे। यदि समान आईडी वाली कोई सूची मौजूद है, तो आप स्रोत दस्तावेज़ में सूची की एक प्रतिलिपि बनाएंगे और कॉपी की गई सूची का उपयोग करने के लिए पैराग्राफ़ के सूची प्रारूप को अपडेट करेंगे।

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## चरण 5: स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ें

 अब, आप स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ में जोड़ सकते हैं`AppendDocument` की विधि`Document` वर्ग.`ImportFormatMode.UseDestinationStyles` पैरामीटर यह सुनिश्चित करता है कि गंतव्य दस्तावेज़ की सूची शैलियों का उपयोग परिशिष्ट ऑपरेशन के दौरान किया जाता है।

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## चरण 6: अंतिम दस्तावेज़ सहेजें

अंत में, मर्ज किए गए दस्तावेज़ को सूची उपयोग गंतव्य शैलियाँ सुविधा सक्षम करके सहेजें`Save` की विधि`Document` कक्षा।

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### .NET के लिए Aspose.Words का उपयोग करके सूची गंतव्य शैलियों के उपयोग के लिए उदाहरण स्रोत कोड 

.NET के लिए Aspose.Words का उपयोग करके C# में "सूची उपयोग गंतव्य शैलियाँ" सुविधा के लिए पूर्ण स्रोत कोड यहां दिया गया है:


```csharp
	// आपके दस्तावेज़ निर्देशिका का पथ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ के अंत के ठीक बाद जारी रखने के लिए सेट करें।
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// बनाई गई सूचियों पर नज़र रखें।
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// जाँच करें कि क्या गंतव्य दस्तावेज़ में पहले से ही इस आईडी वाली सूची मौजूद है। अगर ऐसा है, तो यह हो सकता है
			// दो सूचियों को एक साथ चलाने का कारण बनें। इसके बजाय स्रोत दस्तावेज़ में सूची की एक प्रतिलिपि बनाएँ।
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// इस आईडी के लिए एक नई कॉपी की गई सूची पहले से मौजूद है, संग्रहीत सूची पुनः प्राप्त करें,
				// और इसे वर्तमान पैराग्राफ पर उपयोग करें.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// इस सूची की एक प्रति दस्तावेज़ में जोड़ें और बाद में संदर्भ के लिए संग्रहीत करें।
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// इस पैराग्राफ की सूची को कॉपी की गई सूची पर सेट करें.
				para.ListFormat.List = currentList;
			}
		}
	}
	// स्रोत दस्तावेज़ को गंतव्य दस्तावेज़ के अंत में जोड़ें.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

बस! आपने .NET के लिए Aspose.Words का उपयोग करके सूची उपयोग गंतव्य शैलियाँ सुविधा को सफलतापूर्वक लागू कर दिया है। अंतिम दस्तावेज़ में गंतव्य दस्तावेज़ से सूची शैलियों के साथ मर्ज की गई सामग्री शामिल होगी।