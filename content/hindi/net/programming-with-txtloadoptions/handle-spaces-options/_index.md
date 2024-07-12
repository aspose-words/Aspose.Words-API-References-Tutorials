---
title: रिक्त स्थान विकल्प संभालें
linktitle: रिक्त स्थान विकल्प संभालें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: .NET के लिए Aspose.Words के साथ अपने TXT दस्तावेज़ों में रिक्त स्थान प्रबंधित करना सीखें। अनावश्यक रिक्त स्थान निकालें और पठनीयता में सुधार करें।
type: docs
weight: 10
url: /hi/net/programming-with-txtloadoptions/handle-spaces-options/
---

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Words के साथ "TXT लोडिंग विकल्पों के साथ स्पेस को प्रबंधित करने" की कार्यक्षमता के लिए प्रदान किए गए C# स्रोत कोड का पता लगाने जा रहे हैं। यह सुविधा आपको TXT दस्तावेज़ लोड करते समय रिक्त स्थान प्रबंधन व्यवहार निर्दिष्ट करने की अनुमति देती है।

## चरण 1: वातावरण की स्थापना

आरंभ करने से पहले, सुनिश्चित करें कि आपने .NET के लिए Aspose.Words के साथ अपना विकास वातावरण सेट अप कर लिया है। सुनिश्चित करें कि आपने आवश्यक संदर्भ जोड़ दिए हैं और उचित नामस्थान आयात कर लिए हैं।

## चरण 2: टेक्स्ट दस्तावेज़ बनाना

```csharp
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

इस चरण में, हम एक टेक्स्ट स्ट्रिंग बनाते हैं जो आरंभिक और अंतिम रिक्त स्थान वाली पंक्तियों वाले टेक्स्ट दस्तावेज़ का अनुकरण करता है।

## चरण 3: अपलोड विकल्प कॉन्फ़िगर करना

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

 इस चरण में, हम TXT दस्तावेज़ लोड करने के लिए विकल्पों को कॉन्फ़िगर करते हैं। हम एक नया दस्तावेज़ बनाते हैं`TxtLoadOptions` ऑब्जेक्ट और सेट करें`LeadingSpacesOptions`और`TrailingSpacesOptions` गुण`TxtLeadingSpacesOptions.Trim`और`TxtTrailingSpacesOptions.Trim` यह Aspose.Words को दस्तावेज़ लोड करते समय लाइनों से आरंभिक और अंतिम रिक्त स्थान हटाने के लिए कहता है।

## चरण 4: दस्तावेज़ लोड करना

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

 इस चरण में, हम दस्तावेज़ को लोड करते हैं`Document` विधि और निर्दिष्ट पाठ स्ट्रिंग और लोड विकल्प युक्त मेमोरी स्ट्रीम को पास करना।

## चरण 5: दस्तावेज़ सहेजें

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

 इस अंतिम चरण में, हम परिणामी दस्तावेज़ को .docx प्रारूप में सहेजते हैं`Save` विधि और आउटपुट फ़ाइल के लिए पथ पारित करना।

अब आप रिक्त स्थान प्रबंधन विकल्प निर्दिष्ट करके टेक्स्ट दस्तावेज़ लोड करने के लिए स्रोत कोड चला सकते हैं। परिणामी दस्तावेज़ निर्दिष्ट निर्देशिका में "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx" नाम से सहेजा जाएगा।

### .NET के लिए Aspose.Words के साथ TXT लोडिंग विकल्पों के साथ स्पेस प्रबंधन सुविधा के लिए नमूना स्रोत कोड*

```csharp

            
// आपके दस्तावेज़ निर्देशिका का पथ
string dataDir = "YOUR DOCUMENT DIRECTORY";

const string textDoc = "      Line 1 \n" +
					   "    Line 2   \n" +
					   " Line 3       ";

TxtLoadOptions loadOptions = new TxtLoadOptions
{
	LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
	TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx")
            
        
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Words में TXT लोडिंग विकल्पों के साथ रिक्त स्थान प्रबंधित करने की कार्यक्षमता का पता लगाया। हमने सीखा कि TXT दस्तावेज़ लोड करते समय रिक्त स्थान प्रबंधन व्यवहार को कैसे निर्दिष्ट किया जाए।

यह सुविधा दस्तावेज़ में लाइनों के बाईं और दाईं ओर अनावश्यक रिक्त स्थान से निपटने के लिए बहुत उपयोगी है। उचित लोडिंग विकल्पों को कॉन्फ़िगर करके, आप इन अवांछित रिक्त स्थानों को आसानी से हटा सकते हैं, जो दस्तावेज़ की सामग्री को साफ़ और अधिक पठनीय बनाने में मदद करता है।

Aspose.Words for .NET दस्तावेज़ में हेरफेर और निर्माण के लिए कई उन्नत सुविधाएँ प्रदान करता है। TXT दस्तावेज़ लोड करते समय रिक्त स्थान का प्रबंधन करना आपके निपटान में उपलब्ध कई शक्तिशाली उपकरणों में से एक है।

 अपने विशिष्ट परिदृश्य के लिए सबसे उपयुक्त स्थान प्रबंधन विकल्प चुनना महत्वपूर्ण है। इस उदाहरण में, हमने इसका उपयोग किया है`Trim`लाइन की शुरुआत और अंत से अनावश्यक रिक्त स्थान हटाने के विकल्प। हालाँकि, Aspose.Words में रिक्त स्थान रखने, उन्हें पूरी तरह से हटाने या उन्हें वैसे ही रखने के अन्य विकल्प भी हैं।

अपनी विशिष्ट आवश्यकताओं और अपने TXT दस्तावेज़ों की संरचना के अनुसार इन विकल्पों को अनुकूलित करना न भूलें।

.NET के लिए Aspose.Words के साथ, आप आसानी से अपने दस्तावेज़ों में रिक्त स्थान में हेरफेर कर सकते हैं, लेआउट गुणवत्ता और सामग्री पठनीयता में सुधार कर सकते हैं।

इसलिए, अपने Aspose.Words for .NET प्रोजेक्ट्स में TXT लोडिंग विकल्पों के साथ रिक्त स्थान प्रबंधन को एकीकृत करने में संकोच न करें और अच्छी तरह से प्रारूपित और पढ़ने में आसान दस्तावेज़ बनाने के लिए इसके लाभों का लाभ उठाएं।