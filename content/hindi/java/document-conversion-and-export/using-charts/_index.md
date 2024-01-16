---
title: जावा के लिए Aspose.Words में चार्ट का उपयोग करना
linktitle: चार्ट का उपयोग करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words में चार्ट बनाना और अनुकूलित करना सीखें। डेटा विज़ुअलाइज़ेशन के लिए चार्ट प्रकार, फ़ॉर्मेटिंग और अक्ष गुणों का अन्वेषण करें।
type: docs
weight: 12
url: /hi/java/document-conversion-and-export/using-charts/
---

## जावा के लिए Aspose.Words में चार्ट का उपयोग करने का परिचय

इस ट्यूटोरियल में, हम देखेंगे कि जावा के लिए Aspose.Words का उपयोग करके चार्ट के साथ कैसे काम किया जाए। आप विभिन्न प्रकार के चार्ट बनाना, अक्ष गुणों को अनुकूलित करना, डेटा लेबल को प्रारूपित करना और बहुत कुछ सीखेंगे। आइए गोता लगाएँ!

## एक लाइन चार्ट बनाना

लाइन चार्ट बनाने के लिए, निम्नलिखित कोड का उपयोग करें:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

// डिफ़ॉल्ट जनरेट की गई श्रृंखला हटाएं.
chart.getSeries().clear();

// डेटा और डेटा लेबल के साथ एक श्रृंखला जोड़ना।
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

// या फॉर्मेट कोड को स्रोत सेल से लिंक करें।
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## अन्य प्रकार के चार्ट बनाना

आप समान तकनीकों का उपयोग करके विभिन्न प्रकार के चार्ट जैसे कॉलम, क्षेत्र, बबल, स्कैटर और बहुत कुछ बना सकते हैं। यहां एक साधारण कॉलम चार्ट सम्मिलित करने का एक उदाहरण दिया गया है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// डिफ़ॉल्ट जनरेट की गई श्रृंखला हटाएं.
chart.getSeries().clear();

// श्रेणियां बनाना और डेटा जोड़ना.
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## एक्सिस गुणों को अनुकूलित करना

आप अक्ष गुणों को अनुकूलित कर सकते हैं, जैसे अक्ष प्रकार बदलना, टिक चिह्न सेट करना, लेबल स्वरूपण करना, और बहुत कुछ। यहां XY अक्ष गुणों को परिभाषित करने का एक उदाहरण दिया गया है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

// डिफ़ॉल्ट श्रृंखला साफ़ करें और अपना डेटा जोड़ें।

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

// दिनांक के बजाय X अक्ष को एक श्रेणी के रूप में बदलें।
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); // अक्ष (सैकड़ों) की प्रदर्शन इकाइयों में मापा गया।
xAxis.setReverseOrder(true);
xAxis.setMajorTickMark(AxisTickMark.CROSS);
xAxis.setMinorTickMark(AxisTickMark.OUTSIDE);
xAxis.setTickLabelOffset(200);

yAxis.setTickLabelPosition(AxisTickLabelPosition.HIGH);
yAxis.setMajorUnit(100.0);
yAxis.setMinorUnit(50.0);
yAxis.getDisplayUnit().setUnit(AxisBuiltInUnit.HUNDREDS);
yAxis.getScaling().setMinimum(new AxisBound(100.0));
yAxis.getScaling().setMaximum(new AxisBound(700.0));

doc.save("Your Directory Path" + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## डेटा लेबल्स को फ़ॉर्मेट करना

आप विभिन्न संख्या प्रारूपों के साथ डेटा लेबल को प्रारूपित कर सकते हैं। यहाँ एक उदाहरण है:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// डिफ़ॉल्ट श्रृंखला साफ़ करें और अपना डेटा जोड़ें।

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## अतिरिक्त चार्ट अनुकूलन

आप सीमाओं को समायोजित करके, लेबल के बीच अंतराल इकाइयों, चार्ट अक्षों को छिपाकर और बहुत कुछ करके अपने चार्ट को और अधिक अनुकूलित कर सकते हैं। इन विकल्पों के बारे में अधिक जानने के लिए दिए गए कोड स्निपेट देखें।

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया है कि जावा के लिए Aspose.Words का उपयोग करके चार्ट के साथ कैसे काम किया जाए। आपने विभिन्न प्रकार के चार्ट बनाना, अक्ष गुणों को अनुकूलित करना, डेटा लेबल को प्रारूपित करना और बहुत कुछ सीख लिया है। जावा के लिए Aspose.Words आपके दस्तावेज़ों में डेटा के दृश्य प्रतिनिधित्व को जोड़ने, आपके जानकारी प्रस्तुत करने के तरीके को बेहतर बनाने के लिए शक्तिशाली उपकरण प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं एक चार्ट में अनेक शृंखलाएँ कैसे जोड़ सकता हूँ?

 आप इसका उपयोग करके चार्ट में एकाधिक श्रृंखलाएँ जोड़ सकते हैं`chart.getSeries().add()` तरीका। श्रृंखला का नाम, श्रेणियां और डेटा मान निर्दिष्ट करना सुनिश्चित करें।

### मैं कस्टम संख्या प्रारूपों के साथ डेटा लेबल कैसे प्रारूपित कर सकता हूं?

आप तक पहुंच कर डेटा लेबल को प्रारूपित कर सकते हैं`DataLabels` एक श्रृंखला के गुण और वांछित प्रारूप कोड का उपयोग करके सेट करना`getNumberFormat().setFormatCode()`.

### मैं चार्ट में अक्ष गुणों को कैसे अनुकूलित करूं?

 आप एक्सेस करके अक्ष गुणों जैसे प्रकार, टिक चिह्न, लेबल और बहुत कुछ को अनुकूलित कर सकते हैं`ChartAxis` गुण जैसे`setCategoryType()`, `setCrosses()` , और`setMajorTickMark()`.

### मैं स्कैटर या एरिया चार्ट जैसे अन्य प्रकार के चार्ट कैसे बना सकता हूं?

 आप उपयुक्त निर्दिष्ट करके विभिन्न चार्ट प्रकार बना सकते हैं`ChartType` का उपयोग करके चार्ट सम्मिलित करते समय`builder.insertChart(ChartType.TYPE, width, height)`.

### मैं चार्ट अक्ष को कैसे छुपा सकता हूँ?

 आप इसे सेट करके चार्ट अक्ष छिपा सकते हैं`setHidden(true)` अक्ष की संपत्ति.