---
title: Word दस्तावेज़ों में शीर्षलेख और पादलेख में हेरफेर करना
linktitle: Word दस्तावेज़ों में शीर्षलेख और पादलेख में हेरफेर करना
second_title: Aspose.Words Python दस्तावेज़ प्रबंधन API
description: Python के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ों में शीर्षलेख और पादलेख में हेरफेर करना सीखें। अनुकूलित करने, जोड़ने, हटाने और बहुत कुछ के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका। अब अपने दस्तावेज़ स्वरूपण को बेहतर बनाएं!
type: docs
weight: 16
url: /hi/python-net/document-structure-and-content-manipulation/document-headers-footers/
---
Word दस्तावेज़ों में शीर्षलेख और पादलेख आपकी सामग्री को संदर्भ, ब्रांडिंग और अतिरिक्त जानकारी प्रदान करने में महत्वपूर्ण भूमिका निभाते हैं। Aspose.Words for Python API का उपयोग करके इन तत्वों में हेरफेर करने से आपके दस्तावेज़ों की उपस्थिति और कार्यक्षमता में उल्लेखनीय वृद्धि हो सकती है। इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि पायथन के लिए Aspose.Words का उपयोग करके हेडर और फ़ुटर के साथ कैसे काम किया जाए।


## पायथन के लिए Aspose.Words के साथ शुरुआत करना

हेडर और फ़ुटर हेरफेर में गोता लगाने से पहले, आपको पायथन के लिए Aspose.Words सेट अप करना होगा। इन चरणों का पालन करें:

1. इंस्टालेशन: पिप का उपयोग करके पायथन के लिए Aspose.Words इंस्टॉल करें।

```python
pip install aspose-words
```

2. मॉड्यूल आयात करना: अपनी पायथन लिपि में आवश्यक मॉड्यूल आयात करें।

```python
import aspose.words
```

## एक साधारण शीर्षलेख और पादलेख जोड़ना

अपने Word दस्तावेज़ में एक मूल शीर्षलेख और पादलेख जोड़ने के लिए, इन चरणों का पालन करें:

1. दस्तावेज़ बनाना: Aspose.Words का उपयोग करके एक नया Word दस्तावेज़ बनाएं।

```python
doc = aspose.words.Document()
```

2.  शीर्षलेख और पादलेख जोड़ना: का उपयोग करें`sections` अनुभागों तक पहुँचने के लिए दस्तावेज़ की संपत्ति। फिर, का उपयोग करें`headers_footers` शीर्षलेख और पादलेख जोड़ने के लिए संपत्ति।

```python
section = doc.sections[0]
header = section.headers_footers[aspose.words.HeaderFooterType.HEADER_PRIMARY]
footer = section.headers_footers[aspose.words.HeaderFooterType.FOOTER_PRIMARY]
```

3. सामग्री जोड़ना: शीर्ष लेख और पाद लेख में सामग्री जोड़ें।

```python
header_paragraph = header.paragraphs.add()
header_run = header_paragraph.runs.add()
header_run.text = "This is the header text."

footer_paragraph = footer.paragraphs.add()
footer_run = footer_paragraph.runs.add()
footer_run.text = "Page number: {PAGE} of {NUMPAGES}"
```

4. दस्तावेज़ को सहेजना: दस्तावेज़ को शीर्षलेख और पादलेख के साथ सहेजें।

```python
doc.save("document_with_header_footer.docx")
```

## शीर्षलेख और पादलेख सामग्री को अनुकूलित करना

आप चित्र, तालिकाएँ और गतिशील फ़ील्ड जोड़कर शीर्ष लेख और पाद लेख सामग्री को अनुकूलित कर सकते हैं। उदाहरण के लिए:

1. छवियाँ जोड़ना: शीर्ष लेख या पाद लेख में छवियाँ सम्मिलित करें।

```python
image_path = "path_to_your_image.png"
header_run.add_picture(image_path)
```

2. तालिकाएँ जोड़ना: सारणीबद्ध जानकारी के लिए तालिकाएँ शामिल करें।

```python
footer_table = footer.add_table(1, 2)
footer_table.rows[0].cells[0].text = "Copyright © 2023"
footer_table.rows[0].cells[1].text = "All rights reserved."
```

3. डायनामिक फ़ील्ड: स्वचालित डेटा प्रविष्टि के लिए डायनामिक फ़ील्ड का उपयोग करें।

```python
footer_run.text = "Page number: {PAGE} of {NUMPAGES} - Document created on {DATE}"
```

## विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख और पाद लेख

विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख और पादलेख बनाना आपके दस्तावेज़ों में एक पेशेवर स्पर्श जोड़ सकता है। ऐसे:

1. विषम और सम पृष्ठ लेआउट सेट करना: विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख और पाद लेख की अनुमति देने के लिए लेआउट को परिभाषित करें।

```python
section = doc.sections[0]
section.page_setup.different_first_page_header_footer = True
section.page_setup.odd_and_even_pages_header_footer = True
```

2. शीर्षलेख और पादलेख जोड़ना: पहले पृष्ठ, विषम पृष्ठों और सम पृष्ठों के लिए शीर्षलेख और पादलेख जोड़ें।

```python
header_first = section.headers_footers[aspose.words.HeaderFooterType.HEADER_FIRST]
footer_first = section.headers_footers[aspose.words.HeaderFooterType.FOOTER_FIRST]
header_odd = section.headers_footers[aspose.words.HeaderFooterType.HEADER_EVEN]
footer_odd = section.headers_footers[aspose.words.HeaderFooterType.FOOTER_EVEN]
header_even = section.headers_footers[aspose.words.HeaderFooterType.HEADER_ODD]
footer_even = section.headers_footers[aspose.words.HeaderFooterType.FOOTER_ODD]
```

3. आवश्यकतानुसार अनुकूलित करें: प्रत्येक शीर्षलेख और पादलेख को अपनी आवश्यकताओं के अनुसार अनुकूलित करें।

## शीर्षलेख और पाद लेख हटाना

किसी Word दस्तावेज़ से शीर्षलेख और पादलेख हटाने के लिए:

1. शीर्षलेख और पाद लेख हटाना: शीर्ष लेख और पाद लेख की सामग्री साफ़ करें।

```python
header.clear_content()
footer.clear_content()
```

2. विभिन्न शीर्षलेखों/पादलेखों को अक्षम करना: यदि आवश्यक हो तो विषम और सम पृष्ठों के लिए विभिन्न शीर्षलेखों और पादलेखों को अक्षम करें।

```python
section.page_setup.different_first_page_header_footer = False
section.page_setup.odd_and_even_pages_header_footer = False
```

## पूछे जाने वाले प्रश्न

### मैं शीर्ष लेख और पाद लेख सामग्री तक कैसे पहुँच सकता हूँ?

 शीर्षलेख और पादलेख सामग्री तक पहुँचने के लिए, का उपयोग करें`headers_footers` दस्तावेज़ के अनुभाग की संपत्ति.

### क्या मैं शीर्षलेखों और पादलेखों में छवियाँ जोड़ सकता हूँ?

 हां, आप इसका उपयोग करके हेडर और फ़ूटर में छवियां जोड़ सकते हैं`add_picture` तरीका।

### क्या विषम और सम पृष्ठों के लिए अलग-अलग शीर्षक रखना संभव है?

बिल्कुल, आप उपयुक्त सेटिंग्स को सक्षम करके विषम और सम पृष्ठों के लिए अलग-अलग शीर्षलेख और पादलेख बना सकते हैं।

### क्या मैं विशिष्ट पृष्ठों से शीर्षलेख और पादलेख हटा सकता हूँ?

हाँ, आप शीर्षलेखों और पादलेखों की सामग्री को प्रभावी ढंग से हटाने के लिए उन्हें साफ़ कर सकते हैं।

### मैं Python के लिए Aspose.Words के बारे में और अधिक कहां से जान सकता हूं?

अधिक विस्तृत दस्तावेज़ीकरण और उदाहरणों के लिए, पर जाएँ[पायथन एपीआई संदर्भ के लिए Aspose.Words](https://reference.aspose.com/words/python-net/).
