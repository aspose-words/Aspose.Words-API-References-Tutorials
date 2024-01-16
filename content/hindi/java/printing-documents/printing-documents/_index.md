---
title: जावा के लिए Aspose.Words में दस्तावेज़ प्रिंट करना
linktitle: दस्तावेज़ मुद्रण
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को प्रिंट करना सीखें। आपके जावा अनुप्रयोगों में निर्बाध मुद्रण के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/java/printing-documents/printing-documents/
---

यदि आप Java के लिए Aspose.Words का उपयोग करके दस्तावेज़ प्रिंट करना चाह रहे हैं, तो आप सही जगह पर हैं। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको दिए गए स्रोत कोड का उपयोग करके जावा के लिए Aspose.Words के साथ दस्तावेज़ों को प्रिंट करने की प्रक्रिया के बारे में बताएंगे।

## परिचय

कई अनुप्रयोगों में दस्तावेज़ों को प्रिंट करना एक सामान्य कार्य है। जावा के लिए Aspose.Words Word दस्तावेज़ों के साथ काम करने के लिए एक शक्तिशाली एपीआई प्रदान करता है, जिसमें उन्हें प्रिंट करने की क्षमता भी शामिल है। इस ट्यूटोरियल में, हम आपको वर्ड दस्तावेज़ को चरण दर चरण प्रिंट करने की प्रक्रिया के बारे में मार्गदर्शन देंगे।

## अपना परिवेश स्थापित करना

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा डेवलपमेंट किट (जेडीके) स्थापित किया गया
- जावा लाइब्रेरी के लिए Aspose.Words डाउनलोड किया गया और आपके प्रोजेक्ट में जोड़ा गया

## दस्तावेज़ लोड हो रहा है

 आरंभ करने के लिए, आपको वह Word दस्तावेज़ लोड करना होगा जिसे आप प्रिंट करना चाहते हैं। प्रतिस्थापित करें`"Your Document Directory"` आपके दस्तावेज़ के पथ के साथ और`"Your Output Directory"` वांछित आउटपुट निर्देशिका के साथ।

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## एक मुद्रण कार्य बनाना

इसके बाद, हम अपने लोड किए गए दस्तावेज़ को प्रिंट करने के लिए एक प्रिंट जॉब बनाएंगे। नीचे दिया गया कोड स्निपेट प्रिंट कार्य प्रारंभ करता है और वांछित प्रिंटर सेटिंग्स सेट करता है।

```java
// हमारे दस्तावेज़ को प्रिंट करने के लिए एक प्रिंट जॉब बनाएं।
PrinterJob pj = PrinterJob.getPrinterJob();
//दस्तावेज़ में पृष्ठों की संख्या के साथ एक विशेषता सेट प्रारंभ करें।
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// प्रिंट दस्तावेज़ में अन्य मापदंडों के साथ प्रिंटर सेटिंग्स पास करें।
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## दस्तावेज़ मुद्रण

अब जब हमने अपना प्रिंट कार्य सेट कर लिया है, तो दस्तावेज़ को प्रिंट करने का समय आ गया है। निम्नलिखित कोड स्निपेट दस्तावेज़ को प्रिंट कार्य के साथ जोड़ता है और प्रिंटिंग प्रक्रिया शुरू करता है।

```java
// प्रिंट कार्य का उपयोग करके मुद्रित किए जाने वाले दस्तावेज़ को पास करें।
pj.setPrintable(awPrintDoc);
pj.print();
```
## संपूर्ण स्रोत कोड
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// हमारे दस्तावेज़ को प्रिंट करने के लिए एक प्रिंट जॉब बनाएं।
PrinterJob pj = PrinterJob.getPrinterJob();
//दस्तावेज़ में पृष्ठों की संख्या के साथ एक विशेषता सेट प्रारंभ करें।
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// प्रिंट दस्तावेज़ में अन्य मापदंडों के साथ प्रिंटर सेटिंग्स पास करें।
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// प्रिंट कार्य का उपयोग करके मुद्रित किए जाने वाले दस्तावेज़ को पास करें।
pj.setPrintable(awPrintDoc);
pj.print();
```
MultipagePrintDocument का स्रोत कोड
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <सारांश>
    /// कस्टम PrintDocument क्लास का कंस्ट्रक्टर।
    // /</सारांश>
    public MultipagePrintDocument(Document document, int pagesPerSheet, boolean printPageBorders,
                                  AttributeSet attributes) {
        if (document == null)
            throw new IllegalArgumentException("document");
        mDocument = document;
        mPagesPerSheet = pagesPerSheet;
        mPrintPageBorders = printPageBorders;
        mAttributeSet = attributes;
    }
    public int print(Graphics g, PageFormat pf, int page) {
        // विशेषता सेट में परिभाषित अनुसार पृष्ठ प्रारंभ और समाप्ति सूचकांक।
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // उस पेज इंडेक्स की गणना करें जिसे आगे प्रस्तुत किया जाना है।
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // यदि पृष्ठ अनुक्रमणिका कुल पृष्ठ सीमा से अधिक है तो कुछ भी नहीं है
        // प्रस्तुत करने के लिए और अधिक.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // प्रत्येक थंबनेल प्लेसहोल्डर के आकार की बिंदुओं में गणना करें।
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // कागज की इस शीट पर मुद्रित होने वाले पहले पृष्ठ की संख्या की गणना करें।
        int startPage = pagesOnCurrentSheet + fromPage;
        // कागज की इस शीट पर मुद्रित होने वाले अंतिम पृष्ठ की संख्या का चयन करें।
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //गणना करने के लिए संग्रहीत वर्तमान पृष्ठ से चयनित पृष्ठों के माध्यम से लूप करें
        // अंतिम पृष्ठ।
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // स्तंभ और पंक्ति सूचकांकों की गणना करें.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // विश्व निर्देशांक (इस मामले में अंक) में थंबनेल स्थान को परिभाषित करें।
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // बाएँ और शीर्ष आरंभिक स्थिति की गणना करें।
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // परिकलित निर्देशांकों का उपयोग करके दस्तावेज़ पृष्ठ को ग्राफ़िक्स ऑब्जेक्ट पर प्रस्तुत करें
                // और थंबनेल प्लेसहोल्डर आकार।
                // उपयोगी रिटर्न मान वह पैमाना है जिस पर पृष्ठ को प्रस्तुत किया गया था।
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // पेज की सीमाएं बनाएं (पेज थंबनेल थंबनेल से छोटा हो सकता है)।
                // प्लेसहोल्डर आकार)।
                if (mPrintPageBorders) {
                    // बिंदुओं में पृष्ठ का वास्तविक 100% आकार प्राप्त करें।
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // ज्ञात स्केल फ़ैक्टर का उपयोग करके स्केल किए गए पृष्ठ के चारों ओर बॉर्डर बनाएं।
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // थंबनेल प्लेसहोल्डर के चारों ओर बॉर्डर बनाएं.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // यदि रेंडरिंग के दौरान कोई त्रुटि हो तो कुछ न करें।
                // यदि रेंडरिंग के दौरान कोई त्रुटि हो तो यह एक खाली पृष्ठ खींच देगा।
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // शीट पर स्तंभों और पंक्तियों की संख्या निर्धारित करें
        //भूदृश्य-उन्मुख कागज़.
        switch (pagesPerSheet) {
            case 16:
                size = new Dimension(4, 4);
                break;
            case 9:
                size = new Dimension(3, 3);
                break;
            case 8:
                size = new Dimension(4, 2);
                break;
            case 6:
                size = new Dimension(3, 2);
                break;
            case 4:
                size = new Dimension(2, 2);
                break;
            case 2:
                size = new Dimension(2, 1);
                break;
            default:
                size = new Dimension(1, 1);
                break;
        }
        // यदि कागज पोर्ट्रेट ओरिएंटेशन में है तो चौड़ाई और ऊंचाई बदलें।
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## निष्कर्ष

बधाई हो! आपने Java के लिए Aspose.Words का उपयोग करके एक Word दस्तावेज़ सफलतापूर्वक मुद्रित कर लिया है। यह चरण-दर-चरण मार्गदर्शिका आपको दस्तावेज़ मुद्रण को अपने जावा अनुप्रयोगों में निर्बाध रूप से एकीकृत करने में मदद करेगी।

## पूछे जाने वाले प्रश्न

### Q1: क्या मैं जावा के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ के विशिष्ट पृष्ठ प्रिंट कर सकता हूँ?

 हाँ, आप किसी दस्तावेज़ को प्रिंट करते समय पृष्ठ सीमा निर्दिष्ट कर सकते हैं। कोड उदाहरण में, हमने उपयोग किया`attributes.add(new PageRanges(1, doc.getPageCount()))` सभी पेज प्रिंट करने के लिए. आप आवश्यकतानुसार पृष्ठ श्रेणी को समायोजित कर सकते हैं।

### Q2: क्या जावा के लिए Aspose.Words बैच प्रिंटिंग के लिए उपयुक्त है?

बिल्कुल! जावा के लिए Aspose.Words बैच प्रिंटिंग कार्यों के लिए उपयुक्त है। आप दस्तावेज़ों की सूची को दोहरा सकते हैं और समान कोड का उपयोग करके उन्हें एक-एक करके प्रिंट कर सकते हैं।

### Q3: मैं मुद्रण त्रुटियों या अपवादों को कैसे संभाल सकता हूँ?

आपको मुद्रण प्रक्रिया के दौरान होने वाले किसी भी संभावित अपवाद को संभालना चाहिए। अपवादों से निपटने के बारे में जानकारी के लिए Aspose.Words for Java दस्तावेज़ देखें।

### Q4: क्या मैं प्रिंट सेटिंग्स को और अधिक अनुकूलित कर सकता हूँ?

हाँ, आप अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए प्रिंट सेटिंग्स को अनुकूलित कर सकते हैं। उपलब्ध प्रिंट विकल्पों के बारे में अधिक जानने के लिए Aspose.Words for Java दस्तावेज़ का अन्वेषण करें।

### Q5: जावा के लिए Aspose.Words के लिए मुझे अधिक सहायता और समर्थन कहां मिल सकता है?

 अतिरिक्त सहायता और सहायता के लिए, आप यहां जा सकते हैं[जावा फोरम के लिए Aspose.Words](https://forum.aspose.com/).

---

अब जब आपने जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को प्रिंट करना सफलतापूर्वक सीख लिया है, तो आप इस कार्यक्षमता को अपने जावा अनुप्रयोगों में लागू करना शुरू कर सकते हैं। हैप्पी कोडिंग!