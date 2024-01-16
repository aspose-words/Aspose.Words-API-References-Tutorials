---
title: मर्ज फ़ील्ड का नाम बदलें
linktitle: मर्ज फ़ील्ड का नाम बदलें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: इस ट्यूटोरियल में, आप सीखेंगे कि .NET के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ में मर्ज फ़ील्ड का नाम कैसे बदला जाए।
type: docs
weight: 10
url: /hi/net/working-with-fields/rename-merge-fields/
---

नीचे C# स्रोत कोड को समझाने के लिए चरण-दर-चरण मार्गदर्शिका दी गई है जो .NET के लिए Aspose.Words के मर्ज फ़ील्ड नाम बदलने की सुविधा का उपयोग करती है। वांछित परिणाम प्राप्त करने के लिए प्रत्येक चरण का सावधानीपूर्वक पालन करें।

## चरण 1: दस्तावेज़ निर्देशिका सेटअप

दिए गए कोड में, आपको अपने दस्तावेज़ों की निर्देशिका निर्दिष्ट करनी होगी। अपने दस्तावेज़ निर्देशिका के लिए उचित पथ के साथ "आपकी दस्तावेज़ निर्देशिका" मान को बदलें।

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## चरण 2: दस्तावेज़ बनाना और मर्ज फ़ील्ड सम्मिलित करना

हम एक नया दस्तावेज़ बनाकर और उसका उपयोग करके शुरुआत करते हैं`DocumentBuilder` मर्ज फ़ील्ड सम्मिलित करने के लिए.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## चरण 3: मर्ज फ़ील्ड का नाम बदलना

हम दस्तावेज़ श्रेणी में प्रत्येक फ़ील्ड के माध्यम से लूप करते हैं, और यदि यह एक मर्ज फ़ील्ड है, तो हम "जोड़कर फ़ील्ड का नाम बदलते हैं_नाम बदला" प्रत्यय.

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

## चरण 4: दस्तावेज़ सहेजना

 अंत में, हम कॉल करते हैं`Save()` संशोधित दस्तावेज़ को सहेजने की विधि.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### .NET के लिए Aspose.Words के साथ मर्ज फ़ील्ड का नाम बदलने के लिए स्रोत कोड उदाहरण

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// दस्तावेज़ बनाएं और मर्ज फ़ील्ड डालें।
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

#### प्रश्न: मैं .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का नाम कैसे बदल सकता हूं?

 उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का नाम बदलने के लिए, आप दस्तावेज़ में फ़ील्ड के माध्यम से लूप कर सकते हैं`FieldMergingArgs` कक्षा और उपयोग करें`FieldMergingArgs.FieldName` फ़ील्ड का नाम बदलने की विधि.

#### प्रश्न: क्या .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में केवल कुछ मर्ज किए गए फ़ील्ड का नाम बदलना संभव है?

उ: हाँ, .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में केवल कुछ मर्ज किए गए फ़ील्ड का नाम बदलना संभव है। आप विशिष्ट मानदंडों, जैसे फ़ील्ड नाम या अन्य प्रासंगिक गुणों का उपयोग करके फ़िल्टर कर सकते हैं कि किन फ़ील्ड का नाम बदलना है। फिर आप इसका उपयोग करके संबंधित फ़ील्ड का नाम बदल सकते हैं`FieldMergingArgs.FieldName` तरीका।

#### प्रश्न: मैं कैसे जांच सकता हूं कि .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का सफलतापूर्वक नाम बदल दिया गया था?

 उ: यह जांचने के लिए कि क्या .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का सफलतापूर्वक नाम बदला गया था, आप इसका उपयोग कर सकते हैं`FieldMergedArgs` क्लास और एक्सेस करें`FieldMergedArgs.IsMerged` यह निर्धारित करने के लिए संपत्ति कि हिट के साथ फ़ील्ड का नाम बदला गया था या नहीं।

#### प्रश्न: .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का नाम बदलने के क्या परिणाम होंगे?

उ: जब आप .NET के लिए Aspose.Words के साथ किसी Word दस्तावेज़ में मर्ज किए गए फ़ील्ड का नाम बदलते हैं, तो यह दस्तावेज़ में फ़ील्ड का नाम बदल देता है, जो फ़ील्ड नाम पर निर्भर अन्य कार्यक्षमता या प्रक्रियाओं को प्रभावित कर सकता है। मर्ज किए गए फ़ील्ड का नाम बदलने से पहले इन संभावित परिणामों पर विचार करना सुनिश्चित करें।

#### प्रश्न: क्या .NET के लिए Aspose.Words के साथ नाम बदलने के बाद मर्ज किए गए फ़ील्ड का मूल नाम पुनर्स्थापित करना संभव है?

उ: हां, .NET के लिए Aspose.Words के साथ नाम बदलने के बाद मर्ज किए गए फ़ील्ड का मूल नाम पुनर्स्थापित करना संभव है। आप फ़ील्ड के मूल नाम को एक चर या सूची में संग्रहीत कर सकते हैं, और फिर यदि आवश्यक हो तो मूल नाम को पुनर्स्थापित करने के लिए उस जानकारी का उपयोग कर सकते हैं।