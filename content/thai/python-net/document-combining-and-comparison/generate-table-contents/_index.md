---
title: การร่างสารบัญที่ครอบคลุมสำหรับเอกสาร Word
linktitle: การร่างสารบัญที่ครอบคลุมสำหรับเอกสาร Word
second_title: API การจัดการเอกสาร Aspose.Words Python
description: สร้างสารบัญที่อ่านง่ายด้วย Aspose.Words สำหรับ Python เรียนรู้วิธีสร้าง ปรับแต่ง และอัปเดตโครงสร้างเอกสารของคุณได้อย่างราบรื่น
type: docs
weight: 15
url: /th/python-net/document-combining-and-comparison/generate-table-contents/
---

## บทนำสู่สารบัญ

สารบัญจะแสดงภาพรวมของโครงสร้างเอกสาร ทำให้ผู้อ่านสามารถนำทางไปยังส่วนที่ต้องการได้อย่างง่ายดาย สารบัญมีประโยชน์อย่างยิ่งสำหรับเอกสารยาวๆ เช่น เอกสารวิจัย รายงาน หรือหนังสือ การสร้างสารบัญจะช่วยปรับปรุงประสบการณ์ของผู้ใช้และช่วยให้ผู้อ่านมีส่วนร่วมกับเนื้อหาของคุณได้อย่างมีประสิทธิภาพมากขึ้น

## การจัดเตรียมสภาพแวดล้อม

 ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words สำหรับ Python แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/python/)นอกจากนี้ ตรวจสอบให้แน่ใจว่าคุณมีเอกสาร Word ตัวอย่างที่คุณต้องการปรับปรุงด้วยสารบัญ

## การโหลดเอกสาร

```python
import asposewords

# Load the document
doc = asposewords.Document("your_document.docx")
```

## การกำหนดหัวเรื่องและหัวเรื่องย่อย

หากต้องการสร้างสารบัญ คุณต้องกำหนดหัวเรื่องและหัวเรื่องย่อยในเอกสารของคุณ ใช้รูปแบบย่อหน้าที่เหมาะสมเพื่อทำเครื่องหมายส่วนต่างๆ เหล่านี้ ตัวอย่างเช่น ใช้ "หัวเรื่อง 1" สำหรับหัวเรื่องหลักและ "หัวเรื่อง 2" สำหรับหัวเรื่องย่อย

```python
# Define headings and subheadings
for para in doc.get_child_nodes(asposewords.NodeType.PARAGRAPH, True):
    if para.paragraph_format.style_name == "Heading 1":
        # Add main heading
    elif para.paragraph_format.style_name == "Heading 2":
        # Add subheading
```

## การสร้างสารบัญ

ตอนนี้เราได้กำหนดหัวข้อและหัวข้อย่อยเรียบร้อยแล้ว เรามาสร้างสารบัญกันเลย เราจะสร้างส่วนใหม่ที่จุดเริ่มต้นของเอกสารและใส่เนื้อหาที่เหมาะสมลงไป

```python
# Create a new section for the table of contents
toc_section = doc.sections.insert_before(doc.sections[0])
toc_body = toc_section.body

# Add the title of the table of contents
toc_title = toc_body.append_paragraph("Table of Contents")
toc_title.paragraph_format.style_name = "Table of Contents Title"
```

## การปรับแต่งสารบัญ

คุณสามารถปรับแต่งลักษณะของสารบัญได้โดยการปรับเปลี่ยนแบบอักษร สไตล์ และการจัดรูปแบบ อย่าลืมใช้การจัดรูปแบบที่สม่ำเสมอตลอดทั้งเอกสารเพื่อให้ดูสวยงาม

```python
# Customize the appearance of the table of contents
for para in toc_body.get_child_nodes(asposewords.NodeType.PARAGRAPH, False):
    para.paragraph_format.style_name = "TOC Entries"
```

## การเพิ่มไฮเปอร์ลิงก์

หากต้องการให้สารบัญมีการโต้ตอบได้ ให้เพิ่มไฮเปอร์ลิงก์ที่ให้ผู้อ่านข้ามไปยังส่วนที่เกี่ยวข้องในเอกสารได้โดยตรง

```python
# Add hyperlinks to headings
for heading in headings:
    entry = toc_body.append_paragraph(heading.text)
    entry.paragraph_format.style_name = "TOC Entries"
    entry.hyperlink = "#" + heading.get_text().replace(" ", "_")
```

## การจัดรูปแบบสารบัญ

การจัดรูปแบบสารบัญเกี่ยวข้องกับการกำหนดรูปแบบย่อหน้าที่เหมาะสมสำหรับชื่อเรื่อง รายการ และองค์ประกอบอื่นๆ

```python
# Define styles for the table of contents
toc_title.style.name = "Table of Contents Title"
doc.styles.add_style("Table of Contents Title", asposewords.StyleType.PARAGRAPH)
```

## การอัปเดตสารบัญ

หากคุณทำการเปลี่ยนแปลงโครงสร้างเอกสาร คุณสามารถอัปเดตสารบัญเพื่อสะท้อนถึงการเปลี่ยนแปลงเหล่านั้นได้อย่างง่ายดาย

```python
# Update the table of contents
doc.update_fields()
```

## การทำให้กระบวนการเป็นอัตโนมัติ

เพื่อประหยัดเวลาและมั่นใจถึงความสม่ำเสมอ โปรดพิจารณาสร้างสคริปต์ที่สร้างและอัปเดตสารบัญสำหรับเอกสารของคุณโดยอัตโนมัติ

```python
# Automation script
def generate_table_of_contents(document_path):
    # Load the document
    doc = asposewords.Document(document_path)

    # ... (Rest of the code)

    # Update the table of contents
    doc.update_fields()
    doc.save(document_path)
```

## การจัดการหมายเลขหน้า

คุณสามารถเพิ่มหมายเลขหน้าลงในสารบัญเพื่อให้ผู้อ่านทราบบริบทเพิ่มเติมเกี่ยวกับตำแหน่งที่จะค้นหาส่วนต่างๆ เฉพาะเจาะจงได้

```python
# Add page numbers to table of contents
for entry in toc_body.get_child_nodes(asposewords.NodeType.PARAGRAPH, False):
    entry_text = entry.get_text()
    entry_page = doc.get_page_number(entry)
    entry_text += " - Page " + str(entry_page)
    entry.clear_contents()
    entry.append_text(entry_text)
```

## บทสรุป

การสร้างสารบัญที่ครอบคลุมโดยใช้ Aspose.Words สำหรับ Python สามารถปรับปรุงประสบการณ์การใช้งานเอกสารของคุณได้อย่างมาก ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถปรับปรุงการนำทางเอกสาร ให้การเข้าถึงส่วนสำคัญต่างๆ ได้อย่างรวดเร็ว และนำเสนอเนื้อหาของคุณในลักษณะที่เป็นระเบียบและเป็นมิตรต่อผู้อ่านมากขึ้น

## คำถามที่พบบ่อย

### ฉันจะกำหนดหัวข้อย่อยภายในสารบัญได้อย่างไร

ในการกำหนดหัวเรื่องย่อย ให้ใช้รูปแบบย่อหน้าที่เหมาะสมในเอกสารของคุณ เช่น "หัวเรื่อง 3" หรือ "หัวเรื่อง 4" สคริปต์จะรวมหัวเรื่องเหล่านี้ไว้ในสารบัญโดยอัตโนมัติตามลำดับชั้น

### ฉันสามารถเปลี่ยนขนาดตัวอักษรของรายการสารบัญได้หรือไม่

แน่นอน! ปรับแต่งรูปแบบ "รายการ TOC" โดยการปรับขนาดตัวอักษรและคุณลักษณะการจัดรูปแบบอื่น ๆ ให้ตรงกับสุนทรียภาพของเอกสารของคุณ

### เป็นไปได้ไหมที่จะสร้างสารบัญสำหรับเอกสารที่มีอยู่?

ใช่ คุณสามารถสร้างสารบัญสำหรับเอกสารที่มีอยู่ได้ เพียงโหลดเอกสารโดยใช้ Aspose.Words ปฏิบัติตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ และอัปเดตสารบัญตามต้องการ

### ฉันจะลบสารบัญออกจากเอกสารของฉันได้อย่างไร

หากคุณตัดสินใจที่จะลบสารบัญ เพียงลบส่วนที่มีสารบัญ อย่าลืมอัปเดตหมายเลขหน้าที่เหลือเพื่อสะท้อนถึงการเปลี่ยนแปลง