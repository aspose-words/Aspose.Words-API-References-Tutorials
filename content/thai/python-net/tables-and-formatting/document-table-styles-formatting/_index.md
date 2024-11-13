---
title: สไตล์และการจัดรูปแบบตารางเอกสารโดยใช้ Aspose.Words Python
linktitle: สไตล์และการจัดรูปแบบตารางเอกสาร
second_title: API การจัดการเอกสาร Aspose.Words Python
description: เรียนรู้วิธีการกำหนดรูปแบบและสไตล์ของตารางเอกสารโดยใช้ Aspose.Words สำหรับ Python สร้าง ปรับแต่ง และส่งออกตารางด้วยคำแนะนำทีละขั้นตอนและตัวอย่างโค้ด ปรับปรุงการนำเสนอเอกสารของคุณวันนี้!
type: docs
weight: 12
url: /th/python-net/tables-and-formatting/document-table-styles-formatting/
---

ตารางเอกสารมีบทบาทสำคัญในการนำเสนอข้อมูลในรูปแบบที่เป็นระเบียบและดึงดูดสายตา Aspose.Words for Python มอบชุดเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับตารางและปรับแต่งสไตล์และการจัดรูปแบบได้อย่างมีประสิทธิภาพ ในบทความนี้ เราจะสำรวจวิธีการจัดการและปรับปรุงตารางเอกสารโดยใช้ Aspose.Words for Python API มาเริ่มกันเลย!

## เริ่มต้นใช้งาน Aspose.Words สำหรับ Python

ก่อนที่เราจะเจาะลึกถึงรายละเอียดของรูปแบบและการจัดรูปแบบของตารางเอกสาร เรามาตรวจสอบกันก่อนว่าคุณได้ตั้งค่าเครื่องมือที่จำเป็นไว้แล้ว:

1. ติดตั้ง Aspose.Words สำหรับ Python: เริ่มต้นด้วยการติดตั้งไลบรารี Aspose.Words โดยใช้ pip ซึ่งสามารถทำได้โดยใช้คำสั่งต่อไปนี้:
   
    ```bash
    pip install aspose-words
    ```

2. นำเข้าไลบรารี: นำเข้าไลบรารี Aspose.Words ลงในสคริปต์ Python ของคุณโดยใช้คำสั่งนำเข้าต่อไปนี้:

    ```python
    import aspose.words
    ```

3. โหลดเอกสาร: โหลดเอกสารที่มีอยู่หรือสร้างเอกสารใหม่โดยใช้ Aspose.Words API

## การสร้างและการแทรกตารางลงในเอกสาร

หากต้องการสร้างและแทรกตารางในเอกสารโดยใช้ Aspose.Words สำหรับ Python ให้ทำตามขั้นตอนเหล่านี้:

1.  สร้างตาราง: ใช้`DocumentBuilder` คลาสเพื่อสร้างตารางใหม่และระบุจำนวนแถวและคอลัมน์

    ```python
    builder = aspose.words.DocumentBuilder(doc)
    table = builder.start_table()
    ```

2.  แทรกข้อมูล: เพิ่มข้อมูลลงในตารางโดยใช้ตัวสร้าง`insert_cell` และ`write` วิธีการ

    ```python
    builder.insert_cell()
    builder.write("Header 1")
    builder.insert_cell()
    builder.write("Header 2")
    builder.end_row()
    ```

3. ทำซ้ำแถว: เพิ่มแถวและเซลล์ตามต้องการ โดยทำตามรูปแบบที่คล้ายกัน

4.  แทรกตารางลงในเอกสาร: สุดท้ายแทรกตารางลงในเอกสารโดยใช้`end_table` วิธี.

    ```python
    builder.end_table()
    ```

## การใช้การจัดรูปแบบตารางพื้นฐาน

 การจัดรูปแบบตารางพื้นฐานสามารถทำได้โดยใช้วิธีการที่ให้มาโดย`Table` และ`Cell` คลาสต่างๆ นี่คือวิธีที่คุณสามารถปรับปรุงรูปลักษณ์ของตารางของคุณได้:

1. ตั้งค่าความกว้างของคอลัมน์: ปรับความกว้างของคอลัมน์เพื่อให้แน่ใจว่ามีการจัดตำแหน่งที่เหมาะสมและสวยงาม

    ```python
    for cell in table.first_row.cells:
        cell.cell_format.preferred_width = aspose.words.PreferredWidth.from_points(100)
    ```

2. การเติมช่องว่างในเซลล์: เพิ่มการเติมช่องว่างในเซลล์เพื่อให้มีระยะห่างที่ดีขึ้น

    ```python
    for row in table.rows:
        for cell in row.cells:
            cell.cell_format.set_paddings(10, 10, 10, 10)
    ```

3. ความสูงของแถว: ปรับแต่งความสูงของแถวตามความต้องการ

    ```python
    for row in table.rows:
        row.row_format.height_rule = aspose.words.HeightRule.AT_LEAST
        row.row_format.height = aspose.words.ConvertUtil.inch_to_points(1)
    ```

## การจัดรูปแบบตารางด้วย Aspose.Words

Aspose.Words สำหรับ Python มีตัวเลือกการออกแบบมากมายเพื่อทำให้ตารางของคุณดูน่าสนใจ:

1. สไตล์ตาราง: ใช้สไตล์ตารางที่กำหนดไว้ล่วงหน้าเพื่อให้ได้รูปลักษณ์ที่เป็นมืออาชีพ

    ```python
    table.style = aspose.words.StyleIdentifier.LIGHT_LIST_ACCENT_5
    ```

2. สีพื้นหลังเซลล์: เปลี่ยนสีพื้นหลังเซลล์เพื่อเน้นข้อมูลเฉพาะ

    ```python
    cell.cell_format.shading.background_pattern_color = aspose.words.Color.from_rgb(240, 240, 240)
    ```

3. การจัดรูปแบบแบบอักษร: ปรับแต่งรูปแบบ ขนาดและสีของแบบอักษรเพื่อให้สามารถอ่านได้ดีขึ้น

    ```python
    run = cell.paragraphs[0].runs[0]
    run.font.size = aspose.words.Size(12, aspose.words.SizeUnit.POINTS)
    run.font.color = aspose.words.Color.from_rgb(0, 0, 0)
    ```

## การผสานและแยกเซลล์สำหรับเค้าโครงที่ซับซ้อน

การสร้างเค้าโครงตารางที่ซับซ้อนมักต้องรวมและแยกเซลล์:

1. รวมเซลล์: รวมเซลล์หลายเซลล์เพื่อสร้างเซลล์เดียวที่ใหญ่กว่า

    ```python
    table.rows[0].cells[0].cell_format.horizontal_merge = aspose.words.CellMerge.FIRST
    table.rows[0].cells[1].cell_format.horizontal_merge = aspose.words.CellMerge.PREVIOUS
    ```

2. แยกเซลล์: แยกเซลล์กลับเป็นส่วนประกอบแต่ละส่วน

    ```python
    cell.cell_format.horizontal_merge = aspose.words.CellMerge.NONE
    ```

## การปรับความสูงและความกว้างของแถวและคอลัมน์

ปรับแต่งขนาดแถวและคอลัมน์ให้เหมาะสมเพื่อเค้าโครงตารางที่สมดุล:

1. ปรับความสูงของแถว: ปรับเปลี่ยนความสูงของแถวตามเนื้อหา

    ```python
    row.row_format.height_rule = aspose.words.HeightRule.AUTO
    ```

2. ปรับความกว้างคอลัมน์: ปรับความกว้างคอลัมน์โดยอัตโนมัติเพื่อให้พอดีกับเนื้อหา

    ```python
    table.auto_fit(auto_fit_behaviour=aspose.words.AutoFitBehaviour.AUTO_FIT_TO_CONTENTS)
    ```

## การเพิ่มขอบและการแรเงาให้กับตาราง

ปรับปรุงรูปลักษณ์ของตารางโดยการเพิ่มขอบและการแรเงา:

1. เส้นขอบ: ปรับแต่งเส้นขอบให้กับตารางและเซลล์

    ```python
    table.set_borders(0.5, aspose.words.LineStyle.SINGLE, aspose.words.Color.from_rgb(0, 0, 0))
    ```

2. การแรเงา: แรเงาลงบนเซลล์เพื่อให้เกิดเอฟเฟกต์ที่สวยงาม

    ```python
    cell.cell_format.shading.background_pattern_color = aspose.words.Color.from_rgb(230, 230, 230)
    ```

## การทำงานกับเนื้อหาและการจัดตำแหน่งเซลล์

จัดการเนื้อหาเซลล์และการจัดตำแหน่งอย่างมีประสิทธิภาพเพื่อให้สามารถอ่านได้ดีขึ้น:

1. เนื้อหาเซลล์: แทรกเนื้อหา เช่น ข้อความและรูปภาพ ลงในเซลล์

    ```python
    builder.insert_cell()
    builder.write("Hello, Aspose!")
    ```

2. การจัดตำแหน่งข้อความ: จัดตำแหน่งข้อความในเซลล์ตามต้องการ

    ```python
    cell.paragraphs[0].paragraph_format.alignment = aspose.words.ParagraphAlignment.CENTER
    ```

## การจัดการส่วนหัวและส่วนท้ายของตาราง

รวมส่วนหัวและส่วนท้ายไว้ในตารางของคุณเพื่อบริบทที่ดีขึ้น:

1. ส่วนหัวของตาราง: ตั้งค่าแถวแรกเป็นแถวส่วนหัว

    ```python
    table.rows[0].row_format.is_header = True
    ```

2. ส่วนท้ายของตาราง: สร้างแถวส่วนท้ายสำหรับข้อมูลเพิ่มเติม

    ```python
    footer_row = table.append_row()
    footer_row.cells[0].cell_format.horizontal_merge = aspose.words.CellMerge.NONE
    footer_row.cells[0].paragraphs[0].runs[0].text = "Total"
    ```
	
## การปรับเค้าโครงตารางโดยอัตโนมัติ

ตรวจสอบให้แน่ใจว่าเค้าโครงตารางของคุณปรับเปลี่ยนโดยอัตโนมัติตามเนื้อหา:

1. ปรับให้พอดีหน้าต่างโดยอัตโนมัติ: ให้ตารางพอดีกับความกว้างของหน้า

    ```python
    table.allow_auto_fit = True
    ```

2. ปรับขนาดเซลล์อัตโนมัติ: เปิดใช้งานการปรับขนาดเซลล์อัตโนมัติเพื่อรองรับเนื้อหา

    ```python
    table.auto_fit(auto_fit_behaviour=aspose.words.AutoFitBehaviour.AUTO_FIT_TO_WINDOW)
    ```

## การส่งออกตารางไปยังรูปแบบที่แตกต่างกัน

เมื่อตารางของคุณพร้อมแล้ว คุณสามารถส่งออกเป็นรูปแบบต่างๆ เช่น PDF หรือ DOCX:

1. บันทึกเป็น PDF: บันทึกเอกสารพร้อมตารางเป็นไฟล์ PDF

    ```python
    doc.save("table_document.pdf", aspose.words.SaveFormat.PDF)
    ```

2. บันทึกเป็น DOCX: บันทึกเอกสารเป็นไฟล์ DOCX

    ```python
    doc.save("table_document.docx", aspose.words.SaveFormat.DOCX)
    ```

## การแก้ไขปัญหาและเคล็ดลับสำหรับการจัดการตารางอย่างมีประสิทธิภาพ

- หากตารางปรากฏมีความผิดเพี้ยน ให้ตรวจสอบความกว้างของคอลัมน์หรือความสูงของแถวที่ไม่ถูกต้อง
- ทดสอบการเรนเดอร์ตารางในรูปแบบต่างๆ เพื่อให้แน่ใจว่ามีความสอดคล้องกัน
- สำหรับเค้าโครงที่ซับซ้อน ควรวางแผนการผสานและแยกเซลล์อย่างรอบคอบ

## บทสรุป

Aspose.Words for Python นำเสนอชุดเครื่องมือที่ครอบคลุมสำหรับการสร้าง การจัดรูปแบบ และการจัดรูปแบบตารางเอกสาร ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทความนี้ คุณจะสามารถจัดการตารางในเอกสารของคุณ ปรับแต่งรูปลักษณ์ของตาราง และส่งออกตารางเป็นรูปแบบต่างๆ ได้อย่างมีประสิทธิภาพ ใช้พลังของ Aspose.Words เพื่อปรับปรุงการนำเสนอเอกสารของคุณและให้ข้อมูลที่ชัดเจนและดึงดูดสายตาแก่ผู้อ่านของคุณ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Words สำหรับ Python ได้อย่างไร?

ในการติดตั้ง Aspose.Words สำหรับ Python ให้ใช้คำสั่งต่อไปนี้: 

```bash
pip install aspose-words
```

### ฉันสามารถนำรูปแบบที่กำหนดเองมาใช้กับตารางของฉันได้ไหม

ใช่ คุณสามารถนำรูปแบบที่กำหนดเองไปใช้กับตารางของคุณได้โดยการแก้ไขคุณสมบัติต่างๆ เช่น แบบอักษร สี และเส้นขอบ โดยใช้ Aspose.Words

### สามารถรวมเซลล์ในตารางได้หรือไม่?

 ใช่ คุณสามารถรวมเซลล์ในตารางได้โดยใช้`CellMerge` ทรัพย์สินที่ให้ไว้โดย Aspose.Words

### ฉันจะส่งออกตารางของฉันไปยังรูปแบบที่แตกต่างกันได้อย่างไร

 คุณสามารถส่งออกตารางของคุณไปยังรูปแบบต่างๆ เช่น PDF หรือ DOCX โดยใช้`save` วิธีการและระบุรูปแบบที่ต้องการ

### ฉันสามารถเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ Python ได้จากที่ใด

 สำหรับเอกสารและเอกสารอ้างอิงที่ครอบคลุม โปรดไปที่[เอกสารอ้างอิง API Aspose.Words สำหรับ Python](https://reference.aspose.com/words/python-net/).
