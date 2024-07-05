---
title: วิธีการช่วยเหลือสำหรับการแยกเนื้อหาใน Aspose.Words สำหรับ Java
linktitle: วิธีการช่วยเหลือในการแยกเนื้อหา
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีแยกเนื้อหาจากเอกสาร Word อย่างมีประสิทธิภาพโดยใช้ Aspose.Words สำหรับ Java สำรวจวิธีการช่วยเหลือ การจัดรูปแบบที่กำหนดเอง และอื่นๆ ในคู่มือที่ครอบคลุมนี้
type: docs
weight: 14
url: /th/java/document-manipulation/helper-methods-for-extracting-content/
---

## ข้อมูลเบื้องต้นเกี่ยวกับวิธีการช่วยเหลือในการแยกเนื้อหาใน Aspose.Words สำหรับ Java

Aspose.Words สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร Word โดยทางโปรแกรมได้ งานทั่วไปอย่างหนึ่งเมื่อทำงานกับเอกสาร Word คือการดึงเนื้อหาออกมา ในบทความนี้ เราจะสำรวจวิธีการช่วยเหลือบางประการในการแยกเนื้อหาอย่างมีประสิทธิภาพโดยใช้ Aspose.Words สำหรับ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกตัวอย่างโค้ด ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่า Aspose.Words สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

## วิธีช่วยเหลือ 1: แยกย่อหน้าตามสไตล์

```java
public static ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    // สร้างอาร์เรย์เพื่อรวบรวมย่อหน้าของสไตล์ที่ระบุ
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);

    // ดูย่อหน้าทั้งหมดเพื่อค้นหาย่อหน้าที่มีสไตล์ที่ระบุ
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}
```

คุณสามารถใช้วิธีนี้เพื่อแยกย่อหน้าที่มีสไตล์เฉพาะในเอกสาร Word ของคุณได้ สิ่งนี้มีประโยชน์เมื่อคุณต้องการแยกเนื้อหาที่มีการจัดรูปแบบเฉพาะ เช่น ส่วนหัวหรือเครื่องหมายคำพูดแบบบล็อก

## วิธีช่วยเหลือ 2: แยกเนื้อหาตามโหนด

```java
public static ArrayList<Node> extractContentBetweenNodes(Node startNode, Node endNode, boolean isInclusive) {
    // ขั้นแรก ตรวจสอบว่าโหนดที่ส่งไปยังวิธีนี้นั้นถูกต้องสำหรับการใช้งาน
    verifyParameterNodes(startNode, endNode);
    
    // สร้างรายการเพื่อจัดเก็บโหนดที่แยกออกมา
    ArrayList<Node> nodes = new ArrayList<Node>();

    // หากเครื่องหมายตัวใดตัวหนึ่งเป็นส่วนหนึ่งของความคิดเห็น รวมถึงความคิดเห็นด้วย เราจำเป็นต้องย้ายตัวชี้
    // ส่งต่อไปยังโหนดความคิดเห็นที่พบหลังจากโหนด CommentRangeEnd
    if (endNode.getNodeType() == NodeType.COMMENT_RANGE_END && isInclusive) {
        Node node = findNextNode(NodeType.COMMENT, endNode.getNextSibling());
        if (node != null)
            endNode = node;
    }
    
    // เก็บบันทึกของโหนดดั้งเดิมที่ส่งผ่านไปยังวิธีนี้เพื่อแยกโหนดตัวทำเครื่องหมายหากจำเป็น
    Node originalStartNode = startNode;
    Node originalEndNode = endNode;

    //แยกเนื้อหาตามโหนดระดับบล็อก (ย่อหน้าและตาราง) สำรวจผ่านโหนดหลักเพื่อค้นหา
    // เราจะแยกเนื้อหาของโหนดแรกและโหนดสุดท้าย ขึ้นอยู่กับว่าโหนดตัวทำเครื่องหมายอยู่ในบรรทัดหรือไม่
    startNode = getAncestorInBody(startNode);
    endNode = getAncestorInBody(endNode);
    boolean isExtracting = true;
    boolean isStartingNode = true;
    // โหนดปัจจุบันที่เรากำลังแยกออกจากเอกสาร
    Node currNode = startNode;

    // เริ่มการแยกเนื้อหา ประมวลผลโหนดระดับบล็อกทั้งหมดและแยกโหนดแรกโดยเฉพาะ
    // และโหนดสุดท้ายเมื่อจำเป็น ดังนั้นการจัดรูปแบบย่อหน้าจึงยังคงอยู่
    // วิธีนี้ซับซ้อนกว่าเครื่องสกัดแบบปกติเล็กน้อยเนื่องจากเราจำเป็นต้องแยกตัวประกอบ
    // ในการแตกไฟล์โดยใช้โหนดแบบอินไลน์ ฟิลด์ บุ๊กมาร์ก ฯลฯ เพื่อให้มีประโยชน์
    while (isExtracting) {
        // โคลนโหนดปัจจุบันและโหนดย่อยเพื่อรับสำเนา
        Node cloneNode = currNode.deepClone(true);
        boolean isEndingNode = currNode.equals(endNode);
        if (isStartingNode || isEndingNode) {
            // เราจำเป็นต้องประมวลผลเครื่องหมายแต่ละตัวแยกกัน ดังนั้นส่งต่อไปยังวิธีแยกกันแทน
            // ควรประมวลผลจุดสิ้นสุดในตอนแรกเพื่อเก็บดัชนีโหนด
            if (isEndingNode) {
                // !isStartingNode: อย่าเพิ่มโหนดสองครั้งหากเครื่องหมายเป็นโหนดเดียวกัน
                processMarker(cloneNode, nodes, originalEndNode, currNode, isInclusive,
                        false, !isStartingNode, false);
                isExtracting = false;
            }
            //จำเป็นต้องแยกเงื่อนไขออกจากกัน เนื่องจากเครื่องหมายเริ่มต้นและสิ้นสุดระดับบล็อกอาจเป็นโหนดเดียวกัน
            if (isStartingNode) {
                processMarker(cloneNode, nodes, originalStartNode, currNode, isInclusive,
                        true, true, false);
                isStartingNode = false;
            }
        } else
            // โหนดไม่ใช่เครื่องหมายเริ่มต้นหรือสิ้นสุด เพียงเพิ่มสำเนาลงในรายการ
            nodes.add(cloneNode);

        // ย้ายไปยังโหนดถัดไปแล้วแตกออก หากโหนดถัดไปเป็นโมฆะ
        // เนื้อหาที่เหลือจะพบได้ในส่วนอื่น
        if (currNode.getNextSibling() == null && isExtracting) {
            // ย้ายไปยังส่วนถัดไป
            Section nextSection = (Section) currNode.getAncestor(NodeType.SECTION).getNextSibling();
            currNode = nextSection.getBody().getFirstChild();
        } else {
            // ย้ายไปยังโหนดถัดไปในร่างกาย
            currNode = currNode.getNextSibling();
        }
    }

    // เพื่อให้เข้ากันได้กับโหมดที่มีบุ๊กมาร์กแบบอินไลน์ ให้เพิ่มย่อหน้าถัดไป (ว่าง)
    if (isInclusive && originalEndNode == endNode && !originalEndNode.isComposite())
        includeNextParagraph(endNode, nodes);

    // กลับโหนดระหว่างเครื่องหมายโหนด
    return nodes;
}
```

วิธีการนี้ช่วยให้คุณสามารถแยกเนื้อหาระหว่างสองโหนดที่ระบุได้ ไม่ว่าจะเป็นย่อหน้า ตาราง หรือองค์ประกอบระดับบล็อกอื่นๆ โดยจะจัดการกับสถานการณ์ต่างๆ รวมถึงเครื่องหมายอินไลน์ ฟิลด์ และบุ๊กมาร์ก

## วิธีช่วยเหลือ 3: การสร้างเอกสารใหม่

```java
public static Document generateDocument(Document srcDoc, ArrayList<Node> nodes) throws Exception {
    Document dstDoc = new Document();
    
    // ลบย่อหน้าแรกออกจากเอกสารเปล่า
    dstDoc.getFirstSection().getBody().removeAllChildren();
    
    // นำเข้าแต่ละโหนดจากรายการไปยังเอกสารใหม่ คงรูปแบบเดิมของโหนดไว้
    NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
    for (Node node : nodes) {
        Node importNode = importer.importNode(node, true);
        dstDoc.getFirstSection().getBody().appendChild(importNode);
    }
    
    return dstDoc;
}
```

วิธีการนี้ช่วยให้คุณสร้างเอกสารใหม่ได้โดยการนำเข้ารายการโหนดจากเอกสารต้นฉบับ โดยยังคงรูปแบบดั้งเดิมของโหนดไว้ ทำให้มีประโยชน์สำหรับการสร้างเอกสารใหม่ที่มีเนื้อหาเฉพาะ

## บทสรุป

การแยกเนื้อหาออกจากเอกสาร Word อาจเป็นส่วนสำคัญของงานประมวลผลเอกสารหลายอย่าง Aspose.Words สำหรับ Java มีวิธีการช่วยเหลือที่มีประสิทธิภาพซึ่งทำให้กระบวนการนี้ง่ายขึ้น ไม่ว่าคุณจะต้องแยกย่อหน้าตามสไตล์ เนื้อหาระหว่างโหนด หรือสร้างเอกสารใหม่ วิธีการเหล่านี้จะช่วยให้คุณทำงานกับเอกสาร Word ในแอปพลิเคชัน Java ของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Words สำหรับ Java ได้อย่างไร

 หากต้องการติดตั้ง Aspose.Words สำหรับ Java คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose เยี่ยม[ที่นี่](https://releases.aspose.com/words/java/) เพื่อรับเวอร์ชันล่าสุด

### ฉันสามารถแยกเนื้อหาจากส่วนเฉพาะของเอกสาร Word ได้หรือไม่

ได้ คุณสามารถแยกเนื้อหาจากส่วนเฉพาะของเอกสาร Word ได้โดยใช้วิธีการที่กล่าวถึงในบทความนี้ เพียงระบุโหนดเริ่มต้นและสิ้นสุดที่กำหนดส่วนที่คุณต้องการแยก

### Aspose.Words สำหรับ Java เข้ากันได้กับ Java 11 หรือไม่

ใช่ Aspose.Words สำหรับ Java เข้ากันได้กับ Java 11 และเวอร์ชันที่สูงกว่า คุณสามารถใช้มันในแอปพลิเคชัน Java ของคุณได้โดยไม่มีปัญหาใด ๆ

### ฉันสามารถปรับแต่งการจัดรูปแบบของเนื้อหาที่แยกออกมาได้หรือไม่

ใช่ คุณสามารถปรับแต่งการจัดรูปแบบของเนื้อหาที่แยกออกมาได้โดยการแก้ไขโหนดที่นำเข้าในเอกสารที่สร้างขึ้น Aspose.Words สำหรับ Java มีตัวเลือกการจัดรูปแบบที่หลากหลายเพื่อตอบสนองความต้องการของคุณ

### ฉันจะหาเอกสารและตัวอย่างเพิ่มเติมสำหรับ Aspose.Words สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมสำหรับ Aspose.Words สำหรับ Java บนเว็บไซต์ Aspose เยี่ยม[https://reference.aspose.com/words/java/](https://reference.aspose.com/words/java/) สำหรับเอกสารและทรัพยากรโดยละเอียด