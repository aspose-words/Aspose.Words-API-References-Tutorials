---
title: استخدام كائنات OLE وعناصر تحكم ActiveX في Aspose.Words لـ Java
linktitle: استخدام كائنات OLE وعناصر تحكم ActiveX
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعلم كيفية استخدام كائنات OLE وعناصر تحكم ActiveX في Aspose.Words لـ Java. أنشئ مستندات تفاعلية بسهولة. ابدأ الآن!
type: docs
weight: 21
url: /ar/java/using-document-elements/using-ole-objects-and-activex/
---
في هذا البرنامج التعليمي، سنستكشف كيفية العمل مع كائنات OLE (ربط الكائنات وتضمينها) وعناصر تحكم ActiveX في Aspose.Words for Java. تعد كائنات OLE وعناصر تحكم ActiveX أدوات فعالة تسمح لك بتحسين مستنداتك عن طريق تضمين محتوى خارجي أو ربطه، مثل جداول البيانات أو ملفات الوسائط المتعددة أو عناصر التحكم التفاعلية. تابع معنا بينما نتعمق في أمثلة التعليمات البرمجية ونتعلم كيفية استخدام هذه الميزات بفعالية.

### المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Words for Java: تأكد من تثبيت مكتبة Aspose.Words في مشروع Java الخاص بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/java/).

2. بيئة تطوير Java: يجب أن يكون لديك بيئة تطوير Java عاملة معدة على نظامك.

### إدراج كائن OLE

لنبدأ بإدراج كائن OLE في مستند Word. سنقوم بإنشاء مستند Word بسيط ثم نقوم بإدراج كائن OLE يمثل صفحة ويب.

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com"، "htmlfile"، true، true، null)؛
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

في هذا الكود، نقوم بإنشاء مستند جديد وإدراج كائن OLE الذي يعرض موقع Aspose. يمكنك استبدال عنوان URL بالمحتوى المطلوب.

### إدراج كائن OLE باستخدام OlePackage

بعد ذلك، دعنا نستكشف كيفية إدراج كائن OLE باستخدام OlePackage. يسمح لك هذا بتضمين ملفات خارجية ككائنات OLE في مستندك.

```java
@Test
public void insertOleObjectWithOlePackage() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    byte[] bs = FileUtils.readFileToByteArray(new File("Your Directory Path" + "Zip file.zip"));
    try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
    {
        Shape shape = builder.insertOleObject(stream, "Package", true, null);
        OlePackage olePackage = shape.getOleFormat().getOlePackage();
        olePackage.setFileName("filename.zip");
        olePackage.setDisplayName("displayname.zip");
        doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
    }
}
```

في هذا المثال، قمنا بإدراج كائن OLE باستخدام OlePackage، مما يسمح لك بتضمين ملفات خارجية ككائنات مضمنة.

### إدراج كائن OLE كرمز

الآن، دعونا نرى كيفية إدراج كائن OLE كرمز. يكون هذا مفيدًا عندما تريد عرض رمز يمثل ملفًا مضمنًا.

```java
@Test
public void insertOleObjectAsIcon() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObjectAsIcon("Your Directory Path" + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico", "My embedded file");
    doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
}
```

في هذا الكود، نقوم بإدراج كائن OLE كرمز، مما يوفر تمثيلاً أكثر جاذبية للمحتوى المضمن.

### قراءة خصائص عنصر تحكم ActiveX

الآن، دعونا نحول تركيزنا إلى عناصر تحكم ActiveX. سوف نتعلم كيفية قراءة خصائص عناصر تحكم ActiveX داخل مستند Word.

```java
@Test
public void readActiveXControlProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "ActiveX controls.docx");
    String properties = "";
    for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
    {
        if (shape.getOleFormat() == null) break;
        OleControl oleControl = shape.getOleFormat().getOleControl();
        if (oleControl.isForms2OleControl())
        {
            Forms2OleControl checkBox = (Forms2OleControl) oleControl;
            properties = properties + "\nCaption: " + checkBox.getCaption();
            properties = properties + "\nValue: " + checkBox.getValue();
            properties = properties + "\nEnabled: " + checkBox.getEnabled();
            properties = properties + "\nType: " + checkBox.getType();
            if (checkBox.getChildNodes() != null)
            {
                properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
            }
            properties += "\n";
        }
    }
    properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
    System.out.println("\n" + properties);
}
```

في هذا الكود، نقوم بالتكرار عبر الأشكال الموجودة في مستند Word، وتحديد عناصر تحكم ActiveX، واسترداد خصائصها.

### خاتمة

تهانينا! لقد تعلمت كيفية العمل مع كائنات OLE وعناصر تحكم ActiveX في Aspose.Words for Java. تفتح هذه الميزات عالمًا من الإمكانيات لإنشاء مستندات ديناميكية وتفاعلية.

### الأسئلة الشائعة

### ما هو الغرض من كائنات OLE في مستند Word؟ 
   - تسمح لك كائنات OLE بتضمين محتوى خارجي أو ربطه، مثل الملفات أو صفحات الويب، داخل مستند Word.

### هل يمكنني تخصيص مظهر كائنات OLE في المستند الخاص بي؟ 
   - نعم، يمكنك تخصيص مظهر كائنات OLE، بما في ذلك إعدادات الأيقونات وأسماء الملفات.

### ما هي عناصر تحكم ActiveX، وكيف يمكنها تحسين المستندات الخاصة بي؟ 
   - تعد عناصر تحكم ActiveX عناصر تفاعلية يمكنها إضافة وظائف إلى مستندات Word، مثل عناصر التحكم في النماذج أو مشغلات الوسائط المتعددة.

### هل Aspose.Words for Java مناسب لأتمتة المستندات على مستوى المؤسسة؟ 
   - نعم، Aspose.Words for Java هي مكتبة قوية لأتمتة إنشاء المستندات ومعالجتها في تطبيقات Java.

### أين يمكنني الوصول إلى Aspose.Words لـ Java؟ 
   -  يمكنك تنزيل Aspose.Words for Java من[هنا](https://releases.aspose.com/words/java/).

ابدأ مع Aspose.Words for Java اليوم واطلق العنان للإمكانات الكاملة لأتمتة المستندات وتخصيصها!
