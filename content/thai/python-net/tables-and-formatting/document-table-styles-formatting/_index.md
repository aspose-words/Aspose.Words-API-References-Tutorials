---
title: ลักษณะตารางเอกสารและการจัดรูปแบบโดยใช้ Aspose.Words Python
linktitle: ลักษณะตารางเอกสารและการจัดรูปแบบ
second_title: Aspose.Words API การจัดการเอกสาร Python
description: เรียนรู้วิธีจัดรูปแบบและจัดรูปแบบตารางเอกสารโดยใช้ Aspose.Words สำหรับ Python สร้าง ปรับแต่ง และส่งออกตารางพร้อมคำแนะนำทีละขั้นตอนและตัวอย่างโค้ด ปรับปรุงการนำเสนอเอกสารของคุณวันนี้!
type: docs
weight: 12
url: /th/python-net/tables-and-formatting/document-table-styles-formatting/
---

ตารางเอกสารมีบทบาทสำคัญในการนำเสนอข้อมูลในลักษณะที่เป็นระเบียบและดึงดูดสายตา Aspose.Words สำหรับ Python มีชุดเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาทำงานกับตารางได้อย่างมีประสิทธิภาพ รวมถึงปรับแต่งสไตล์และการจัดรูปแบบได้ ในบทความนี้ เราจะสำรวจวิธีจัดการและปรับปรุงตารางเอกสารโดยใช้ Aspose.Words สำหรับ Python API มาดำน้ำกันเถอะ!

## เริ่มต้นใช้งาน Aspose.Words สำหรับ Python

ก่อนที่เราจะเจาะลึกเกี่ยวกับลักษณะเฉพาะของตารางเอกสารและการจัดรูปแบบ เรามาตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าเครื่องมือที่จำเป็นแล้ว:

1. ติดตั้ง Aspose.Words สำหรับ Python: เริ่มต้นด้วยการติดตั้งไลบรารี Aspose.Words โดยใช้ pip ซึ่งสามารถทำได้ด้วยคำสั่งต่อไปนี้:
   
    ```bash
    pip install aspose-words
    ```

2. นำเข้าไลบรารี: นำเข้าไลบรารี Aspose.Words ลงในสคริปต์ Python ของคุณโดยใช้คำสั่งนำเข้าต่อไปนี้:

    ```python
    import aspose.words
    ```

3. โหลดเอกสาร: โหลดเอกสารที่มีอยู่หรือสร้างเอกสารใหม่โดยใช้ Aspose.Words API

## การสร้างและการแทรกตารางลงในเอกสาร

หากต้องการสร้างและแทรกตารางลงในเอกสารโดยใช้ Aspose.Words สำหรับ Python ให้ทำตามขั้นตอนเหล่านี้:

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

4.  แทรกตารางลงในเอกสาร: สุดท้าย แทรกตารางลงในเอกสารโดยใช้`end_table` วิธี.

    ```python
    builder.end_table()
    ```

## การใช้การจัดรูปแบบตารางพื้นฐาน

 การจัดรูปแบบตารางขั้นพื้นฐานสามารถทำได้โดยใช้วิธีการที่จัดทำโดย`Table` และ`Cell` ชั้นเรียน ต่อไปนี้คือวิธีที่คุณสามารถปรับปรุงรูปลักษณ์ของตารางของคุณได้:

1. ตั้งค่าความกว้างของคอลัมน์: ปรับความกว้างของคอลัมน์เพื่อให้แน่ใจว่ามีการจัดตำแหน่งที่เหมาะสมและดึงดูดสายตา

    ```python
    for cell in table.first_row.cells:
        cell.cell_format.preferred_width = aspose.words.PreferredWidth.from_points(100)
    ```

2. การเติมเซลล์: เพิ่มการเติมลงในเซลล์เพื่อปรับปรุงระยะห่าง

    ```python
    for row in table.rows:
        for cell in row.cells:
            cell.cell_format.set_paddings(10, 10, 10, 10)
    ```

3. ความสูงของแถว: ปรับแต่งความสูงของแถวตามต้องการ

    ```python
    for row in table.rows:
        row.row_format.height_rule = aspose.words.HeightRule.AT_LEAST
        row.row_format.height = aspose.words.ConvertUtil.inch_to_points(1)
    ```

## จัดสไตล์ตารางด้วย Aspose.Words

Aspose.Words สำหรับ Python มีตัวเลือกสไตล์มากมายเพื่อทำให้ตารางของคุณดูน่าดึงดูด:

1. สไตล์ตาราง: ใช้สไตล์ตารางที่กำหนดไว้ล่วงหน้าเพื่อให้ได้รูปลักษณ์ที่เป็นมืออาชีพ

    ```python
    table.style = aspose.words.StyleIdentifier.LIGHT_LIST_ACCENT_5
    ```

2. สีพื้นหลังของเซลล์: เปลี่ยนสีพื้นหลังของเซลล์เพื่อเน้นข้อมูลเฉพาะ

    ```python
    cell.cell_format.shading.background_pattern_color = aspose.words.Color.from_rgb(240, 240, 240)
    ```

3. การจัดรูปแบบแบบอักษร: ปรับแต่งลักษณะ ขนาด และสีแบบอักษรเพื่อให้อ่านง่ายขึ้น

    ```python
    run = cell.paragraphs[0].runs[0]
    run.font.size = aspose.words.Size(12, aspose.words.SizeUnit.POINTS)
    run.font.color = aspose.words.Color.from_rgb(0, 0, 0)
    ```

## การรวมและการแยกเซลล์สำหรับเลย์เอาต์ที่ซับซ้อน

การสร้างเค้าโครงตารางที่ซับซ้อนมักต้องมีการผสานและแยกเซลล์:

1. ผสานเซลล์: ผสานหลายเซลล์เพื่อสร้างเซลล์เดียวที่ใหญ่ขึ้น

    ```python
    table.rows[0].cells[0].cell_format.horizontal_merge = aspose.words.CellMerge.FIRST
    table.rows[0].cells[1].cell_format.horizontal_merge = aspose.words.CellMerge.PREVIOUS
    ```

2. แยกเซลล์: แยกเซลล์กลับเข้าไปในองค์ประกอบแต่ละส่วน

    ```python
    cell.cell_format.horizontal_merge = aspose.words.CellMerge.NONE
    ```

## การปรับความสูงและความกว้างของแถวและคอลัมน์

ปรับขนาดแถวและคอลัมน์อย่างละเอียดเพื่อเค้าโครงตารางที่สมดุล:

1. ปรับความสูงของแถว: แก้ไขความสูงของแถวตามเนื้อหา

    ```python
    row.row_format.height_rule = aspose.words.HeightRule.AUTO
    ```

2. ปรับความกว้างของคอลัมน์: ปรับความกว้างของคอลัมน์ให้พอดีกับเนื้อหาโดยอัตโนมัติ

    ```python
    table.auto_fit(auto_fit_behaviour=aspose.words.AutoFitBehaviour.AUTO_FIT_TO_CONTENTS)
    ```

## การเพิ่มเส้นขอบและการแรเงาให้กับตาราง

ปรับปรุงลักษณะที่ปรากฏของตารางโดยการเพิ่มเส้นขอบและการแรเงา:

1. เส้นขอบ: ปรับแต่งเส้นขอบสำหรับตารางและเซลล์

    ```python
    table.set_borders(0.5, aspose.words.LineStyle.SINGLE, aspose.words.Color.from_rgb(0, 0, 0))
    ```

2. การแรเงา: ใช้การแรเงากับเซลล์เพื่อให้ได้เอฟเฟกต์ที่ดึงดูดสายตา

    ```python
    cell.cell_format.shading.background_pattern_color = aspose.words.Color.from_rgb(230, 230, 230)
    ```

## การทำงานกับเนื้อหาของเซลล์และการจัดตำแหน่ง

จัดการเนื้อหาและการจัดแนวเซลล์อย่างมีประสิทธิภาพเพื่อให้อ่านง่ายขึ้น:

1. เนื้อหาเซลล์: แทรกเนื้อหา เช่น ข้อความและรูปภาพ ลงในเซลล์

    ```python
    builder.insert_cell()
    builder.write("Hello, Aspose!")
    ```

2. การจัดแนวข้อความ: จัดแนวข้อความเซลล์ตามต้องการ

    ```python
    cell.paragraphs[0].paragraph_format.alignment = aspose.words.ParagraphAlignment.CENTER
    ```

## การจัดการส่วนหัวและส่วนท้ายของตาราง

รวมส่วนหัวและส่วนท้ายลงในตารางของคุณเพื่อบริบทที่ดีขึ้น:

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

ตรวจสอบให้แน่ใจว่าเค้าโครงตารางของคุณปรับโดยอัตโนมัติตามเนื้อหา:

1. ปรับให้พอดีกับหน้าต่างอัตโนมัติ: อนุญาตให้ตารางพอดีกับความกว้างของหน้า

    ```python
    table.allow_auto_fit = True
    ```

2. ปรับขนาดเซลล์อัตโนมัติ: เปิดใช้งานการปรับขนาดเซลล์อัตโนมัติเพื่อรองรับเนื้อหา

    ```python
    table.auto_fit(auto_fit_behaviour=aspose.words.AutoFitBehaviour.AUTO_FIT_TO_WINDOW)
    ```

## การส่งออกตารางเป็นรูปแบบต่างๆ

เมื่อตารางของคุณพร้อมแล้ว คุณสามารถส่งออกเป็นรูปแบบต่างๆ ได้ เช่น PDF หรือ DOCX:

1. บันทึกเป็น PDF: บันทึกเอกสารพร้อมกับตารางเป็นไฟล์ PDF

    ```python
    doc.save("table_document.pdf", aspose.words.SaveFormat.PDF)
    ```

2. บันทึกเป็น DOCX: บันทึกเอกสารเป็นไฟล์ DOCX

    ```python
    doc.save("table_document.docx", aspose.words.SaveFormat.DOCX)
    ```

## การแก้ไขปัญหาและเคล็ดลับสำหรับการจัดการโต๊ะอย่างมีประสิทธิภาพ

- หากตารางบิดเบี้ยว ให้ตรวจสอบความกว้างของคอลัมน์หรือความสูงของแถวที่ไม่ถูกต้อง
- ทดสอบการเรนเดอร์ตารางในรูปแบบต่างๆ เพื่อให้มั่นใจถึงความสอดคล้อง
- สำหรับเลย์เอาต์ที่ซับซ้อน ให้วางแผนการรวมและแยกเซลล์อย่างระมัดระวัง

## บทสรุป

Aspose.Words สำหรับ Python มีชุดเครื่องมือที่ครอบคลุมสำหรับการสร้าง จัดสไตล์ และจัดรูปแบบตารางเอกสาร ด้วยการทำตามขั้นตอนที่อธิบายไว้ในบทความนี้ คุณสามารถจัดการตารางในเอกสารของคุณ ปรับแต่งลักษณะที่ปรากฏ และส่งออกเป็นรูปแบบต่างๆ ได้อย่างมีประสิทธิภาพ ควบคุมพลังของ Aspose.Words เพื่อปรับปรุงการนำเสนอเอกสารของคุณและให้ข้อมูลที่ชัดเจนและดึงดูดสายตาแก่ผู้อ่านของคุณ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Words สำหรับ Python ได้อย่างไร

หากต้องการติดตั้ง Aspose.Words สำหรับ Python ให้ใช้คำสั่งต่อไปนี้: 

```bash
pip install aspose-words
```

### ฉันสามารถใช้สไตล์ที่กำหนดเองกับตารางของฉันได้หรือไม่

ได้ คุณสามารถใช้สไตล์ที่กำหนดเองกับตารางของคุณได้โดยการปรับเปลี่ยนคุณสมบัติต่างๆ เช่น แบบอักษร สี และเส้นขอบโดยใช้ Aspose.Words

### เป็นไปได้ไหมที่จะรวมเซลล์ในตาราง?

 ใช่ คุณสามารถผสานเซลล์ในตารางได้โดยใช้`CellMerge` ทรัพย์สินที่จัดทำโดย Aspose.Words

### ฉันจะส่งออกตารางเป็นรูปแบบต่างๆ ได้อย่างไร

 คุณสามารถส่งออกตารางของคุณเป็นรูปแบบต่างๆ เช่น PDF หรือ DOCX ได้โดยใช้`save` วิธีการและระบุรูปแบบที่ต้องการ

### ฉันจะเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ Python ได้ที่ไหน

 สำหรับเอกสารและข้อมูลอ้างอิงที่ครอบคลุม โปรดไปที่[Aspose.Words สำหรับการอ้างอิง Python API](https://reference.aspose.com/words/python-net/).
