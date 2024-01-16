---
title: वेब एक्सटेंशन टास्क पैन का उपयोग करना
linktitle: वेब एक्सटेंशन टास्क पैन का उपयोग करना
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words के साथ वेब एक्सटेंशन टास्क पैन का उपयोग करने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/net/programming-with-webextension/using-web-extension-task-panes/
---

यह आलेख .NET के लिए Aspose.Words के साथ वेब एक्सटेंशन कार्य फलक का उपयोग करने के तरीके पर चरण-दर-चरण मार्गदर्शिका प्रदान करता है। हम कोड के प्रत्येक भाग को विस्तार से समझाएंगे। इस ट्यूटोरियल के अंत में, आप यह समझ पाएंगे कि वेब एक्सटेंशन के लिए कार्य फलक कैसे जोड़ें और कॉन्फ़िगर करें।

शुरू करने से पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Words को स्थापित और कॉन्फ़िगर किया है। आप Aspose वेबसाइट पर लाइब्रेरी और इंस्टॉलेशन निर्देश पा सकते हैं।

## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें

 आरंभ करने के लिए, आपको उस निर्देशिका का पथ परिभाषित करना होगा जहां आप जेनरेट किए गए दस्तावेज़ को सहेजना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक कार्य फलक बनाएं और कॉन्फ़िगर करें

 हम एक बनाते हैं`TaskPane` ऑब्जेक्ट करें और इसे दस्तावेज़ में जोड़ें`s `WebExtensionTaskPanes` संग्रह। इसके बाद, हम कार्य फलक के गुणों को कॉन्फ़िगर करते हैं, जैसे इसकी डॉक की गई स्थिति, दृश्यता और चौड़ाई।

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

हम कैटलॉग आईडी, संस्करण और स्टोर प्रकार सहित वेब एक्सटेंशन क्रेडेंशियल भी सेट करते हैं।

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

अंत में, हम वेब एक्सटेंशन में गुण और बाइंडिंग जोड़ते हैं।

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## चरण 3: दस्तावेज़ को सहेजें और लोड करें

हम दस्तावेज़ को निर्दिष्ट निर्देशिका में कॉन्फ़िगर किए गए कार्य फलक के साथ सहेजते हैं।

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## चरण 4: कार्य फलक जानकारी प्रदर्शित करें

इसके बाद, हम दस्तावेज़ लोड करते हैं और कार्य फलक स्रोत जानकारी प्रदर्शित करते हैं।

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

बस इतना ही ! आपने .NET के लिए Aspose.Words के साथ वेब एक्सटेंशन टास्क पैन का सफलतापूर्वक उपयोग किया है।

### .NET के लिए Aspose.Words के साथ वेब एक्सटेंशन कार्य फलक का उपयोग करने के लिए उदाहरण स्रोत कोड


```csharp

	// दस्तावेज़ निर्देशिका का पथ.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	TaskPane taskPane = new TaskPane();
	doc.WebExtensionTaskPanes.Add(taskPane);

	taskPane.DockState = TaskPaneDockState.Right;
	taskPane.IsVisible = true;
	taskPane.Width = 300;

	taskPane.WebExtension.Reference.Id = "wa102923726";
	taskPane.WebExtension.Reference.Version = "1.0.0.0";
	taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
	taskPane.WebExtension.Reference.Store = "th-TH";
	taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
	taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
		WebExtensionBindingType.Text, "194740422"));

	doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	
	
	doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	Console.WriteLine("Task panes sources:\n");

	foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
	{
		WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
		Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
	}
 
```
