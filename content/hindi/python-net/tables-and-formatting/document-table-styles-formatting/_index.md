---
title: Aspose.Words Python का उपयोग करके दस्तावेज़ तालिका शैलियाँ और स्वरूपण
linktitle: दस्तावेज़ तालिका शैलियाँ और स्वरूपण
second_title: Aspose.Words Python दस्तावेज़ प्रबंधन API
description: Python के लिए Aspose.Words का उपयोग करके दस्तावेज़ तालिकाओं को स्टाइल और फ़ॉर्मेट करना सीखें। चरण-दर-चरण मार्गदर्शिकाओं और कोड उदाहरणों के साथ तालिकाएँ बनाएं, अनुकूलित करें और निर्यात करें। आज ही अपने दस्तावेज़ प्रस्तुतीकरण को बेहतर बनाएं!
type: docs
weight: 12
url: /hi/python-net/tables-and-formatting/document-table-styles-formatting/
---

दस्तावेज़ तालिकाएँ जानकारी को व्यवस्थित और आकर्षक तरीके से प्रस्तुत करने में महत्वपूर्ण भूमिका निभाती हैं। Aspose.Words for Python टूल का एक शक्तिशाली सेट प्रदान करता है जो डेवलपर्स को तालिकाओं के साथ कुशलतापूर्वक काम करने और उनकी शैलियों और स्वरूपण को अनुकूलित करने की अनुमति देता है। इस लेख में, हम यह पता लगाएंगे कि पायथन एपीआई के लिए Aspose.Words का उपयोग करके दस्तावेज़ तालिकाओं में हेरफेर और सुधार कैसे किया जाए। आइए गोता लगाएँ!

## पायथन के लिए Aspose.Words के साथ शुरुआत करना

इससे पहले कि हम दस्तावेज़ तालिका शैलियों और स्वरूपण की बारीकियों में उतरें, आइए सुनिश्चित करें कि आपके पास आवश्यक उपकरण सेट हैं:

1. पायथन के लिए Aspose.Words इंस्टॉल करें: पाइप का उपयोग करके Aspose.Words लाइब्रेरी इंस्टॉल करके शुरुआत करें। यह निम्नलिखित कमांड से किया जा सकता है:
   
    ```bash
    pip install aspose-words
    ```

2. लाइब्रेरी आयात करें: निम्नलिखित आयात कथन का उपयोग करके Aspose.Words लाइब्रेरी को अपनी पायथन स्क्रिप्ट में आयात करें:

    ```python
    import aspose.words
    ```

3. दस्तावेज़ लोड करें: किसी मौजूदा दस्तावेज़ को लोड करें या Aspose.Words API का उपयोग करके एक नया दस्तावेज़ बनाएं।

## दस्तावेज़ों में तालिकाएँ बनाना और सम्मिलित करना

Aspose.Words for Python का उपयोग करके दस्तावेज़ों में तालिकाएँ बनाने और सम्मिलित करने के लिए, इन चरणों का पालन करें:

1.  एक तालिका बनाएं: इसका उपयोग करें`DocumentBuilder` एक नई तालिका बनाने और पंक्तियों और स्तंभों की संख्या निर्दिष्ट करने के लिए क्लास।

    ```python
    builder = aspose.words.DocumentBuilder(doc)
    table = builder.start_table()
    ```

2.  डेटा सम्मिलित करें: बिल्डर का उपयोग करके तालिका में डेटा जोड़ें`insert_cell` और`write` तरीके.

    ```python
    builder.insert_cell()
    builder.write("Header 1")
    builder.insert_cell()
    builder.write("Header 2")
    builder.end_row()
    ```

3. पंक्तियाँ दोहराएँ: समान पैटर्न का अनुसरण करते हुए आवश्यकतानुसार पंक्तियाँ और सेल जोड़ें।

4.  दस्तावेज़ में तालिका सम्मिलित करें: अंत में, का उपयोग करके तालिका को दस्तावेज़ में सम्मिलित करें`end_table` तरीका।

    ```python
    builder.end_table()
    ```

## मूल तालिका फ़ॉर्मेटिंग लागू करना

 द्वारा प्रदान की गई विधियों का उपयोग करके मूल तालिका स्वरूपण प्राप्त किया जा सकता है`Table` और`Cell` कक्षाएं. यहां बताया गया है कि आप अपनी तालिका का स्वरूप कैसे बढ़ा सकते हैं:

1. कॉलम की चौड़ाई निर्धारित करें: उचित संरेखण और दृश्य अपील सुनिश्चित करने के लिए कॉलम की चौड़ाई समायोजित करें।

    ```python
    for cell in table.first_row.cells:
        cell.cell_format.preferred_width = aspose.words.PreferredWidth.from_points(100)
    ```

2. सेल पैडिंग: बेहतर रिक्ति के लिए सेल में पैडिंग जोड़ें।

    ```python
    for row in table.rows:
        for cell in row.cells:
            cell.cell_format.set_paddings(10, 10, 10, 10)
    ```

3. पंक्ति की ऊँचाई: पंक्ति की ऊँचाई को आवश्यकतानुसार अनुकूलित करें।

    ```python
    for row in table.rows:
        row.row_format.height_rule = aspose.words.HeightRule.AT_LEAST
        row.row_format.height = aspose.words.ConvertUtil.inch_to_points(1)
    ```

## Aspose.Words के साथ स्टाइलिंग टेबल्स

Aspose.Words for Python आपकी तालिकाओं को आकर्षक बनाने के लिए स्टाइलिंग विकल्पों की एक श्रृंखला प्रदान करता है:

1. टेबल शैलियाँ: पेशेवर लुक पाने के लिए पूर्वनिर्धारित टेबल शैलियाँ लागू करें।

    ```python
    table.style = aspose.words.StyleIdentifier.LIGHT_LIST_ACCENT_5
    ```

2. सेल पृष्ठभूमि रंग: विशिष्ट डेटा को हाइलाइट करने के लिए सेल पृष्ठभूमि रंग बदलें।

    ```python
    cell.cell_format.shading.background_pattern_color = aspose.words.Color.from_rgb(240, 240, 240)
    ```

3. फ़ॉन्ट फ़ॉर्मेटिंग: बेहतर पठनीयता के लिए फ़ॉन्ट शैली, आकार और रंग को अनुकूलित करें।

    ```python
    run = cell.paragraphs[0].runs[0]
    run.font.size = aspose.words.Size(12, aspose.words.SizeUnit.POINTS)
    run.font.color = aspose.words.Color.from_rgb(0, 0, 0)
    ```

## जटिल लेआउट के लिए कोशिकाओं का विलय और विभाजन

जटिल तालिका लेआउट बनाने के लिए अक्सर कोशिकाओं के विलय और विभाजन की आवश्यकता होती है:

1. सेल मर्ज करें: एक बड़ा सेल बनाने के लिए कई सेल को मर्ज करें।

    ```python
    table.rows[0].cells[0].cell_format.horizontal_merge = aspose.words.CellMerge.FIRST
    table.rows[0].cells[1].cell_format.horizontal_merge = aspose.words.CellMerge.PREVIOUS
    ```

2. विभाजित कोशिकाएँ: कोशिकाओं को वापस उनके व्यक्तिगत घटकों में विभाजित करना।

    ```python
    cell.cell_format.horizontal_merge = aspose.words.CellMerge.NONE
    ```

## पंक्ति और स्तंभ की ऊँचाई और चौड़ाई का समायोजन

संतुलित तालिका लेआउट के लिए पंक्ति और स्तंभ आयामों को ठीक करें:

1. पंक्ति की ऊँचाई समायोजित करें: सामग्री के आधार पर पंक्ति की ऊँचाई को संशोधित करें।

    ```python
    row.row_format.height_rule = aspose.words.HeightRule.AUTO
    ```

2. कॉलम की चौड़ाई समायोजित करें: सामग्री को फिट करने के लिए कॉलम की चौड़ाई स्वचालित रूप से समायोजित करें।

    ```python
    table.auto_fit(auto_fit_behaviour=aspose.words.AutoFitBehaviour.AUTO_FIT_TO_CONTENTS)
    ```

## तालिकाओं में बॉर्डर और शेडिंग जोड़ना

बॉर्डर और शेडिंग जोड़कर तालिका का स्वरूप बढ़ाएँ:

1. बॉर्डर्स: टेबल और सेल के लिए बॉर्डर कस्टमाइज़ करें।

    ```python
    table.set_borders(0.5, aspose.words.LineStyle.SINGLE, aspose.words.Color.from_rgb(0, 0, 0))
    ```

2. छायांकन: दिखने में आकर्षक प्रभाव के लिए कोशिकाओं पर छायांकन लागू करें।

    ```python
    cell.cell_format.shading.background_pattern_color = aspose.words.Color.from_rgb(230, 230, 230)
    ```

## सेल सामग्री और संरेखण के साथ कार्य करना

बेहतर पठनीयता के लिए सेल सामग्री और संरेखण को कुशलतापूर्वक प्रबंधित करें:

1. सेल सामग्री: सेल में सामग्री, जैसे पाठ और छवियाँ, सम्मिलित करें।

    ```python
    builder.insert_cell()
    builder.write("Hello, Aspose!")
    ```

2. टेक्स्ट संरेखण: सेल टेक्स्ट को आवश्यकतानुसार संरेखित करें।

    ```python
    cell.paragraphs[0].paragraph_format.alignment = aspose.words.ParagraphAlignment.CENTER
    ```

## टेबल हेडर और फूटर को संभालना

बेहतर संदर्भ के लिए अपनी तालिकाओं में शीर्षलेख और पादलेख शामिल करें:

1. टेबल हेडर: पहली पंक्ति को हेडर पंक्ति के रूप में सेट करें।

    ```python
    table.rows[0].row_format.is_header = True
    ```

2. तालिका पाद लेख: अतिरिक्त जानकारी के लिए पाद लेख पंक्ति बनाएँ

    ```python
    footer_row = table.append_row()
    footer_row.cells[0].cell_format.horizontal_merge = aspose.words.CellMerge.NONE
    footer_row.cells[0].paragraphs[0].runs[0].text = "Total"
    ```
	
## टेबल लेआउट को स्वचालित रूप से समायोजित करना

सुनिश्चित करें कि आपकी तालिका का लेआउट सामग्री के आधार पर स्वचालित रूप से समायोजित हो जाता है:

1. विंडो में स्वतः फ़िट: तालिका को पृष्ठ की चौड़ाई में फ़िट होने दें।

    ```python
    table.allow_auto_fit = True
    ```

2. सेल का स्वत: आकार बदलें: सामग्री को समायोजित करने के लिए स्वचालित सेल आकार बदलने को सक्षम करें।

    ```python
    table.auto_fit(auto_fit_behaviour=aspose.words.AutoFitBehaviour.AUTO_FIT_TO_WINDOW)
    ```

## विभिन्न प्रारूपों में तालिकाएँ निर्यात करना

एक बार आपकी तालिका तैयार हो जाने पर, आप इसे विभिन्न स्वरूपों में निर्यात कर सकते हैं, जैसे PDF या DOCX:

1. पीडीएफ के रूप में सहेजें: तालिका के साथ दस्तावेज़ को पीडीएफ फाइल के रूप में सहेजें।

    ```python
    doc.save("table_document.pdf", aspose.words.SaveFormat.PDF)
    ```

2. DOCX के रूप में सहेजें: दस्तावेज़ को DOCX फ़ाइल के रूप में सहेजें।

    ```python
    doc.save("table_document.docx", aspose.words.SaveFormat.DOCX)
    ```

## प्रभावी तालिका प्रबंधन के लिए समस्या निवारण और युक्तियाँ

- यदि तालिकाएँ विकृत दिखाई देती हैं, तो गलत कॉलम चौड़ाई या पंक्ति ऊँचाई की जाँच करें।
- स्थिरता सुनिश्चित करने के लिए विभिन्न प्रारूपों में टेस्ट टेबल रेंडरिंग।
- जटिल लेआउट के लिए, सेल विलय और विभाजन की योजना सावधानीपूर्वक बनाएं।

## निष्कर्ष

Aspose.Words for Python दस्तावेज़ तालिकाएँ बनाने, स्टाइल करने और फ़ॉर्मेट करने के लिए एक व्यापक टूलकिट प्रदान करता है। इस आलेख में उल्लिखित चरणों का पालन करके, आप अपने दस्तावेज़ों में तालिकाओं को प्रभावी ढंग से प्रबंधित कर सकते हैं, उनकी उपस्थिति को अनुकूलित कर सकते हैं और उन्हें विभिन्न प्रारूपों में निर्यात कर सकते हैं। अपने दस्तावेज़ प्रस्तुतियों को बेहतर बनाने और अपने पाठकों को स्पष्ट, आकर्षक जानकारी प्रदान करने के लिए Aspose.Words की शक्ति का उपयोग करें।

## पूछे जाने वाले प्रश्न

### मैं Python के लिए Aspose.Words कैसे स्थापित करूं?

Python के लिए Aspose.Words इंस्टॉल करने के लिए, निम्नलिखित कमांड का उपयोग करें: 

```bash
pip install aspose-words
```

### क्या मैं अपनी तालिकाओं में कस्टम शैलियाँ लागू कर सकता हूँ?

हाँ, आप Aspose.Words का उपयोग करके विभिन्न गुणों जैसे फ़ॉन्ट, रंग और बॉर्डर को संशोधित करके अपनी तालिकाओं में कस्टम शैलियाँ लागू कर सकते हैं।

### क्या किसी तालिका में कोशिकाओं को मर्ज करना संभव है?

 हाँ, आप इसका उपयोग करके तालिका में कक्षों को मर्ज कर सकते हैं`CellMerge` Aspose.Words द्वारा प्रदान की गई संपत्ति।

### मैं अपनी तालिकाओं को विभिन्न प्रारूपों में कैसे निर्यात करूं?

 आप इसका उपयोग करके अपनी तालिकाओं को PDF या DOCX जैसे विभिन्न प्रारूपों में निर्यात कर सकते हैं`save` विधि और वांछित प्रारूप निर्दिष्ट करना।

### मैं Python के लिए Aspose.Words के बारे में और अधिक कहां से जान सकता हूं?

 व्यापक दस्तावेज़ीकरण और संदर्भों के लिए, जाएँ[पायथन एपीआई संदर्भों के लिए Aspose.Words](https://reference.aspose.com/words/python-net/).
