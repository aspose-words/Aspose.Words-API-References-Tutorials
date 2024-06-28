---
title: การพิมพ์เอกสารใน Aspose.Words สำหรับ Java
linktitle: การพิมพ์เอกสาร
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีพิมพ์เอกสารโดยใช้ Aspose.Words สำหรับ Java คำแนะนำทีละขั้นตอนสำหรับการพิมพ์ที่ราบรื่นในแอปพลิเคชัน Java ของคุณ
type: docs
weight: 10
url: /th/java/printing-documents/printing-documents/
---

หากคุณต้องการพิมพ์เอกสารโดยใช้ Aspose.Words สำหรับ Java คุณมาถูกที่แล้ว ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการพิมพ์เอกสารด้วย Aspose.Words สำหรับ Java โดยใช้ซอร์สโค้ดที่ให้มา

## การแนะนำ

การพิมพ์เอกสารถือเป็นงานทั่วไปในหลายแอปพลิเคชัน Aspose.Words สำหรับ Java มอบ API อันทรงพลังเพื่อทำงานกับเอกสาร Word รวมถึงความสามารถในการพิมพ์เอกสารเหล่านั้น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการพิมพ์เอกสาร Word ทีละขั้นตอน

## การตั้งค่าสภาพแวดล้อมของคุณ

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
- ดาวน์โหลดและเพิ่มไลบรารี Aspose.Words สำหรับ Java ลงในโปรเจ็กต์ของคุณ

## กำลังโหลดเอกสาร

 ในการเริ่มต้น คุณจะต้องโหลดเอกสาร Word ที่คุณต้องการพิมพ์ แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังเอกสารของคุณและ`"Your Output Directory"` ด้วยไดเร็กทอรีเอาต์พุตที่ต้องการ

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## การสร้างงานพิมพ์

ต่อไป เราจะสร้างงานพิมพ์เพื่อพิมพ์เอกสารที่โหลดของเรา ข้อมูลโค้ดด้านล่างนี้จะเริ่มต้นงานพิมพ์และตั้งค่าเครื่องพิมพ์ที่ต้องการ

```java
// สร้างงานพิมพ์เพื่อพิมพ์เอกสารของเราด้วย
PrinterJob pj = PrinterJob.getPrinterJob();
//เริ่มต้นชุดแอตทริบิวต์ด้วยจำนวนหน้าในเอกสาร
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// ส่งการตั้งค่าเครื่องพิมพ์พร้อมกับพารามิเตอร์อื่นๆ ไปยังเอกสารที่พิมพ์
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## การพิมพ์เอกสาร

ตอนนี้เราได้ตั้งค่างานพิมพ์แล้ว ก็ถึงเวลาพิมพ์เอกสาร ข้อมูลโค้ดต่อไปนี้เชื่อมโยงเอกสารกับงานพิมพ์และเริ่มกระบวนการพิมพ์

```java
// ส่งเอกสารที่จะพิมพ์โดยใช้ฟังก์ชันการพิมพ์
pj.setPrintable(awPrintDoc);
pj.print();
```
## กรอกซอร์สโค้ดให้สมบูรณ์
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// สร้างงานพิมพ์เพื่อพิมพ์เอกสารของเราด้วย
PrinterJob pj = PrinterJob.getPrinterJob();
//เริ่มต้นชุดแอตทริบิวต์ด้วยจำนวนหน้าในเอกสาร
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// ส่งการตั้งค่าเครื่องพิมพ์พร้อมกับพารามิเตอร์อื่นๆ ไปยังเอกสารที่พิมพ์
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// ส่งเอกสารที่จะพิมพ์โดยใช้ฟังก์ชันการพิมพ์
pj.setPrintable(awPrintDoc);
pj.print();
```
ซอร์สโค้ดของ MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <สรุป>
    ///ตัวสร้างของคลาส PrintDocument แบบกำหนดเอง
    // / </สรุป>
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
        // ดัชนีเริ่มต้นและสิ้นสุดของหน้าตามที่กำหนดไว้ในชุดแอ็ตทริบิวต์
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // คำนวณดัชนีหน้าที่จะแสดงผลต่อไป
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // หากดัชนีหน้ามากกว่าช่วงหน้าทั้งหมดก็ไม่มีอะไรเลย
        // มากขึ้นในการเรนเดอร์
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // คำนวณขนาดของตัวยึดรูปขนาดย่อแต่ละรายการเป็นจุด
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // คำนวณจำนวนหน้าแรกที่จะพิมพ์บนกระดาษแผ่นนี้
        int startPage = pagesOnCurrentSheet + fromPage;
        // เลือกหมายเลขหน้าสุดท้ายที่จะพิมพ์บนกระดาษแผ่นนี้
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //วนซ้ำหน้าที่เลือกจากหน้าปัจจุบันที่เก็บไว้เพื่อคำนวณ
        // หน้าสุดท้าย.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // คำนวณดัชนีคอลัมน์และแถว
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // กำหนดตำแหน่งภาพขนาดย่อในพิกัดโลก (จุดในกรณีนี้)
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // คำนวณตำแหน่งเริ่มต้นด้านซ้ายและด้านบน
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // เรนเดอร์หน้าเอกสารเป็นออบเจ็กต์กราฟิกโดยใช้พิกัดที่คำนวณได้
                // และขนาดตัวยึดตำแหน่งภาพขนาดย่อ
                // ค่าที่ส่งคืนที่เป็นประโยชน์คือมาตราส่วนในการแสดงผลเพจ
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // วาดเส้นขอบหน้า (รูปขนาดย่อของหน้าอาจเล็กกว่ารูปขนาดย่อได้
                // ขนาดตัวยึดตำแหน่ง)
                if (mPrintPageBorders) {
                    // ได้ขนาดหน้าจริง 100% เป็นจุด
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // วาดเส้นขอบรอบหน้าที่ปรับขนาดโดยใช้ตัวคูณขนาดที่ทราบ
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // วาดเส้นขอบรอบๆ พื้นที่ที่สำรองไว้สำหรับรูปขนาดย่อ
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // หากมีข้อผิดพลาดใดๆ เกิดขึ้นระหว่างการเรนเดอร์ ไม่ต้องทำอะไรเลย
                // การดำเนินการนี้จะวาดหน้าว่างหากมีข้อผิดพลาดใดๆ ในระหว่างการเรนเดอร์
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // กำหนดจำนวนคอลัมน์และแถวบนแผ่นงานสำหรับ
        //กระดาษแนวแนวนอน
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
        // สลับความกว้างและความสูงหากกระดาษอยู่ในแนวตั้ง
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## บทสรุป

ยินดีด้วย! คุณพิมพ์เอกสาร Word สำเร็จโดยใช้ Aspose.Words สำหรับ Java คำแนะนำทีละขั้นตอนนี้จะช่วยคุณรวมการพิมพ์เอกสารเข้ากับแอปพลิเคชัน Java ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถพิมพ์หน้าเฉพาะของเอกสารโดยใช้ Aspose.Words for Java ได้หรือไม่

 ได้ คุณสามารถระบุช่วงหน้าเมื่อพิมพ์เอกสารได้ ในตัวอย่างโค้ดเราใช้`attributes.add(new PageRanges(1, doc.getPageCount()))` เพื่อพิมพ์ทุกหน้า คุณสามารถปรับช่วงหน้าได้ตามต้องการ

### คำถามที่ 2: Aspose.Words สำหรับ Java เหมาะสำหรับการพิมพ์เป็นชุดหรือไม่

อย่างแน่นอน! Aspose.Words สำหรับ Java เหมาะอย่างยิ่งสำหรับงานพิมพ์เป็นชุด คุณสามารถวนซ้ำรายการเอกสารและพิมพ์ทีละรายการโดยใช้โค้ดที่คล้ายกัน

### คำถามที่ 3: ฉันจะจัดการกับข้อผิดพลาดหรือข้อยกเว้นในการพิมพ์ได้อย่างไร

คุณควรจัดการกับข้อยกเว้นที่อาจเกิดขึ้นระหว่างกระบวนการพิมพ์ ตรวจสอบเอกสารประกอบ Aspose.Words สำหรับ Java สำหรับข้อมูลเกี่ยวกับการจัดการข้อยกเว้น

### คำถามที่ 4: ฉันสามารถปรับแต่งการตั้งค่าการพิมพ์เพิ่มเติมได้หรือไม่

ได้ คุณสามารถปรับแต่งการตั้งค่าการพิมพ์ให้ตรงตามความต้องการเฉพาะของคุณได้ สำรวจเอกสารประกอบ Aspose.Words สำหรับ Java เพื่อเรียนรู้เพิ่มเติมเกี่ยวกับตัวเลือกการพิมพ์ที่มี

### คำถามที่ 5: ฉันจะรับความช่วยเหลือและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Words สำหรับ Java ได้ที่ไหน

 สำหรับการสนับสนุนและความช่วยเหลือเพิ่มเติม คุณสามารถไปที่[Aspose.Words สำหรับฟอรัม Java](https://forum.aspose.com/).

---

ตอนนี้คุณได้เรียนรู้วิธีพิมพ์เอกสารโดยใช้ Aspose.Words สำหรับ Java เรียบร้อยแล้ว คุณสามารถเริ่มใช้ฟังก์ชันนี้ในแอปพลิเคชัน Java ของคุณได้ ขอให้มีความสุขในการเขียนโค้ด!