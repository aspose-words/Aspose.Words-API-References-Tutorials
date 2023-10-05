---
title: استخدام الرسوم البيانية في Aspose.Words لجافا
linktitle: استخدام الرسوم البيانية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية إنشاء المخططات وتخصيصها في Aspose.Words لـ Java. استكشف أنواع المخططات والتنسيقات وخصائص المحاور لتصور البيانات.
type: docs
weight: 12
url: /ar/java/document-conversion-and-export/using-charts/
---

## مقدمة لاستخدام الرسوم البيانية في Aspose.Words لجافا

في هذا البرنامج التعليمي، سوف نستكشف كيفية العمل مع المخططات باستخدام Aspose.Words for Java. ستتعلم كيفية إنشاء أنواع مختلفة من المخططات وتخصيص خصائص المحور وتنسيق تسميات البيانات والمزيد. دعونا الغوص في!

## إنشاء مخطط خطي

لإنشاء مخطط خطي، استخدم الكود التالي:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

// حذف السلسلة التي تم إنشاؤها افتراضيًا.
chart.getSeries().clear();

// إضافة سلسلة تحتوي على البيانات وتسميات البيانات.
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

// أو قم بربط كود التنسيق بخلية مصدر.
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## إنشاء أنواع أخرى من الرسوم البيانية

يمكنك إنشاء أنواع مختلفة من المخططات مثل العمود والمنطقة والفقاعة والمبعثر والمزيد باستخدام تقنيات مشابهة. فيما يلي مثال لإدراج مخطط عمودي بسيط:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// حذف السلسلة التي تم إنشاؤها افتراضيًا.
chart.getSeries().clear();

// إنشاء الفئات وإضافة البيانات.
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## تخصيص خصائص المحور

يمكنك تخصيص خصائص المحور، مثل تغيير نوع المحور، وتعيين علامات التجزئة، وتنسيق التسميات، والمزيد. فيما يلي مثال لتحديد خصائص المحور XY:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

// امسح السلسلة الافتراضية وأضف بياناتك.

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

// قم بتغيير المحور X ليكون فئة بدلاً من التاريخ.
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); //تقاس بوحدات العرض للمحور Y (المئات).
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

## تنسيق تسميات البيانات

يمكنك تنسيق تسميات البيانات بتنسيقات أرقام مختلفة. هنا مثال:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// امسح السلسلة الافتراضية وأضف بياناتك.

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## تخصيصات الرسم البياني الإضافية

يمكنك تخصيص مخططاتك بشكل أكبر عن طريق ضبط الحدود ووحدات الفاصل الزمني بين التسميات وإخفاء محاور المخطط والمزيد. استكشف مقتطفات التعليمات البرمجية المتوفرة لمعرفة المزيد حول هذه الخيارات.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية العمل مع المخططات باستخدام Aspose.Words لـ Java. لقد تعلمت كيفية إنشاء أنواع مختلفة من المخططات وتخصيص خصائص المحور وتنسيق تسميات البيانات والمزيد. يوفر Aspose.Words for Java أدوات قوية لإضافة تمثيلات مرئية للبيانات إلى مستنداتك، مما يعزز طريقة تقديم المعلومات.

## الأسئلة الشائعة

### كيف يمكنني إضافة سلسلة متعددة إلى الرسم البياني؟

 يمكنك إضافة سلاسل متعددة إلى المخطط باستخدام`chart.getSeries().add()` طريقة. تأكد من تحديد اسم السلسلة والفئات وقيم البيانات.

### كيف يمكنني تنسيق تسميات البيانات بتنسيقات أرقام مخصصة؟

يمكنك تنسيق تسميات البيانات عن طريق الوصول إلى`DataLabels` خصائص السلسلة وتعيين رمز التنسيق المطلوب باستخدام`getNumberFormat().setFormatCode()`.

### كيف يمكنني تخصيص خصائص المحور في المخطط؟

 يمكنك تخصيص خصائص المحور مثل النوع وعلامات التجزئة والتسميات والمزيد عن طريق الوصول إلى`ChartAxis` خصائص مثل`setCategoryType()`, `setCrosses()` ، و`setMajorTickMark()`.

### كيف يمكنني إنشاء أنواع أخرى من المخططات مثل المخططات المبعثرة أو المخططات المساحية؟

 يمكنك إنشاء أنواع مختلفة من المخططات عن طريق تحديد النوع المناسب`ChartType` عند إدراج الرسم البياني باستخدام`builder.insertChart(ChartType.TYPE, width, height)`.

### كيف يمكنني إخفاء محور المخطط؟

 يمكنك إخفاء محور المخطط عن طريق تعيين`setHidden(true)` خاصية المحور.