---
title: मेल मर्ज पर दस्तावेज़ डालें
linktitle: मेल मर्ज पर दस्तावेज़ डालें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: इस व्यापक, चरण-दर-चरण ट्यूटोरियल में जानें कि .NET के लिए Aspose.Words का उपयोग करके मेल मर्ज फ़ील्ड में दस्तावेज़ कैसे सम्मिलित करें।
type: docs
weight: 10
url: /hi/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## परिचय

.NET के लिए Aspose.Words के साथ दस्तावेज़ स्वचालन की दुनिया में आपका स्वागत है! क्या आपने कभी सोचा है कि मेल मर्ज ऑपरेशन के दौरान मुख्य दस्तावेज़ के भीतर विशिष्ट फ़ील्ड में दस्तावेज़ों को गतिशील रूप से कैसे सम्मिलित किया जाए? ख़ैर, आप सही जगह पर हैं। यह ट्यूटोरियल आपको .NET के लिए Aspose.Words का उपयोग करके मेल मर्ज फ़ील्ड में दस्तावेज़ सम्मिलित करने की प्रक्रिया के माध्यम से चरण-दर-चरण मार्गदर्शन करेगा। यह एक पहेली को जोड़ने जैसा है, जहां प्रत्येक टुकड़ा पूरी तरह से अपनी जगह पर आ जाता है। तो, आइए गोता लगाएँ!

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1.  Aspose.NET के लिए शब्द: आप कर सकते हैं[डाउनलोड का नवीनतम संस्करण यहां](https://releases.aspose.com/words/net/) . यदि आपको लाइसेंस खरीदने की आवश्यकता है, तो आप ऐसा कर सकते हैं[यहाँ](https://purchase.aspose.com/buy) . वैकल्पिक रूप से, आप एक प्राप्त कर सकते हैं[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) या इसे a के साथ आज़माएँ[मुफ्त परीक्षण](https://releases.aspose.com/).
2. विकास परिवेश: विज़ुअल स्टूडियो या कोई अन्य C# IDE।
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग से परिचित होने से यह ट्यूटोरियल आसान हो जाएगा।

## नामस्थान आयात करें

सबसे पहली बात, आपको आवश्यक नामस्थान आयात करने की आवश्यकता होगी। ये आपके प्रोजेक्ट के बिल्डिंग ब्लॉक्स की तरह हैं।

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

आइए इस प्रक्रिया को प्रबंधनीय चरणों में विभाजित करें। प्रत्येक चरण पिछले चरण पर आधारित होगा, जो आपको पूर्ण समाधान की ओर ले जाएगा।

## चरण 1: अपनी निर्देशिका स्थापित करना

इससे पहले कि आप दस्तावेज़ सम्मिलित करना शुरू कर सकें, आपको अपनी दस्तावेज़ निर्देशिका का पथ परिभाषित करना होगा। यह वह जगह है जहां आपके दस्तावेज़ संग्रहीत हैं।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: मुख्य दस्तावेज़ लोड करना

इसके बाद, आप मुख्य दस्तावेज़ लोड करेंगे। इस दस्तावेज़ में मर्ज फ़ील्ड शामिल हैं जहां अन्य दस्तावेज़ डाले जाएंगे।

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## चरण 3: फ़ील्ड मर्जिंग कॉलबैक सेट करना

विलय प्रक्रिया को संभालने के लिए, आपको कॉलबैक फ़ंक्शन सेट करना होगा। यह फ़ंक्शन निर्दिष्ट मर्ज फ़ील्ड में दस्तावेज़ सम्मिलित करने के लिए ज़िम्मेदार होगा।

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## चरण 4: मेल मर्ज निष्पादित करना

अब मेल मर्ज निष्पादित करने का समय आ गया है। यहां जादू पैदा होता है। आप मर्ज फ़ील्ड और उस दस्तावेज़ को निर्दिष्ट करेंगे जिसे इस फ़ील्ड में डाला जाना चाहिए।

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## चरण 5: दस्तावेज़ सहेजना

मेल मर्ज पूरा होने के बाद, आप संशोधित दस्तावेज़ सहेज लेंगे। इस नए दस्तावेज़ में सामग्री वहीं डाली जाएगी जहां आप इसे चाहते हैं।

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## चरण 6: कॉलबैक हैंडलर बनाना

कॉलबैक हैंडलर एक वर्ग है जो मर्ज फ़ील्ड के लिए विशेष प्रसंस्करण करता है। यह फ़ील्ड मान में निर्दिष्ट दस्तावेज़ को लोड करता है और इसे वर्तमान मर्ज फ़ील्ड में सम्मिलित करता है।

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## चरण 7: दस्तावेज़ सम्मिलित करना

यह विधि निर्दिष्ट दस्तावेज़ को वर्तमान पैराग्राफ या तालिका सेल में सम्मिलित करती है।

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## निष्कर्ष

आखिर तुमने इसे हासिल कर ही लिया है! आपने .NET के लिए Aspose.Words का उपयोग करके मेल मर्ज ऑपरेशन के दौरान दस्तावेज़ों को विशिष्ट फ़ील्ड में सफलतापूर्वक सम्मिलित कर लिया है। यह शक्तिशाली सुविधा आपका ढेर सारा समय और मेहनत बचा सकती है, खासकर बड़ी मात्रा में दस्तावेज़ों के साथ काम करते समय। इसे ऐसे समझें कि आपके पास एक निजी सहायक है जो आपके सारे भारी काम संभालता है। तो, आगे बढ़ें और इसे आज़माएं। हैप्पी कोडिंग!

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं अलग-अलग मर्ज फ़ील्ड में एकाधिक दस्तावेज़ सम्मिलित कर सकता हूँ?
 हाँ तुम कर सकते हो। बस उपयुक्त मर्ज फ़ील्ड और संबंधित दस्तावेज़ पथ निर्दिष्ट करें`MailMerge.Execute` तरीका।

### क्या सम्मिलित दस्तावेज़ को मुख्य दस्तावेज़ से अलग प्रारूपित करना संभव है?
 बिल्कुल! आप इसका उपयोग कर सकते हैं`ImportFormatMode` में पैरामीटर`NodeImporter` फ़ॉर्मेटिंग को नियंत्रित करने के लिए.

### यदि मर्ज फ़ील्ड नाम गतिशील है तो क्या होगा?
आप डायनामिक मर्ज फ़ील्ड नामों को कॉलबैक हैंडलर के पैरामीटर के रूप में पास करके संभाल सकते हैं।

### क्या मैं इस पद्धति का उपयोग विभिन्न फ़ाइल स्वरूपों के साथ कर सकता हूँ?
हाँ, Aspose.Words DOCX, PDF और अन्य सहित विभिन्न फ़ाइल स्वरूपों का समर्थन करता है।

### मैं दस्तावेज़ प्रविष्टि प्रक्रिया के दौरान त्रुटियों से कैसे निपटूँ?
होने वाले किसी भी अपवाद को प्रबंधित करने के लिए अपने कॉलबैक हैंडलर में त्रुटि प्रबंधन लागू करें।