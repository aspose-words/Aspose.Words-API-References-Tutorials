---
title: تحديد تنسيق المستند في Aspose.Words لـ Java
linktitle: تحديد تنسيق الوثيقة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية اكتشاف تنسيقات المستندات في Java باستخدام Aspose.Words. تحديد DOC وDOCX والمزيد. تنظيم الملفات بكفاءة.
type: docs
weight: 25
url: /ar/java/document-loading-and-saving/determining-document-format/
---

## مقدمة لتحديد تنسيق المستند في Aspose.Words لـ Java

عند العمل مع معالجة المستندات في Java، من المهم تحديد تنسيق الملفات التي تتعامل معها. يوفر Aspose.Words for Java ميزات قوية لتحديد تنسيقات المستندات، وسنرشدك خلال العملية.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- [Aspose.Words لجافا](https://releases.aspose.com/words/java/)
- تم تثبيت Java Development Kit (JDK) على نظامك
- المعرفة الأساسية ببرمجة جافا

## الخطوة 1: إعداد الدليل

أولاً، نحتاج إلى إعداد الأدلة اللازمة لتنظيم ملفاتنا بشكل فعال. سنقوم بإنشاء أدلة لأنواع المستندات المختلفة.

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

// قم بإنشاء الدلائل إذا لم تكن موجودة بالفعل.
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

لقد أنشأنا أدلة لأنواع المستندات المدعومة وغير المعروفة والمشفرة وما قبل 97.

## الخطوة 2: الكشف عن تنسيق المستند

الآن، دعونا نكتشف تنسيق المستندات الموجودة في أدلةنا. سوف نستخدم Aspose.Words for Java لتحقيق ذلك.

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    // عرض نوع الوثيقة
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        // أضف حالات لتنسيقات المستندات الأخرى حسب الحاجة
    }

    // التعامل مع المستندات المشفرة
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        // التعامل مع أنواع المستندات الأخرى
        switch (info.getLoadFormat()) {
            case LoadFormat.DOC_PRE_WORD_60:
                FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                break;
            case LoadFormat.UNKNOWN:
                FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                break;
            default:
                FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                break;
        }
    }
}
```

في مقتطف التعليمات البرمجية هذا، نقوم بمراجعة الملفات والكشف عن تنسيقاتها وتنظيمها في الأدلة المعنية.

## أكمل كود المصدر لتحديد تنسيق المستند في Aspose.Words لـ Java

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        // قم بإنشاء الدلائل إذا لم تكن موجودة بالفعل.
        if (supportedDir.exists() == false)
            supportedDir.mkdir();
        if (unknownDir.exists() == false)
            unknownDir.mkdir();
        if (encryptedDir.exists() == false)
            encryptedDir.mkdir();
        if (pre97Dir.exists() == false)
            pre97Dir.mkdir();
        Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
                .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
                .map(File::getPath)
                .collect(Collectors.toSet());
        for (String fileName : listFiles) {
            String nameOnly = Paths.get(fileName).getFileName().toString();
            System.out.println(nameOnly);
            FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);
            // عرض نوع الوثيقة
            switch (info.getLoadFormat()) {
                case LoadFormat.DOC:
                    System.out.println("\tMicrosoft Word 97-2003 document.");
                    break;
                case LoadFormat.DOT:
                    System.out.println("\tMicrosoft Word 97-2003 template.");
                    break;
                case LoadFormat.DOCX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Document.");
                    break;
                case LoadFormat.DOCM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
                    break;
                case LoadFormat.DOTX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Template.");
                    break;
                case LoadFormat.DOTM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
                    break;
                case LoadFormat.FLAT_OPC:
                    System.out.println("\tFlat OPC document.");
                    break;
                case LoadFormat.RTF:
                    System.out.println("\tRTF format.");
                    break;
                case LoadFormat.WORD_ML:
                    System.out.println("\tMicrosoft Word 2003 WordprocessingML format.");
                    break;
                case LoadFormat.HTML:
                    System.out.println("\tHTML format.");
                    break;
                case LoadFormat.MHTML:
                    System.out.println("\tMHTML (Web archive) format.");
                    break;
                case LoadFormat.ODT:
                    System.out.println("\tOpenDocument Text.");
                    break;
                case LoadFormat.OTT:
                    System.out.println("\tOpenDocument Text Template.");
                    break;
                case LoadFormat.DOC_PRE_WORD_60:
                    System.out.println("\tMS Word 6 or Word 95 format.");
                    break;
                case LoadFormat.UNKNOWN:
                    System.out.println("\tUnknown format.");
                    break;
            }
            if (info.isEncrypted()) {
                System.out.println("\tAn encrypted document.");
                FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
            } else {
                switch (info.getLoadFormat()) {
                    case LoadFormat.DOC_PRE_WORD_60:
                        FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                        break;
                    case LoadFormat.UNKNOWN:
                        FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                        break;
                    default:
                        FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                        break;
                }
            }
        }

```

## خاتمة

يعد تحديد تنسيقات المستندات في Aspose.Words for Java أمرًا ضروريًا لمعالجة المستندات بكفاءة. باستخدام الخطوات الموضحة في هذا الدليل، يمكنك تحديد أنواع المستندات والتعامل معها وفقًا لذلك في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Words لـ Java؟

 يمكنك تنزيل Aspose.Words for Java من[هنا](https://releases.aspose.com/words/java/) واتبع تعليمات التثبيت المقدمة.

### ما هي تنسيقات المستندات المدعومة؟

يدعم Aspose.Words for Java تنسيقات المستندات المختلفة، بما في ذلك DOC وDOCX وRTF وHTML والمزيد. يمكنك الرجوع إلى الوثائق للحصول على قائمة كاملة.

### كيف يمكنني اكتشاف المستندات المشفرة باستخدام Aspose.Words لـ Java؟

 يمكنك استخدام`FileFormatUtil.detectFileFormat()` طريقة للكشف عن المستندات المشفرة، كما هو موضح في هذا الدليل.

### هل هناك أي قيود عند العمل مع تنسيقات المستندات القديمة؟

قد تحتوي تنسيقات المستندات القديمة، مثل MS Word 6 أو Word 95، على قيود من حيث الميزات والتوافق مع التطبيقات الحديثة. فكر في ترقية هذه المستندات أو تحويلها عند الضرورة.

### هل يمكنني أتمتة اكتشاف تنسيق المستند في تطبيق Java الخاص بي؟

نعم، يمكنك أتمتة الكشف عن تنسيق المستند عن طريق دمج الكود المقدم في تطبيق Java الخاص بك. يتيح لك هذا معالجة المستندات بناءً على تنسيقاتها المكتشفة.