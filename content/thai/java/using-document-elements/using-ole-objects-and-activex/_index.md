---
title: การใช้วัตถุ OLE และตัวควบคุม ActiveX ใน Aspose.Words สำหรับ Java
linktitle: การใช้วัตถุ OLE และตัวควบคุม ActiveX
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้การใช้วัตถุ OLE และตัวควบคุม ActiveX ใน Aspose.Words สำหรับ Java สร้างเอกสารเชิงโต้ตอบได้อย่างง่ายดาย เริ่มต้นทันที!
type: docs
weight: 21
url: /th/java/using-document-elements/using-ole-objects-and-activex/
---
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับออบเจ็กต์ OLE (การเชื่อมโยงและการฝังวัตถุ) และตัวควบคุม ActiveX ใน Aspose.Words สำหรับ Java วัตถุ OLE และตัวควบคุม ActiveX เป็นเครื่องมือที่มีประสิทธิภาพที่ช่วยให้คุณสามารถปรับปรุงเอกสารของคุณโดยการฝังหรือลิงก์เนื้อหาภายนอก เช่น สเปรดชีต ไฟล์มัลติมีเดีย หรือตัวควบคุมแบบโต้ตอบ ปฏิบัติตามในขณะที่เราเจาะลึกตัวอย่างโค้ดและเรียนรู้วิธีใช้คุณลักษณะเหล่านี้อย่างมีประสิทธิภาพ

### ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Words สำหรับ Java : ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Words ในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

2. สภาพแวดล้อมการพัฒนา Java : คุณควรตั้งค่าสภาพแวดล้อมการพัฒนา Java ที่ใช้งานได้บนระบบของคุณ

### การแทรกวัตถุ OLE

เริ่มต้นด้วยการแทรกวัตถุ OLE ลงในเอกสาร Word เราจะสร้างเอกสาร Word แบบธรรมดาแล้วแทรกวัตถุ OLE ที่เป็นตัวแทนของเว็บเพจ

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com", "htmlfile", จริง, จริง, null);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

ในโค้ดนี้ เราสร้างเอกสารใหม่และแทรกวัตถุ OLE ที่แสดงเว็บไซต์ Aspose คุณสามารถแทนที่ URL ด้วยเนื้อหาที่ต้องการได้

### การแทรกวัตถุ OLE ด้วย OlePackage

ต่อไป เรามาสำรวจวิธีการแทรกวัตถุ OLE โดยใช้ OlePackage ซึ่งจะทำให้คุณสามารถฝังไฟล์ภายนอกเป็นวัตถุ OLE ในเอกสารของคุณได้

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

ในตัวอย่างนี้ เราแทรกวัตถุ OLE โดยใช้ OlePackage ซึ่งช่วยให้คุณสามารถรวมไฟล์ภายนอกเป็นวัตถุฝังตัวได้

### การแทรกวัตถุ OLE เป็นไอคอน

ตอนนี้เรามาดูวิธีการแทรกวัตถุ OLE เป็นไอคอน สิ่งนี้มีประโยชน์เมื่อคุณต้องการแสดงไอคอนที่แสดงถึงไฟล์ที่ฝัง

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

ในโค้ดนี้ เราจะแทรกออบเจ็กต์ OLE เป็นไอคอน ซึ่งจะทำให้การแสดงเนื้อหาที่ฝังไว้ดูน่าดึงดูดยิ่งขึ้น

### การอ่านคุณสมบัติการควบคุม ActiveX

ตอนนี้ เรามาเปลี่ยนโฟกัสไปที่ตัวควบคุม ActiveX กันดีกว่า เราจะเรียนรู้วิธีการอ่านคุณสมบัติของตัวควบคุม ActiveX ภายในเอกสาร Word

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

ในโค้ดนี้ เราวนซ้ำรูปร่างในเอกสาร Word ระบุตัวควบคุม ActiveX และดึงคุณสมบัติเหล่านั้น

### บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีทำงานกับวัตถุ OLE และตัวควบคุม ActiveX ใน Aspose.Words สำหรับ Java คุณสมบัติเหล่านี้เปิดโลกแห่งความเป็นไปได้ในการสร้างเอกสารแบบไดนามิกและโต้ตอบได้

### คำถามที่พบบ่อย

### วัตถุประสงค์ของวัตถุ OLE ในเอกสาร Word คืออะไร? 
   - วัตถุ OLE ช่วยให้คุณสามารถฝังหรือลิงก์เนื้อหาภายนอก เช่น ไฟล์หรือเว็บเพจ ภายในเอกสาร Word ได้

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของวัตถุ OLE ในเอกสารของฉันได้หรือไม่ 
   - ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของวัตถุ OLE รวมถึงไอคอนการตั้งค่าและชื่อไฟล์ได้

### ตัวควบคุม ActiveX คืออะไร และจะปรับปรุงเอกสารของฉันได้อย่างไร 
   - ตัวควบคุม ActiveX เป็นองค์ประกอบแบบโต้ตอบที่สามารถเพิ่มฟังก์ชันการทำงานให้กับเอกสาร Word ของคุณ เช่น ตัวควบคุมฟอร์มหรือเครื่องเล่นมัลติมีเดีย

### Aspose.Words สำหรับ Java เหมาะสำหรับระบบอัตโนมัติของเอกสารระดับองค์กรหรือไม่ 
   - ใช่ Aspose.Words สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้างและจัดการเอกสารในแอปพลิเคชัน Java โดยอัตโนมัติ

### ฉันจะเข้าถึง Aspose.Words สำหรับ Java ได้ที่ไหน 
   -  คุณสามารถดาวน์โหลด Aspose.Words สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

เริ่มต้นใช้งาน Aspose.Words สำหรับ Java วันนี้และปลดล็อกศักยภาพเต็มรูปแบบของระบบอัตโนมัติและการปรับแต่งเอกสาร!
