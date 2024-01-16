---
title: Word दस्तावेज़ में सामग्री तालिका हटाएँ
linktitle: Word दस्तावेज़ में सामग्री तालिका हटाएँ
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में सामग्री तालिका को हटाने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/remove-content/remove-table-of-contents/
---
इस ट्यूटोरियल में, हम आपको बताएंगे कि .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके किसी Word दस्तावेज़ में सामग्री तालिका को कैसे हटाया जाए। सामग्री तालिका कभी-कभी निरर्थक या अनावश्यक हो सकती है, और यह कोड आपको इसे प्रभावी ढंग से हटाने में मदद करेगा। हम आपको अपने .NET प्रोजेक्ट में कोड को समझने और लागू करने में मदद करने के लिए चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित चीज़ें हैं:
- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान
- आपके प्रोजेक्ट में .NET के लिए Aspose.Words लाइब्रेरी स्थापित है
- एक Word दस्तावेज़ जिसमें सामग्री की एक तालिका है जिसे आप हटाना चाहते हैं

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
 सबसे पहले, आपको अपने Word दस्तावेज़ के स्थान पर निर्देशिका पथ सेट करना होगा। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` उचित पथ के साथ कोड में।

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ अपलोड करें
 इसके बाद, हम Word दस्तावेज़ को एक उदाहरण में लोड करेंगे`Document` क्लास का उपयोग कर रहा हूँ`Load` तरीका।

```csharp
// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "your-document.docx");
```

## चरण 3: सामग्री तालिका हटाएँ
 सामग्री तालिका को हटाने के लिए, हम TOC (सामग्री तालिका) प्रकार के माध्यम से लूप करेंगे`FieldStart` दस्तावेज़ में नोड्स. हम इन नोड्स को संग्रहीत करेंगे ताकि हम उन तक तुरंत पहुंच सकें और हटाने के लिए नोड्स की एक सूची बना सकें।

```csharp
// त्वरित पहुंच के लिए दस्तावेज़ में टीओसी फ़ील्ड के फ़ील्डस्टार्ट नोड्स को संग्रहीत करें।
List<FieldStart> fieldStarts = new List<FieldStart>();
// यह निर्दिष्ट टीओसी के अंदर पाए गए नोड्स को संग्रहीत करने के लिए एक सूची है। इस विधि के अंत में उन्हें हटा दिया जाएगा.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// जांचें कि क्या निर्दिष्ट टीओसी सूचकांक मौजूद है।
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // इन नोड्स को संग्रहीत करना और अंत में उन सभी को हटा देना अधिक सुरक्षित है।
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // जब हमें फ़ील्डTOC प्रकार का फ़ील्डएंड नोड मिलता है,
     //हम जानते हैं कि हम वर्तमान टीओसी के अंत पर हैं और हम यहीं रुकते हैं।
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### .NET के लिए Aspose.Words का उपयोग करके सामग्री तालिका हटाने के लिए नमूना स्रोत कोड 
```csharp

// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "your-document.docx");

// त्वरित पहुंच के लिए दस्तावेज़ में टीओसी फ़ील्ड के फ़ील्डस्टार्ट नोड्स को संग्रहीत करें।
List<FieldStart> fieldStarts = new List<FieldStart>();
// यह निर्दिष्ट टीओसी के अंदर पाए गए नोड्स को संग्रहीत करने के लिए एक सूची है। इस विधि के अंत में उन्हें हटा दिया जाएगा.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// सुनिश्चित करें कि पारित सूचकांक द्वारा निर्दिष्ट टीओसी मौजूद है।
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// इन नोड्स को संग्रहीत करना और बाद में उन सभी को एक साथ हटा देना अधिक सुरक्षित है।
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// एक बार जब हमें फ़ील्डTOC प्रकार का फ़ील्डएंड नोड मिलता है,
	// हम जानते हैं कि हम वर्तमान टीओसी के अंत पर हैं और यहीं रुकते हैं।
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words लाइब्रेरी का उपयोग करके किसी Word दस्तावेज़ से सामग्री तालिका को हटाने के लिए चरण-दर-चरण मार्गदर्शिका प्रस्तुत की है। दिए गए कोड और निर्देशों का पालन करके, आप सामग्री तालिका को आसानी से हटा सकते हैं और अपने दस्तावेज़ के लेआउट में सुधार कर सकते हैं। अपनी विशिष्ट आवश्यकताओं के अनुरूप निर्देशिका पथ और फ़ाइल नामों को अनुकूलित करना याद रखें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मुझे Word दस्तावेज़ में सामग्री तालिका को हटाने के लिए Aspose.Words का उपयोग क्यों करना चाहिए?

उत्तर: Aspose.Words .NET अनुप्रयोगों में Word दस्तावेज़ों में हेरफेर करने के लिए एक शक्तिशाली और बहुमुखी क्लास लाइब्रेरी है। Aspose.Words का उपयोग करके, आप अपने दस्तावेज़ों से सामग्री तालिका को प्रभावी ढंग से हटा सकते हैं, जो सामग्री तालिका अनावश्यक या अनावश्यक होने पर उपयोगी हो सकती है। यह आपको अपने दस्तावेज़ की सामग्री को अनुकूलित करने और उसकी समग्र प्रस्तुति में सुधार करने की अनुमति देता है।

#### प्रश्न: मैं .NET के लिए Aspose.Words में दस्तावेज़ कैसे अपलोड करूं?

उ: किसी Word दस्तावेज़ में सामग्री तालिका को हटाने के लिए, आपको पहले Aspose.Words की Load() विधि का उपयोग करके दस्तावेज़ को मेमोरी में लोड करना होगा। किसी विशिष्ट निर्देशिका से दस्तावेज़ लोड करने के लिए नमूना कोड यहां दिया गया है:

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ लोड करें
Document doc = new Document(dataDir + "your-document.docx");
```

 प्रतिस्थापित करें`"YOUR DOCUMENTS DIRECTORY"` आपके दस्तावेज़ के वास्तविक पथ के साथ।

#### प्रश्न: मैं Aspose.Words का उपयोग करके किसी दस्तावेज़ में सामग्री तालिका को कैसे हटाऊं?

 उ: टीओसी को हटाने के लिए, आपको इसके माध्यम से पुनरावृत्त करना होगा`FieldStart` दस्तावेज़ में TOC के नोड टाइप करें। आप त्वरित पहुंच के लिए इन नोड्स को संग्रहीत कर सकते हैं और हटाने के लिए नोड्स की एक सूची बना सकते हैं। यहाँ एक नमूना कोड है:

```csharp
// त्वरित पहुंच के लिए दस्तावेज़ में टीओसी फ़ील्ड के फ़ील्डस्टार्ट नोड्स को संग्रहीत करें।
List<FieldStart> fieldStarts = new List<FieldStart>();
//यह निर्दिष्ट टीओसी के अंदर पाए जाने वाले नोड्स को संग्रहीत करने की एक सूची है। इस विधि के अंत में उन्हें हटा दिया जाएगा.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// जांचें कि सामग्री अनुक्रमणिका की निर्दिष्ट तालिका मौजूद है या नहीं।
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// इन नोड्स को संग्रहीत करना और अंत में उन सभी को हटा देना अधिक सुरक्षित है।
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// जब हमें फ़ील्डTOC प्रकार का फ़ील्डएंड नोड मिलता है,
//हम जानते हैं कि हम वर्तमान टीओसी के अंत पर हैं और हम यहीं रुकते हैं।
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### प्रश्न: संपादित दस्तावेज़ को .NET के लिए Aspose.Words में कैसे सहेजें?

उ: सामग्री तालिका को हटाने के बाद, आपको Save() विधि का उपयोग करके संशोधित दस्तावेज़ को सहेजना होगा। संपादित दस्तावेज़ के लिए वांछित आउटपुट फ़ाइल पथ और प्रारूप (उदाहरण के लिए, DOCX) निर्दिष्ट करें। यहाँ एक नमूना कोड है:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```