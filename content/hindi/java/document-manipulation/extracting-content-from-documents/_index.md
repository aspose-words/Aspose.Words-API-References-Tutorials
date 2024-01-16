---
title: जावा के लिए Aspose.Words में दस्तावेज़ों से सामग्री निकालना
linktitle: दस्तावेज़ों से सामग्री निकालना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों से आसानी से सामग्री निकालना सीखें। हमारी चरण-दर-चरण मार्गदर्शिका और कोड नमूने प्रक्रिया को सरल बनाते हैं।
type: docs
weight: 13
url: /hi/java/document-manipulation/extracting-content-from-documents/
---

## जावा के लिए Aspose.Words में दस्तावेज़ों से सामग्री निकालने का परिचय

दस्तावेज़ प्रसंस्करण की दुनिया में, दस्तावेज़ों से सामग्री निकालना एक सामान्य आवश्यकता है। चाहे आपको पाठ, तालिकाओं, छवियों या विशिष्ट दस्तावेज़ तत्वों को निकालने की आवश्यकता हो, जावा के लिए Aspose.Words इस कार्य को आसान बनाने के लिए शक्तिशाली उपकरण प्रदान करता है। इस व्यापक गाइड में, हम आपको जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों से सामग्री निकालने की प्रक्रिया के बारे में बताएंगे। 

## आवश्यक शर्तें

इससे पहले कि हम निष्कर्षण प्रक्रिया में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1.  जावा के लिए Aspose.Words: आपके पास जावा विकास परिवेश में Aspose.Words for Java स्थापित और सेटअप होना चाहिए। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/).

2. सामग्री निकालने के लिए एक दस्तावेज़: इस गाइड के लिए, हम "Extract content.docx" नामक एक नमूना दस्तावेज़ का उपयोग करेंगे। सुनिश्चित करें कि आपके पास निष्कर्षण के लिए एक समान दस्तावेज़ तैयार है।

## ब्लॉक-स्तरीय नोड्स के बीच सामग्री निकालना

```java
// ब्लॉक-स्तरीय नोड्स के बीच सामग्री निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getLastSection().getChild(NodeType.PARAGRAPH, 2, true);
Table endTable = (Table) doc.getLastSection().getChild(NodeType.TABLE, 0, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endTable, true);
Collections.reverse(extractedNodes);
while (extractedNodes.size() > 0) {
    endTable.getParentNode().insertAfter((Node) extractedNodes.get(0), endTable);
    extractedNodes.remove(0);
}
doc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBlockLevelNodes.docx");
```

## बुकमार्क के बीच सामग्री निकालना

```java
//बुकमार्क के बीच सामग्री निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Bookmark bookmark = doc.getRange().getBookmarks().get("Bookmark1");
BookmarkStart bookmarkStart = bookmark.getBookmarkStart();
BookmarkEnd bookmarkEnd = bookmark.getBookmarkEnd();
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.IncludingBookmark.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.WithoutBookmark.docx");
```

## टिप्पणी श्रेणियों के बीच सामग्री निकालना

```java
// टिप्पणी श्रेणियों के बीच सामग्री निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Extract content.docx");
CommentRangeStart commentStart = (CommentRangeStart) doc.getChild(NodeType.COMMENT_RANGE_START, 0, true);
CommentRangeEnd commentEnd = (CommentRangeEnd) doc.getChild(NodeType.COMMENT_RANGE_END, 0, true);
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.IncludingComment.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.WithoutComment.docx");
```

## अनुच्छेदों के बीच सामग्री निकालना

```java
// अनुच्छेदों के बीच सामग्री निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 6, true);
Paragraph endPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 10, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endPara, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphs.docx");
```

## अनुच्छेद शैलियों के बीच सामग्री निकालना

```java
// अनुच्छेद शैलियों के बीच सामग्री निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Extract content.docx");
ArrayList<Paragraph> parasStyleHeading1 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 1");
ArrayList<Paragraph> parasStyleHeading3 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 3");
Node startPara1 = parasStyleHeading1.get(0);
Node endPara1 = parasStyleHeading3.get(0);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara1, endPara1, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphStyles.docx");
```

## रन के बीच सामग्री निकालना

```java
// रन के बीच सामग्री निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph para = (Paragraph) doc.getChild(NodeType.PARAGRAPH, 7, true);
Run startRun = para.getRuns().get(1);
Run endRun = para.getRuns().get(4);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startRun, endRun, true);
Node node = (Node) extractedNodes.get(0);
System.out.println(node.toString(SaveFormat.TEXT));
```

## DocumentVisitor का उपयोग करके सामग्री निकालना

```java
// DocumentVisitor का उपयोग करके सामग्री निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Absolute position tab.docx");
MyDocToTxtWriter myConverter = new MyDocToTxtWriter();
doc.accept(myConverter);
System.out.println(myConverter.getText());
```

## फ़ील्ड का उपयोग करके सामग्री निकालना

```java
// फ़ील्ड का उपयोग करके सामग्री निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Extract content.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.moveToMergeField("Fullname", false, false);
FieldStart startField = (FieldStart) builder.getCurrentNode();
Paragraph endPara = (Paragraph) doc.getFirstSection().getChild(NodeType.PARAGRAPH, 5, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startField, endPara, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentUsingField.docx");
```

## सामग्री की तालिका निकालना

```java
// सामग्री तालिका निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Table of contents.docx");
for (Field field : doc.getRange().getFields()) {
    if (field.getType() == FieldType.FIELD_HYPERLINK) {
        FieldHyperlink hyperlink = (FieldHyperlink) field;
        if (hyperlink.getSubAddress() != null && hyperlink.getSubAddress().startsWith("_Toc")) {
            Paragraph tocItem = (Paragraph) field.getStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(tocItem.toString(SaveFormat.TEXT).trim());
            System.out.println("------------------");
            Bookmark bm = doc.getRange().getBookmarks().get(hyperlink.getSubAddress());
            Paragraph pointer = (Paragraph) bm.getBookmarkStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(pointer.toString(SaveFormat.TEXT));
        }
    }
}
```

## केवल पाठ निकालना

```java
// केवल पाठ निकालने के लिए जावा कोड नमूना
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertField("MERGEFIELD Field");
System.out.println("GetText() Result: " + doc.getText());
System.out.println("ToString() Result: " + doc.toString(SaveFormat.TEXT));
```

## शैलियों के आधार पर सामग्री निकालना

```java
// शैलियों के आधार पर सामग्री निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Styles.docx");
final String PARA_STYLE = "Heading 1";
final String RUN_STYLE = "Intense Emphasis";
ArrayList<Paragraph> paragraphs = paragraphsByStyleName(doc, PARA_STYLE);
System.out.println("Paragraphs with \"{paraStyle}\" styles ({paragraphs.Count}):");
for (Paragraph paragraph : paragraphs)
    System.out.println(paragraph.toString(SaveFormat.TEXT));
ArrayList<Run> runs = runsByStyleName(doc, RUN_STYLE);
System.out.println("\nRuns with \"{runStyle}\" styles ({runs.Count}):");
for (Run run : runs)
    System.out.println(run.getRange().getText());
}

public ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}

public ArrayList<Run> runsByStyleName(Document doc, String styleName) {
    ArrayList<Run> runsWithStyle = new ArrayList<Run>();
    NodeCollection runs = doc.getChildNodes(NodeType.RUN, true);
    for (Run run : (Iterable<Run>) runs) {
        if (run.getFont().getStyle().getName().equals(styleName))
            runsWithStyle.add(run);
    }
    return runsWithStyle;
}
```

## टेक्स्ट निकालना और प्रिंट करना

```java
// टेक्स्ट निकालने और प्रिंट करने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Contents of the table: ");
System.out.println(table.getRange().getText());
System.out.println("\nContents of the row: ");
System.out.println(table.getRows().get(1).getRange().getText());
System.out.println("\nContents of the cell: ");
System.out.println(table.getLastRow().getLastCell().getRange().getText());
```

## फ़ाइलों में छवियाँ निकालना

```java
// फ़ाइलों में छवियाँ निकालने के लिए जावा कोड नमूना
Document doc = new Document("Your Directory Path" + "Images.docx");
NodeCollection shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;
for (Shape shape : (Iterable<Shape>) shapes) {
    if (shape.hasImage()) {
        String imageFileName = MessageFormat.format("Image.ExportImages.{0}_{1}",
                imageIndex, FileFormatUtil.imageTypeToExtension(shape.getImageData().getImageType()));
        shape.getImageData().save("Your Directory Path" + imageFileName);
        imageIndex++;
    }
}
```

## निष्कर्ष

बधाई हो! आपने जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों से सामग्री निकालना सीख लिया है। इस गाइड में विभिन्न निष्कर्षण तकनीकों को शामिल किया गया है, जिसमें ब्लॉक-स्तरीय नोड्स, बुकमार्क, टिप्पणी रेंज, पैराग्राफ और बहुत कुछ के बीच की सामग्री शामिल है। अब आप अपने जावा अनुप्रयोगों में दस्तावेज़ सामग्री निष्कर्षण को कुशलतापूर्वक संभालने के लिए सुसज्जित हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं विशिष्ट दस्तावेज़ अनुभागों से सामग्री कैसे निकालूं?

विशिष्ट दस्तावेज़ अनुभागों से सामग्री निकालने के लिए, आप अनुभागों के शुरुआती और अंतिम बिंदुओं की पहचान कर सकते हैं और उनके बीच सामग्री निकालने के लिए जावा विधियों के लिए उपयुक्त Aspose.Words का उपयोग कर सकते हैं।

### क्या मैं पासवर्ड-सुरक्षित दस्तावेज़ों से सामग्री निकाल सकता हूँ?

हां, जावा के लिए Aspose.Words पासवर्ड-सुरक्षित दस्तावेज़ों से सामग्री निकालने की कार्यक्षमता प्रदान करता है। आप इसका उपयोग करके दस्तावेज़ खोलते समय पासवर्ड प्रदान कर सकते हैं`Document` क्लास कंस्ट्रक्टर.

### मैं सामग्री कैसे निकाल सकता हूँ और उसे विभिन्न स्वरूपों, जैसे सादा पाठ या HTML, में कैसे सहेज सकता हूँ?

 आप जावा के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ से सामग्री निकाल सकते हैं और उसे विभिन्न स्वरूपों में सहेज सकते हैं। सामग्री निकालने के बाद, आप इसका उपयोग कर सकते हैं`Document` इसे सादे पाठ, HTML, या अन्य प्रारूपों में सहेजने के लिए क्लास विधियाँ।

### क्या विशिष्ट दस्तावेज़ तत्वों, जैसे तालिकाओं या छवियों से सामग्री निकालने का कोई तरीका है?

हां, आप जावा के लिए Aspose.Words का उपयोग करके विशिष्ट दस्तावेज़ तत्वों, जैसे तालिकाओं या छवियों से सामग्री निकाल सकते हैं। उन तत्वों की पहचान करें जिन्हें आप निकालना चाहते हैं, और फिर उनकी सामग्री निकालने के लिए उचित तरीकों का उपयोग करें।

### मैं अपने जावा एप्लिकेशन में सामग्री निष्कर्षण प्रक्रिया को कैसे स्वचालित कर सकता हूं?

अपने जावा एप्लिकेशन में सामग्री निष्कर्षण प्रक्रिया को स्वचालित करने के लिए, आप इस गाइड में वर्णित तकनीकों के आधार पर कस्टम कोड बना सकते हैं। आप एकाधिक दस्तावेज़ों के माध्यम से पुनरावृति करने और आवश्यकतानुसार सामग्री निकालने के लिए तर्क भी लागू कर सकते हैं।