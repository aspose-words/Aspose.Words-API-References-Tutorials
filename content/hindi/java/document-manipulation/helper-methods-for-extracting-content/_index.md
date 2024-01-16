---
title: जावा के लिए Aspose.Words में सामग्री निकालने के लिए सहायक तरीके
linktitle: सामग्री निकालने के लिए सहायक तरीके
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों से सामग्री को कुशलतापूर्वक निकालने का तरीका जानें। इस व्यापक मार्गदर्शिका में सहायक तरीकों, कस्टम फ़ॉर्मेटिंग और बहुत कुछ का अन्वेषण करें।
type: docs
weight: 14
url: /hi/java/document-manipulation/helper-methods-for-extracting-content/
---

## जावा के लिए Aspose.Words में सामग्री निकालने के लिए सहायक तरीकों का परिचय

जावा के लिए Aspose.Words एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Word दस्तावेज़ों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है। Word दस्तावेज़ों के साथ काम करते समय एक सामान्य कार्य उनसे सामग्री निकालना है। इस लेख में, हम जावा के लिए Aspose.Words का उपयोग करके सामग्री को कुशलतापूर्वक निकालने के लिए कुछ सहायक तरीकों का पता लगाएंगे।

## आवश्यक शर्तें

इससे पहले कि हम कोड उदाहरणों पर विचार करें, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Words for Java स्थापित और सेटअप है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/).

## सहायक विधि 1: शैली के अनुसार अनुच्छेद निकालना

```java
public static ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    // निर्दिष्ट शैली के पैराग्राफ एकत्र करने के लिए एक सरणी बनाएं।
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);

    // निर्दिष्ट शैली वाले अनुच्छेदों को खोजने के लिए सभी अनुच्छेदों को देखें।
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}
```

आप इस विधि का उपयोग उन अनुच्छेदों को निकालने के लिए कर सकते हैं जिनकी आपके Word दस्तावेज़ में एक विशिष्ट शैली है। यह तब उपयोगी होता है जब आप किसी विशेष फ़ॉर्मेटिंग, जैसे शीर्षक या ब्लॉक उद्धरण, के साथ सामग्री निकालना चाहते हैं।

## सहायक विधि 2: नोड्स द्वारा सामग्री निकालना

```java
public static ArrayList<Node> extractContentBetweenNodes(Node startNode, Node endNode, boolean isInclusive) {
    // सबसे पहले, जांचें कि इस पद्धति को दिए गए नोड्स उपयोग के लिए मान्य हैं।
    verifyParameterNodes(startNode, endNode);
    
    // निकाले गए नोड्स को संग्रहीत करने के लिए एक सूची बनाएं।
    ArrayList<Node> nodes = new ArrayList<Node>();

    // यदि कोई भी मार्कर किसी टिप्पणी का हिस्सा है, जिसमें टिप्पणी भी शामिल है, तो हमें पॉइंटर को स्थानांतरित करने की आवश्यकता है
    // CommentRangeEnd नोड के बाद पाए गए टिप्पणी नोड पर अग्रेषित करें।
    if (endNode.getNodeType() == NodeType.COMMENT_RANGE_END && isInclusive) {
        Node node = findNextNode(NodeType.COMMENT, endNode.getNextSibling());
        if (node != null)
            endNode = node;
    }
    
    // यदि आवश्यक हो तो मार्कर नोड्स को विभाजित करने के लिए इस विधि से पारित मूल नोड्स का रिकॉर्ड रखें।
    Node originalStartNode = startNode;
    Node originalEndNode = endNode;

    //ब्लॉक-स्तरीय नोड्स (पैराग्राफ और तालिकाओं) के आधार पर सामग्री निकालें। उन्हें ढूंढने के लिए मूल नोड्स के माध्यम से पार करें।
    // हम पहले और आखिरी नोड्स की सामग्री को विभाजित करेंगे, यह इस बात पर निर्भर करेगा कि मार्कर नोड्स इनलाइन हैं या नहीं।
    startNode = getAncestorInBody(startNode);
    endNode = getAncestorInBody(endNode);
    boolean isExtracting = true;
    boolean isStartingNode = true;
    // वर्तमान नोड हम दस्तावेज़ से निकाल रहे हैं।
    Node currNode = startNode;

    // सामग्री निकालना प्रारंभ करें. सभी ब्लॉक-स्तरीय नोड्स को संसाधित करें और विशेष रूप से पहले को विभाजित करें
    // और आवश्यकता पड़ने पर अंतिम नोड्स ताकि पैराग्राफ़ स्वरूपण बरकरार रखा जा सके।
    // यह विधि नियमित एक्सट्रैक्टर की तुलना में थोड़ी अधिक जटिल है क्योंकि हमें कारक की आवश्यकता होती है
    // इसे उपयोगी बनाने के लिए इनलाइन नोड्स, फ़ील्ड्स, बुकमार्क्स इत्यादि का उपयोग करके निकालने में।
    while (isExtracting) {
        // एक प्रति प्राप्त करने के लिए वर्तमान नोड और उसके बच्चों को क्लोन करें।
        Node cloneNode = currNode.deepClone(true);
        boolean isEndingNode = currNode.equals(endNode);
        if (isStartingNode || isEndingNode) {
            // हमें प्रत्येक मार्कर को अलग से संसाधित करने की आवश्यकता है, इसलिए इसके बजाय इसे एक अलग विधि में पास करें।
            // नोड इंडेक्स को बनाए रखने के लिए सबसे पहले एंड को संसाधित किया जाना चाहिए।
            if (isEndingNode) {
                // !isStartingNode: यदि मार्कर एक ही नोड हैं तो नोड को दो बार न जोड़ें।
                processMarker(cloneNode, nodes, originalEndNode, currNode, isInclusive,
                        false, !isStartingNode, false);
                isExtracting = false;
            }
            //सशर्त को अलग करने की आवश्यकता है क्योंकि ब्लॉक स्तर के प्रारंभ और अंत मार्कर एक ही नोड हो सकते हैं।
            if (isStartingNode) {
                processMarker(cloneNode, nodes, originalStartNode, currNode, isInclusive,
                        true, true, false);
                isStartingNode = false;
            }
        } else
            // नोड प्रारंभ या अंत मार्कर नहीं है, बस प्रतिलिपि को सूची में जोड़ें।
            nodes.add(cloneNode);

        // अगले नोड पर जाएँ और इसे निकालें। यदि अगला नोड शून्य है,
        // शेष सामग्री एक अलग अनुभाग में पाई जाती है।
        if (currNode.getNextSibling() == null && isExtracting) {
            // अगले भाग पर जाएँ.
            Section nextSection = (Section) currNode.getAncestor(NodeType.SECTION).getNextSibling();
            currNode = nextSection.getBody().getFirstChild();
        } else {
            // शरीर में अगले नोड पर जाएँ.
            currNode = currNode.getNextSibling();
        }
    }

    // इनलाइन बुकमार्क के साथ मोड की अनुकूलता के लिए, अगला पैराग्राफ (खाली) जोड़ें।
    if (isInclusive && originalEndNode == endNode && !originalEndNode.isComposite())
        includeNextParagraph(endNode, nodes);

    // नोड मार्करों के बीच नोड्स लौटाएँ।
    return nodes;
}
```

यह विधि आपको दो निर्दिष्ट नोड्स के बीच सामग्री निकालने की अनुमति देती है, चाहे वे पैराग्राफ, टेबल या कोई अन्य ब्लॉक-स्तरीय तत्व हों। यह इनलाइन मार्कर, फ़ील्ड और बुकमार्क सहित विभिन्न परिदृश्यों को संभालता है।

## सहायक विधि 3: एक नया दस्तावेज़ तैयार करना

```java
public static Document generateDocument(Document srcDoc, ArrayList<Node> nodes) throws Exception {
    Document dstDoc = new Document();
    
    // खाली दस्तावेज़ से पहला पैराग्राफ़ हटाएँ।
    dstDoc.getFirstSection().getBody().removeAllChildren();
    
    // सूची से प्रत्येक नोड को नए दस्तावेज़ में आयात करें। नोड का मूल स्वरूपण रखें.
    NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
    for (Node node : nodes) {
        Node importNode = importer.importNode(node, true);
        dstDoc.getFirstSection().getBody().appendChild(importNode);
    }
    
    return dstDoc;
}
```

यह विधि आपको स्रोत दस्तावेज़ से नोड्स की सूची आयात करके एक नया दस्तावेज़ बनाने की अनुमति देती है। यह नोड्स के मूल स्वरूपण को बरकरार रखता है, जिससे यह विशिष्ट सामग्री के साथ नए दस्तावेज़ बनाने के लिए उपयोगी हो जाता है।

## निष्कर्ष

Word दस्तावेज़ों से सामग्री निकालना कई दस्तावेज़ प्रसंस्करण कार्यों का एक महत्वपूर्ण हिस्सा हो सकता है। जावा के लिए Aspose.Words शक्तिशाली सहायक विधियाँ प्रदान करता है जो इस प्रक्रिया को सरल बनाती हैं। चाहे आपको शैली के अनुसार पैराग्राफ निकालने की आवश्यकता हो, नोड्स के बीच की सामग्री, या नए दस्तावेज़ तैयार करने की आवश्यकता हो, ये विधियां आपके जावा अनुप्रयोगों में वर्ड दस्तावेज़ों के साथ कुशलतापूर्वक काम करने में आपकी सहायता करेंगी।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Words कैसे स्थापित कर सकता हूं?

 जावा के लिए Aspose.Words इंस्टॉल करने के लिए, आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं। मिलने जाना[यहाँ](https://releases.aspose.com/words/java/) नवीनतम संस्करण प्राप्त करने के लिए.

### क्या मैं किसी Word दस्तावेज़ के विशिष्ट अनुभागों से सामग्री निकाल सकता हूँ?

हाँ, आप इस आलेख में उल्लिखित विधियों का उपयोग करके किसी Word दस्तावेज़ के विशिष्ट अनुभागों से सामग्री निकाल सकते हैं। बस आरंभ और अंत नोड्स निर्दिष्ट करें जो उस अनुभाग को परिभाषित करते हैं जिसे आप निकालना चाहते हैं।

### क्या जावा के लिए Aspose.Words जावा 11 के साथ संगत है?

हां, जावा के लिए Aspose.Words जावा 11 और उच्चतर संस्करणों के साथ संगत है। आप इसे अपने जावा एप्लिकेशन में बिना किसी समस्या के उपयोग कर सकते हैं।

### क्या मैं निकाली गई सामग्री के स्वरूपण को अनुकूलित कर सकता हूँ?

हां, आप जेनरेट किए गए दस्तावेज़ में आयातित नोड्स को संशोधित करके निकाली गई सामग्री के स्वरूपण को अनुकूलित कर सकते हैं। जावा के लिए Aspose.Words आपकी आवश्यकताओं को पूरा करने के लिए व्यापक स्वरूपण विकल्प प्रदान करता है।

### जावा के लिए Aspose.Words के लिए मुझे अधिक दस्तावेज़ और उदाहरण कहां मिल सकते हैं?

 आप Aspose वेबसाइट पर Java के लिए Aspose.Words के लिए व्यापक दस्तावेज़ और उदाहरण पा सकते हैं। मिलने जाना[https://reference.aspose.com/words/java/](https://reference.aspose.com/words/java/) विस्तृत दस्तावेज़ीकरण और संसाधनों के लिए।