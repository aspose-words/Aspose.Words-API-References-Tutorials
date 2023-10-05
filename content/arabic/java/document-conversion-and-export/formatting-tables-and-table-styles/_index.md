---
title: تنسيق الجداول وأنماط الجدول في Aspose.Words لـ Java
linktitle: تنسيق الجداول وأنماط الجدول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية تنسيق الجداول وتطبيق أنماط الجدول في Aspose.Words for Java. استكشف الأدلة خطوة بخطوة مع التعليمات البرمجية المصدر لتنسيق الجدول بشكل فعال. قم بتحسين تخطيط المستند الخاص بك باستخدام Aspose.Words.
type: docs
weight: 17
url: /ar/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## مقدمة إلى تنسيق الجداول وأنماط الجدول في Aspose.Words لـ Java

تلعب الجداول دورًا حاسمًا في هيكلة وتنظيم المعلومات في المستندات. يوفر Aspose.Words for Java ميزات قوية لتنسيق الجداول وتطبيق أنماط الجدول لتحسين المظهر المرئي لمستنداتك. في هذا الدليل التفصيلي، سنستكشف الجوانب المختلفة لتنسيق الجداول وتطبيق أنماط الجدول باستخدام Aspose.Words for Java.

## المتطلبات الأساسية

قبل أن نتعمق في التفاصيل، تأكد من دمج مكتبة Aspose.Words for Java في مشروعك. يمكنك تحميله من موقع Aspose:[تحميل Aspose.Words لجافا](https://releases.aspose.com/words/java/).

## احصل على المسافة بين الجدول والنص المحيط

للبدء، دعونا نستكشف كيفية استرداد المسافة بين الجدول والنص المحيط به في المستند.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## تطبيق حدود المخطط التفصيلي على جدول

يمكنك محاذاة جدول إلى منتصف الصفحة، ومسح الحدود الموجودة، وتعيين حد مخطط تفصيلي مخصص باستخدام هذا الرمز:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## بناء جدول مع الحدود

يوضح مقتطف التعليمات البرمجية هذا كيفية إنشاء جدول وتعيين حدود لكل من الجدول وخلاياه:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## تعديل تنسيق الصف

تعرف على كيفية تعديل تنسيق صف معين داخل جدول:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## تطبيق تنسيق الصف

يوضح هذا المثال كيفية تطبيق التنسيق على صف كامل في جدول:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## تعيين حشوة الخلية

اكتشف كيفية تعيين المساحة المتروكة للخلايا الفردية في جدول:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## تعديل تنسيق الخلية

اكتشف كيفية تعديل تنسيق خلية معينة داخل جدول:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## تنسيق الجدول والخلية بحدود مختلفة

تعرف على كيفية تعيين حدود مختلفة للخلايا الفردية في جدول:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// تعيين حدود الجدول
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// ضبط تظليل الخلايا للخلايا الفردية
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// إضافة محتوى إلى الخلايا
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// مسح تنسيق الخلية للصف التالي
builder.getCellFormat().clearFormatting();
// قم بإنشاء حدود أكبر للخلية الأولى من هذا الصف
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## تعيين عنوان الجدول ووصفه

أضف عنوانًا ووصفًا إلى جدولك:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## الخطوة 10: السماح بتباعد الخلايا

السماح بتباعد الخلايا وتعيين قيمتها للجدول:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## الخطوة 11: قم ببناء جدول بأسلوب

إنشاء جدول بنمط محدد مسبقًا:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## الخطوة 12: قم بتوسيع التنسيق على الخلايا والصفوف من النمط

تعرف على كيفية توسيع أنماط الجدول لتطبيق التنسيق على الخلايا والصفوف:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## الخطوة 13: إنشاء نمط الجدول

قم بإنشاء نمط جدول مخصص بتنسيق محدد:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## الخطوة 14: تحديد التنسيق الشرطي

تطبيق التنسيق الشرطي على الصفوف في الجدول:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## الخطوة 15: ضبط تنسيق TableCell

تعيين تنسيق محدد للخلايا الفردية:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## الخطوة 16: تعيين تنسيق TableRow

تطبيق التنسيق على صفوف بأكملها في جدول:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## خاتمة

يمكّنك Aspose.Words for Java من تنسيق الجداول وتطبيق أنماط الجدول بدقة. بدءًا من تعديل تنسيق الخلايا الفردية وحتى إنشاء أنماط جدول مخصصة، لديك الأدوات اللازمة لجعل مستنداتك جذابة ومنظمة من الناحية المرئية.

## الأسئلة الشائعة

### كيف أقوم بتنزيل Aspose.Words لـ Java؟

 يمكنك تنزيل Aspose.Words for Java من موقع Aspose:[تحميل Aspose.Words لجافا](https://releases.aspose.com/words/java/).

### هل يمكنني تطبيق حدود مختلفة على الخلايا الفردية داخل الجدول؟

نعم، يمكنك تعيين حدود مختلفة للخلايا الفردية داخل جدول باستخدام Aspose.Words for Java، كما هو موضح في هذا الدليل.

### ما هو الغرض من تحديد عنوان الجدول ووصفه؟

يؤدي تعيين عنوان الجدول ووصفه إلى تحسين إمكانية الوصول إلى المستند وتنظيمه، مما يسهل على القراء والتقنيات المساعدة فهم المحتوى.

### كيف يمكنني تطبيق التنسيق الشرطي على صفوف معينة في الجدول؟

يمكنك تطبيق التنسيق الشرطي على صفوف معينة في جدول ما عن طريق تحديد أنماط جدول مخصصة باستخدام قواعد التنسيق الشرطي، كما هو موضح في هذا الدليل.

### أين يمكنني العثور على المزيد من الوثائق والموارد الخاصة بـ Aspose.Words for Java؟

 للحصول على وثائق شاملة وموارد إضافية، يرجى زيارة وثائق Aspose.Words for Java:[Aspose.Words لتوثيق جافا](https://reference.aspose.com/words/java/).