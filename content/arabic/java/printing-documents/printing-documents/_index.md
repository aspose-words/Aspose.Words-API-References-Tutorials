---
title: طباعة المستندات في Aspose.Words لـ Java
linktitle: طباعة المستندات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية طباعة المستندات باستخدام Aspose.Words لـ Java. دليل خطوة بخطوة للطباعة السلسة في تطبيقات Java الخاصة بك.
type: docs
weight: 10
url: /ar/java/printing-documents/printing-documents/
---

إذا كنت تتطلع إلى طباعة المستندات باستخدام Aspose.Words for Java، فأنت في المكان الصحيح. في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال عملية طباعة المستندات باستخدام Aspose.Words for Java باستخدام كود المصدر المتوفر.

## مقدمة

تعد طباعة المستندات مهمة شائعة في العديد من التطبيقات. يوفر Aspose.Words for Java واجهة برمجة تطبيقات قوية للعمل مع مستندات Word، بما في ذلك القدرة على طباعتها. سنرشدك في هذا البرنامج التعليمي خلال عملية طباعة مستند Word خطوة بخطوة.

## إعداد بيئتك

قبل أن نتعمق في الكود، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت مجموعة أدوات تطوير Java (JDK).
- تم تنزيل Aspose.Words لمكتبة Java وإضافتها إلى مشروعك

## تحميل الوثيقة

 للبدء، ستحتاج إلى تحميل مستند Word الذي تريد طباعته. يستبدل`"Your Document Directory"` مع المسار إلى المستند الخاص بك و`"Your Output Directory"` مع دليل الإخراج المطلوب.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## إنشاء مهمة طباعة

بعد ذلك، سنقوم بإنشاء مهمة طباعة لطباعة المستند الذي تم تحميله. يقوم مقتطف الكود أدناه بتهيئة مهمة طباعة ويضبط إعدادات الطابعة المطلوبة.

```java
// قم بإنشاء مهمة طباعة لطباعة وثيقتنا بها.
PrinterJob pj = PrinterJob.getPrinterJob();
//قم بتهيئة مجموعة سمات بعدد الصفحات في المستند.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// قم بتمرير إعدادات الطابعة مع المعلمات الأخرى إلى مستند الطباعة.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## طباعة الوثيقة

الآن بعد أن قمنا بإعداد مهمة الطباعة، حان الوقت لطباعة المستند. يقوم مقتطف التعليمات البرمجية التالي بربط المستند بمهمة الطباعة ويبدأ عملية الطباعة.

```java
// قم بتمرير المستند المراد طباعته باستخدام مهمة الطباعة.
pj.setPrintable(awPrintDoc);
pj.print();
```
## كود المصدر الكامل
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// قم بإنشاء مهمة طباعة لطباعة وثيقتنا بها.
PrinterJob pj = PrinterJob.getPrinterJob();
//قم بتهيئة مجموعة سمات بعدد الصفحات في المستند.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// قم بتمرير إعدادات الطابعة مع المعلمات الأخرى إلى مستند الطباعة.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// قم بتمرير المستند المراد طباعته باستخدام مهمة الطباعة.
pj.setPrintable(awPrintDoc);
pj.print();
```
كود المصدر لـ MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <الملخص>
    /// مُنشئ فئة PrintDocument المخصصة.
    // / </ملخص>
    public MultipagePrintDocument(Document document, int pagesPerSheet, boolean printPageBorders,
                                  AttributeSet attributes) {
        if (document == null)
            throw new IllegalArgumentException("document");
        mDocument = document;
        mPagesPerSheet = pagesPerSheet;
        mPrintPageBorders = printPageBorders;
        mAttributeSet = attributes;
    }
    public int print(Graphics g, PageFormat pf, int page) {
        // مؤشرات بداية الصفحة ونهايتها كما هو محدد في مجموعة السمات.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // احسب فهرس الصفحة الذي سيتم عرضه بعد ذلك.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // إذا كان فهرس الصفحة أكبر من إجمالي نطاق الصفحات، فلا يوجد شيء
        // المزيد لتقديمه.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // احسب حجم كل عنصر نائب للصورة المصغرة بالنقاط.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // احسب رقم الصفحة الأولى التي سيتم طباعتها على هذه الورقة.
        int startPage = pagesOnCurrentSheet + fromPage;
        // حدد رقم الصفحة الأخيرة المراد طباعتها على هذه الورقة.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //قم بالمرور عبر الصفحات المحددة من الصفحة الحالية المخزنة لحسابها
        // آخر صفحة.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // حساب مؤشرات الأعمدة والصفوف.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // تحديد موقع الصورة المصغرة في إحداثيات العالم (النقاط في هذه الحالة).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // احسب مواضع البداية اليسرى والعليا.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // قم بعرض صفحة المستند على كائن الرسومات باستخدام الإحداثيات المحسوبة
                // وحجم العنصر النائب للصورة المصغرة.
                // قيمة الإرجاع المفيدة هي المقياس الذي تم عرض الصفحة به.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // ارسم حدود الصفحة (يمكن أن تكون الصورة المصغرة للصفحة أصغر من الصورة المصغرة
                // حجم العنصر النائب).
                if (mPrintPageBorders) {
                    // احصل على الحجم الحقيقي للصفحة بنسبة 100% بالنقاط.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // ارسم الحد حول الصفحة التي تم تغيير حجمها باستخدام عامل القياس المعروف.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // ارسم الحد حول العنصر النائب للصورة المصغرة.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // إذا كانت هناك أية أخطاء تحدث أثناء العرض، فلا تفعل شيئًا.
                // سيؤدي هذا إلى رسم صفحة فارغة في حالة وجود أي أخطاء أثناء العرض.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // حدد عدد الأعمدة والصفوف في الورقة للملف
        //ورقة موجهة نحو المناظر الطبيعية.
        switch (pagesPerSheet) {
            case 16:
                size = new Dimension(4, 4);
                break;
            case 9:
                size = new Dimension(3, 3);
                break;
            case 8:
                size = new Dimension(4, 2);
                break;
            case 6:
                size = new Dimension(3, 2);
                break;
            case 4:
                size = new Dimension(2, 2);
                break;
            case 2:
                size = new Dimension(2, 1);
                break;
            default:
                size = new Dimension(1, 1);
                break;
        }
        // قم بتبديل العرض والارتفاع إذا كانت الورقة في الاتجاه الرأسي.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## خاتمة

تهانينا! لقد نجحت في طباعة مستند Word باستخدام Aspose.Words لـ Java. من المفترض أن يساعدك هذا الدليل التفصيلي على دمج طباعة المستندات في تطبيقات Java الخاصة بك بسلاسة.

## الأسئلة الشائعة

### س1: هل يمكنني طباعة صفحات معينة من المستند باستخدام Aspose.Words for Java؟

 نعم، يمكنك تحديد نطاق الصفحات عند طباعة مستند. في مثال التعليمات البرمجية، استخدمنا`attributes.add(new PageRanges(1, doc.getPageCount()))` لطباعة كافة الصفحات. يمكنك ضبط نطاق الصفحات حسب الحاجة.

### س2: هل Aspose.Words for Java مناسب للطباعة المجمعة؟

قطعاً! يعد Aspose.Words for Java مناسبًا تمامًا لمهام الطباعة المجمعة. يمكنك تكرار قائمة المستندات وطباعتها واحدة تلو الأخرى باستخدام رمز مماثل.

### س3: كيف يمكنني معالجة أخطاء الطباعة أو الاستثناءات؟

يجب عليك التعامل مع أية استثناءات محتملة قد تحدث أثناء عملية الطباعة. راجع وثائق Aspose.Words for Java للحصول على معلومات حول التعامل مع الاستثناءات.

### س4: هل يمكنني تخصيص إعدادات الطباعة بشكل أكبر؟

نعم، يمكنك تخصيص إعدادات الطباعة لتلبية متطلباتك المحددة. استكشف وثائق Aspose.Words for Java لمعرفة المزيد حول خيارات الطباعة المتاحة.

### س5: أين يمكنني الحصول على مزيد من المساعدة والدعم لـ Aspose.Words لـ Java؟

 لمزيد من الدعم والمساعدة، يمكنك زيارة[Aspose.Words لمنتدى جافا](https://forum.aspose.com/).

---

الآن بعد أن تعلمت بنجاح كيفية طباعة المستندات باستخدام Aspose.Words for Java، يمكنك البدء في تنفيذ هذه الوظيفة في تطبيقات Java الخاصة بك. ترميز سعيد!