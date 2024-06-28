---
title: Java के लिए Aspose.Words में दस्तावेज़ों से सामग्री हटाना
linktitle: दस्तावेज़ों से सामग्री हटाना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words का उपयोग करके जावा में Word दस्तावेज़ों से सामग्री को हटाने का तरीका जानें। पृष्ठ विराम, अनुभाग विराम और बहुत कुछ हटाएँ। अपने दस्तावेज़ प्रसंस्करण को अनुकूलित करें।
type: docs
weight: 16
url: /hi/java/document-manipulation/removing-content-from-documents/
---

## जावा के लिए Aspose.Words का परिचय

इससे पहले कि हम निष्कासन तकनीकों में उतरें, आइए संक्षेप में जावा के लिए Aspose.Words का परिचय दें। यह एक जावा एपीआई है जो वर्ड दस्तावेज़ों के साथ काम करने के लिए व्यापक सुविधाएँ प्रदान करता है। आप इस लाइब्रेरी का उपयोग करके Word दस्तावेज़ों को निर्बाध रूप से बना, संपादित, परिवर्तित और हेरफेर कर सकते हैं।

## पेज ब्रेक हटाना

पेज ब्रेक का उपयोग अक्सर दस्तावेज़ के लेआउट को नियंत्रित करने के लिए किया जाता है। हालाँकि, ऐसे मामले भी हो सकते हैं जहाँ आपको उन्हें हटाने की आवश्यकता हो। यहां बताया गया है कि आप जावा के लिए Aspose.Words का उपयोग करके पेज ब्रेक कैसे हटा सकते हैं:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
for (Paragraph para : (Iterable<Paragraph>) paragraphs) {
    if (para.getParagraphFormat().getPageBreakBefore()) {
        para.getParagraphFormat().setPageBreakBefore(false);
    }
    for (Run run : para.getRuns()) {
        if (run.getText().contains(ControlChar.PAGE_BREAK)) {
            run.setText(run.getText().replace(ControlChar.PAGE_BREAK, ""));
        }
    }
}
doc.save("Your Directory Path" + "RemoveContent.RemovePageBreaks.docx");
```

यह कोड स्निपेट दस्तावेज़ में पैराग्राफों के माध्यम से पुनरावृत्त होगा, पेज ब्रेक की जाँच करेगा और उन्हें हटा देगा।

## सेक्शन ब्रेक हटाना

अनुभाग विराम किसी दस्तावेज़ को अलग-अलग स्वरूपण के साथ अलग-अलग अनुभागों में विभाजित करते हैं। अनुभाग विराम हटाने के लिए, इन चरणों का पालन करें:

```java
for (int i = doc.getSections().getCount() - 2; i >= 0; i--) {
    doc.getLastSection().prependContent(doc.getSections().get(i));
    doc.getSections().get(i).remove();
}
```

यह कोड अनुभागों के माध्यम से उल्टे क्रम में पुनरावृत्त होता है, वर्तमान अनुभाग की सामग्री को पिछले अनुभाग के साथ जोड़ता है और फिर कॉपी किए गए अनुभाग को हटा देता है।

## फ़ुटर हटाना

Word दस्तावेज़ों में फ़ुटर में अक्सर पृष्ठ संख्याएँ, दिनांक या अन्य जानकारी होती है। यदि आपको उन्हें हटाने की आवश्यकता है, तो आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
Document doc = new Document("Your Directory Path" + "Header and footer types.docx");
for (Section section : doc.getSections()) {
    HeaderFooter footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_FIRST);
    footer.remove();
    footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
    footer.remove();
    footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_EVEN);
    footer.remove();
}
doc.save("Your Directory Path" + "RemoveContent.RemoveFooters.docx");
```

यह कोड दस्तावेज़ के प्रत्येक अनुभाग से सभी प्रकार के पादलेख (प्रथम, प्राथमिक और यहां तक कि) को हटा देता है।

## विषय-सूची हटाना

सामग्री तालिका (टीओसी) फ़ील्ड एक गतिशील तालिका उत्पन्न करती है जो शीर्षकों और उनके पृष्ठ संख्याओं को सूचीबद्ध करती है। TOC को हटाने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
Document doc = new Document("Your Directory Path" + "Table of contents.docx");
removeTableOfContents(doc, 0);
doc.save("Your Directory Path" + "RemoveContent.RemoveToc.doc");
```

 यह कोड एक विधि को परिभाषित करता है`removeTableOfContents` जो दस्तावेज़ से निर्दिष्ट TOC को हटा देता है।


## निष्कर्ष

इस लेख में, हमने पता लगाया है कि Java के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों से विभिन्न प्रकार की सामग्री को कैसे हटाया जाए। चाहे वह पृष्ठ विराम हो, अनुभाग विराम हो, पादलेख हो, या सामग्री तालिका हो, Aspose.Words आपके दस्तावेज़ों में प्रभावी ढंग से हेरफेर करने के लिए उपकरण प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं विशिष्ट पृष्ठ विराम कैसे हटा सकता हूँ?

विशिष्ट पृष्ठ विराम को हटाने के लिए, अपने दस्तावेज़ में अनुच्छेदों के माध्यम से पुनरावृति करें और वांछित अनुच्छेदों के लिए पृष्ठ विराम विशेषता को साफ़ करें।

### क्या मैं पादलेख के साथ-साथ शीर्षलेख भी हटा सकता हूँ?

हाँ, आप उसी दृष्टिकोण का पालन करके अपने दस्तावेज़ से शीर्षलेख और पादलेख दोनों को हटा सकते हैं जैसा कि पाद लेख के लेख में दिखाया गया है।

### क्या जावा के लिए Aspose.Words नवीनतम वर्ड दस्तावेज़ प्रारूपों के साथ संगत है?

हां, जावा के लिए Aspose.Words आधुनिक दस्तावेज़ों के साथ अनुकूलता सुनिश्चित करते हुए नवीनतम Word दस्तावेज़ स्वरूपों का समर्थन करता है।

### Aspose.Words for Java क्या अन्य दस्तावेज़ हेरफेर सुविधाएँ प्रदान करता है?

जावा के लिए Aspose.Words दस्तावेज़ निर्माण, संपादन, रूपांतरण और बहुत कुछ सहित सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है। विस्तृत जानकारी के लिए आप इसके दस्तावेज़ देख सकते हैं।