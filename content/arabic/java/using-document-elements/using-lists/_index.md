---
title: استخدام القوائم في Aspose.Words لـ Java
linktitle: استخدام القوائم
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعلم كيفية استخدام القوائم في Aspose.Words for Java من خلال هذا البرنامج التعليمي خطوة بخطوة. تنظيم وتنسيق المستندات الخاصة بك بشكل فعال.
type: docs
weight: 18
url: /ar/java/using-document-elements/using-lists/
---

في هذا البرنامج التعليمي الشامل، سنستكشف كيفية استخدام القوائم بشكل فعال في Aspose.Words for Java، وهي واجهة برمجة تطبيقات قوية للعمل مع مستندات Microsoft Word برمجيًا. تعتبر القوائم ضرورية لتنظيم وتنظيم المحتوى في مستنداتك. سنقوم بتغطية جانبين رئيسيين للعمل مع القوائم: إعادة تشغيل القوائم في كل قسم وتحديد مستويات القائمة. دعونا الغوص في!

## مقدمة إلى Aspose.Words لجافا

قبل أن نبدأ العمل مع القوائم، دعونا نتعرف على Aspose.Words for Java. توفر واجهة برمجة التطبيقات هذه للمطورين الأدوات اللازمة لإنشاء مستندات Word وتعديلها ومعالجتها في بيئة Java. إنه حل متعدد الاستخدامات للمهام التي تتراوح من إنشاء المستندات البسيطة إلى التنسيق المعقد وإدارة المحتوى.

### إعداد بيئتك

 للبدء، تأكد من تثبيت Aspose.Words for Java وإعداده في بيئة التطوير لديك. يمكنك تنزيله[هنا](https://releases.aspose.com/words/java/). 

## إعادة تشغيل القوائم في كل قسم

في العديد من السيناريوهات، قد تحتاج إلى إعادة تشغيل القوائم في كل قسم من المستند. يمكن أن يكون ذلك مفيدًا لإنشاء مستندات منظمة تحتوي على أقسام متعددة، مثل التقارير أو الأدلة أو الأبحاث الأكاديمية.

فيما يلي دليل خطوة بخطوة حول كيفية تحقيق ذلك باستخدام Aspose.Words لـ Java:

### تهيئة المستند الخاص بك: 
ابدأ بإنشاء كائن مستند جديد.

```java
Document doc = new Document();
```

### إضافة قائمة مرقمة: 
أضف قائمة مرقمة إلى المستند الخاص بك. سوف نستخدم نمط الترقيم الافتراضي.

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### تكوين إعدادات القائمة: 
\Enable القائمة لإعادة التشغيل عند كل قسم.

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### إعداد منشئ المستندات: 
قم بإنشاء DocumentBuilder لإضافة محتوى إلى مستندك.

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### إضافة عناصر القائمة: 
استخدم حلقة لإضافة عناصر القائمة إلى المستند الخاص بك. سنقوم بإدراج فاصل مقطعي بعد العنصر الخامس عشر.

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### احفظ المستند الخاص بك: 
احفظ المستند بالخيارات المطلوبة.

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

باتباع هذه الخطوات، يمكنك إنشاء مستندات تحتوي على قوائم يتم إعادة تشغيلها عند كل قسم، مع الحفاظ على بنية محتوى واضحة ومنظمة.

## تحديد مستويات القائمة

يتيح لك Aspose.Words for Java تحديد مستويات القائمة، وهو أمر مفيد بشكل خاص عندما تحتاج إلى تنسيقات قائمة مختلفة داخل المستند الخاص بك. دعنا نستكشف كيفية القيام بذلك:

### تهيئة المستند الخاص بك: 
قم بإنشاء كائن مستند جديد.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### إنشاء قائمة مرقمة: 
قم بتطبيق قالب قائمة مرقمة من Microsoft Word.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### تحديد مستويات القائمة: 
التكرار من خلال مستويات القائمة المختلفة وإضافة المحتوى.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### إنشاء قائمة ذات تعداد نقطي: 
الآن، دعونا ننشئ قائمة ذات تعداد نقطي.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### تحديد مستويات القائمة ذات التعداد النقطي: 
على غرار القائمة المرقمة، حدد المستويات وأضف المحتوى.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### تنسيق قائمة التوقف: 
لإيقاف تنسيق القائمة، قم بتعيين القائمة إلى قيمة خالية.

```java
builder.getListFormat().setList(null);
```

### احفظ المستند الخاص بك: 
احفظ المستند.

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

باتباع هذه الخطوات، يمكنك إنشاء مستندات ذات مستويات قائمة مخصصة، مما يسمح لك بالتحكم في تنسيق القوائم في مستنداتك.

## كود المصدر الكامل
```java
	string outPath = "Your Output Directory";
 public void restartListAtEachSection() throws Exception
    {
        Document doc = new Document();
        doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
        List list = doc.getLists().get(0);
        list.isRestartAtEachSection(true);
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().setList(list);
        for (int i = 1; i < 45; i++)
        {
            builder.writeln(MessageFormat.format("List Item {0}", i));
            if (i == 15)
                builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        }
        // سيتم كتابة IsRestartAtEachSection فقط إذا كان الامتثال أعلى من OoxmlComplianceCore.Ecma376.
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // قم بإنشاء قائمة مرقمة بناءً على أحد قوالب قوائم Microsoft Word
        //وتطبيقه على الفقرة الحالية لمنشئ المستندات.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        // هناك تسعة مستويات في هذه القائمة، دعونا نجربهم جميعا.
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // قم بإنشاء قائمة ذات تعداد نقطي استناداً إلى أحد قوالب قوائم Microsoft Word
        //وتطبيقه على الفقرة الحالية لمنشئ المستندات.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // هذه طريقة لإيقاف تنسيق القائمة.
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // قم بإنشاء قائمة بناءً على القالب.
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        // لإعادة استخدام القائمة الأولى، نحتاج إلى إعادة تشغيل الترقيم عن طريق إنشاء نسخة من تنسيق القائمة الأصلي.
        List list2 = doc.getLists().addCopy(list1);
        // يمكننا تعديل القائمة الجديدة بأي شكل من الأشكال، بما في ذلك تحديد رقم بداية جديد.
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## خاتمة

تهانينا! لقد تعلمت كيفية العمل مع القوائم في Aspose.Words for Java بفعالية. تعد القوائم ضرورية لتنظيم المحتوى وعرضه في مستنداتك. سواء كنت بحاجة إلى إعادة تشغيل القوائم في كل قسم أو تحديد مستويات القائمة، فإن Aspose.Words for Java يوفر الأدوات التي تحتاجها لإنشاء مستندات ذات مظهر احترافي.

يمكنك الآن استخدام هذه الميزات بثقة لتحسين مهام إنشاء المستندات وتنسيقها. إذا كانت لديك أي أسئلة أو كنت بحاجة إلى مزيد من المساعدة، فلا تتردد في التواصل مع[Aspose منتدى المجتمع](https://forum.aspose.com/) للدعم.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Words لـ Java؟
 يمكنك تنزيل Aspose.Words for Java من[هنا](https://releases.aspose.com/words/java/) واتبع تعليمات التثبيت في الوثائق.

### هل يمكنني تخصيص تنسيق ترقيم القوائم؟
نعم، يوفر Aspose.Words for Java خيارات شاملة لتخصيص تنسيقات ترقيم القائمة. يمكنك الرجوع إلى وثائق API للحصول على التفاصيل.

### هل Aspose.Words for Java متوافق مع أحدث معايير مستندات Word؟
نعم، يمكنك تكوين Aspose.Words لـ Java ليتوافق مع معايير مستندات Word المختلفة، بما في ذلك ISO 29500.

### هل يمكنني إنشاء مستندات معقدة تحتوي على جداول وصور باستخدام Aspose.Words for Java؟
قطعاً! يدعم Aspose.Words for Java التنسيق المتقدم للمستندات، بما في ذلك الجداول والصور والمزيد. تحقق من الوثائق للحصول على أمثلة.

### أين يمكنني الحصول على ترخيص مؤقت لـ Aspose.Words لـ Java؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
