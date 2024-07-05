---
title: मर्ज फ़ील्ड का नाम बदलें
linktitle: मर्ज फ़ील्ड का नाम बदलें
second_title: Aspose.Words दस्तावेज़ प्रसंस्करण API
description: इस ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मर्ज फ़ील्ड का नाम कैसे बदला जाए।
type: docs
weight: 10
url: /hi/net/working-with-fields/rename-merge-fields/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है जो .NET के लिए Aspose.Words की मर्ज फ़ील्ड नाम बदलने की सुविधा का उपयोग करती है। वांछित परिणाम प्राप्त करने के लिए प्रत्येक चरण का सावधानीपूर्वक पालन करें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए कोड में, आपको अपने दस्तावेज़ों की निर्देशिका निर्दिष्ट करनी होगी। "आपकी दस्तावेज़ निर्देशिका" मान को अपने दस्तावेज़ निर्देशिका के लिए उपयुक्त पथ से बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ बनाना और मर्ज फ़ील्ड सम्मिलित करना

हम एक नया दस्तावेज़ बनाकर और एक का उपयोग करके शुरू करते हैं`DocumentBuilder` मर्ज फ़ील्ड सम्मिलित करने के लिए.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## चरण 3: मर्ज फ़ील्ड का नाम बदलना

हम दस्तावेज़ श्रेणी में प्रत्येक फ़ील्ड के माध्यम से लूप करते हैं, और यदि यह एक मर्ज फ़ील्ड है, तो हम " जोड़कर फ़ील्ड का नाम बदलते हैं_"नाम बदला गया" प्रत्यय.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## चरण 4: दस्तावेज़ को सहेजना

 अंत में, हम कॉल करते हैं`Save()` संशोधित दस्तावेज़ को सहेजने की विधि.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### .NET के लिए Aspose.Words के साथ मर्ज फ़ील्ड का नाम बदलने के लिए स्रोत कोड उदाहरण

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ बनाएं और मर्ज फ़ील्ड डालें.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// मर्ज फ़ील्ड का नाम बदलें.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// दस्तावेज़ सहेजें.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

.NET के लिए Aspose.Words का उपयोग करके अपने दस्तावेज़ में मर्ज फ़ील्ड का नाम बदलने के लिए इन चरणों का पालन करें।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का नाम कैसे बदल सकता हूँ?

 उत्तर: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का नाम बदलने के लिए, आप दस्तावेज़ में फ़ील्ड के माध्यम से लूप कर सकते हैं`FieldMergingArgs` क्लास और का उपयोग करें`FieldMergingArgs.FieldName` फ़ील्ड का नाम बदलने की विधि.

#### प्रश्न: क्या Aspose.Words for .NET के साथ Word दस्तावेज़ में केवल कुछ मर्ज किए गए फ़ील्ड का नाम बदलना संभव है?

उत्तर: हाँ, Aspose.Words for .NET के साथ Word दस्तावेज़ में केवल कुछ मर्ज किए गए फ़ील्ड का नाम बदलना संभव है। आप विशिष्ट मानदंडों, जैसे फ़ील्ड नाम या अन्य प्रासंगिक गुणों का उपयोग करके फ़िल्टर कर सकते हैं कि किन फ़ील्ड का नाम बदलना है। फिर आप संबंधित फ़ील्ड का नाम बदल सकते हैं`FieldMergingArgs.FieldName` तरीका।

#### प्रश्न: मैं कैसे जांच सकता हूं कि Aspose.Words for .NET के साथ Word दस्तावेज़ में किसी मर्ज किए गए फ़ील्ड का नाम सफलतापूर्वक बदला गया है या नहीं?

 उत्तर: यह जाँचने के लिए कि क्या Aspose.Words for .NET के साथ Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का नाम सफलतापूर्वक बदला गया है, आप इसका उपयोग कर सकते हैं`FieldMergedArgs` कक्षा और पहुँच`FieldMergedArgs.IsMerged` संपत्ति का उपयोग यह निर्धारित करने के लिए करें कि क्या फ़ील्ड का नाम हिट के साथ बदला गया था।

#### प्रश्न: Aspose.Words for .NET के साथ Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का नाम बदलने के क्या परिणाम हैं?

उत्तर: जब आप Aspose.Words for .NET के साथ Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का नाम बदलते हैं, तो यह दस्तावेज़ में फ़ील्ड का नाम बदल देता है, जो फ़ील्ड नाम पर निर्भर अन्य कार्यक्षमता या प्रक्रियाओं को प्रभावित कर सकता है। मर्ज किए गए फ़ील्ड का नाम बदलने से पहले इन संभावित परिणामों पर विचार करना सुनिश्चित करें।

#### प्रश्न: क्या Aspose.Words for .NET के साथ नाम बदलने के बाद किसी मर्ज किए गए फ़ील्ड के मूल नाम को पुनर्स्थापित करना संभव है?

उत्तर: हाँ, Aspose.Words for .NET के साथ नाम बदलने के बाद मर्ज किए गए फ़ील्ड के मूल नाम को पुनर्स्थापित करना संभव है। आप फ़ील्ड के मूल नाम को किसी वैरिएबल या सूची में संग्रहीत कर सकते हैं, और फिर ज़रूरत पड़ने पर मूल नाम को पुनर्स्थापित करने के लिए उस जानकारी का उपयोग कर सकते हैं।