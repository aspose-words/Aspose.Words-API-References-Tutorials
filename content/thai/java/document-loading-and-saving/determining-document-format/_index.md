---
title: การกำหนดรูปแบบเอกสารใน Aspose.Words สำหรับ Java
linktitle: การกำหนดรูปแบบเอกสาร
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีตรวจจับรูปแบบเอกสารใน Java ด้วย Aspose.Words ระบุ DOC, DOCX และอื่นๆ จัดระเบียบไฟล์อย่างมีประสิทธิภาพ
type: docs
weight: 25
url: /th/java/document-loading-and-saving/determining-document-format/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการกำหนดรูปแบบเอกสารใน Aspose.Words สำหรับ Java

เมื่อทำงานกับการประมวลผลเอกสารใน Java การกำหนดรูปแบบของไฟล์ที่คุณกำลังติดต่อถือเป็นสิ่งสำคัญ Aspose.Words สำหรับ Java มีคุณสมบัติที่มีประสิทธิภาพสำหรับการระบุรูปแบบเอกสาร และเราจะแนะนำคุณตลอดกระบวนการ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- [Aspose.Words สำหรับ Java](https://releases.aspose.com/words/java/)
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรี

ขั้นแรก เราต้องตั้งค่าไดเร็กทอรีที่จำเป็นเพื่อจัดระเบียบไฟล์ของเราอย่างมีประสิทธิภาพ เราจะสร้างไดเร็กทอรีสำหรับเอกสารประเภทต่างๆ

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

// สร้างไดเร็กทอรีหากยังไม่มี
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

เราได้สร้างไดเร็กทอรีสำหรับประเภทเอกสารที่รองรับ ไม่รู้จัก เข้ารหัส และก่อนปี 97

## ขั้นตอนที่ 2: การตรวจจับรูปแบบเอกสาร

ตอนนี้ เรามาตรวจสอบรูปแบบของเอกสารในไดเร็กทอรีของเรากัน เราจะใช้ Aspose.Words สำหรับ Java เพื่อให้บรรลุเป้าหมายนี้

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    // แสดงประเภทเอกสาร
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        // เพิ่มเคสสำหรับรูปแบบเอกสารอื่นๆ ตามความจำเป็น
    }

    // จัดการเอกสารที่เข้ารหัส
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        // จัดการเอกสารประเภทอื่นๆ
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

ในข้อมูลโค้ดนี้ เราจะวนซ้ำไฟล์ ตรวจหารูปแบบ และจัดระเบียบลงในไดเร็กทอรีที่เกี่ยวข้อง

## กรอกซอร์สโค้ดให้สมบูรณ์เพื่อกำหนดรูปแบบเอกสารใน Aspose.Words สำหรับ Java

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        // สร้างไดเร็กทอรีหากยังไม่มี
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
            // แสดงประเภทเอกสาร
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

## บทสรุป

การกำหนดรูปแบบเอกสารใน Aspose.Words สำหรับ Java เป็นสิ่งจำเป็นสำหรับการประมวลผลเอกสารที่มีประสิทธิภาพ ด้วยขั้นตอนที่อธิบายไว้ในคู่มือนี้ คุณสามารถระบุประเภทเอกสารและจัดการตามนั้นในแอปพลิเคชัน Java ของคุณได้

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Words สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Words สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/words/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้

### รูปแบบเอกสารที่รองรับมีอะไรบ้าง?

Aspose.Words สำหรับ Java รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง DOC, DOCX, RTF, HTML และอื่นๆ คุณสามารถดูเอกสารประกอบเพื่อดูรายการทั้งหมดได้

### ฉันจะตรวจจับเอกสารที่เข้ารหัสโดยใช้ Aspose.Words สำหรับ Java ได้อย่างไร

 คุณสามารถใช้`FileFormatUtil.detectFileFormat()` วิธีการตรวจจับเอกสารที่เข้ารหัส ดังที่แสดงในคู่มือนี้

### มีข้อจำกัดใด ๆ เมื่อทำงานกับรูปแบบเอกสารรุ่นเก่าหรือไม่?

รูปแบบเอกสารรุ่นเก่า เช่น MS Word 6 หรือ Word 95 อาจมีข้อจำกัดในแง่ของคุณสมบัติและความเข้ากันได้กับแอปพลิเคชันสมัยใหม่ พิจารณาอัปเกรดหรือแปลงเอกสารเหล่านี้เมื่อจำเป็น

### ฉันสามารถทำให้การตรวจจับรูปแบบเอกสารในแอปพลิเคชัน Java ของฉันเป็นแบบอัตโนมัติได้หรือไม่

ใช่ คุณสามารถทำให้การตรวจจับรูปแบบเอกสารเป็นอัตโนมัติโดยการรวมโค้ดที่ให้ไว้ในแอปพลิเคชัน Java ของคุณ ซึ่งจะทำให้คุณสามารถประมวลผลเอกสารตามรูปแบบที่ตรวจพบได้