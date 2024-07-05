---
title: การสร้างสารบัญที่ครอบคลุมสำหรับเอกสาร Word
linktitle: การสร้างสารบัญที่ครอบคลุมสำหรับเอกสาร Word
second_title: Aspose.Words API การจัดการเอกสาร Python
description: สร้างสารบัญที่เป็นมิตรกับผู้อ่านด้วย Aspose.Words สำหรับ Python เรียนรู้วิธีสร้าง ปรับแต่ง และอัปเดตโครงสร้างของเอกสารของคุณได้อย่างราบรื่น
type: docs
weight: 15
url: /th/python-net/document-combining-and-comparison/generate-table-contents/
---

## ความรู้เบื้องต้นเกี่ยวกับสารบัญ

สารบัญให้ภาพรวมของโครงสร้างของเอกสาร ช่วยให้ผู้อ่านไปยังส่วนที่ต้องการได้อย่างง่ายดาย มีประโยชน์อย่างยิ่งสำหรับเอกสารที่มีความยาว เช่น เอกสารวิจัย รายงาน หรือหนังสือ ด้วยการสร้างสารบัญ คุณจะปรับปรุงประสบการณ์ผู้ใช้และช่วยให้ผู้อ่านมีส่วนร่วมกับเนื้อหาของคุณได้อย่างมีประสิทธิภาพมากขึ้น

## การตั้งค่าสภาพแวดล้อม

 ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words สำหรับ Python แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/python/)- นอกจากนี้ ตรวจสอบให้แน่ใจว่าคุณมีเอกสาร Word ตัวอย่างที่คุณต้องการปรับปรุงด้วยสารบัญ

## กำลังโหลดเอกสาร

```python
import asposewords

# Load the document
doc = asposewords.Document("your_document.docx")
```

## การกำหนดหัวเรื่องและหัวเรื่องย่อย

ในการสร้างสารบัญ คุณต้องกำหนดหัวข้อและหัวข้อย่อยภายในเอกสารของคุณ ใช้ลักษณะย่อหน้าที่เหมาะสมเพื่อทำเครื่องหมายส่วนเหล่านี้ ตัวอย่างเช่น ใช้ "หัวเรื่อง 1" สำหรับหัวเรื่องหลัก และ "หัวเรื่อง 2" สำหรับหัวเรื่องย่อย

```python
# Define headings and subheadings
for para in doc.get_child_nodes(asposewords.NodeType.PARAGRAPH, True):
    if para.paragraph_format.style_name == "Heading 1":
        # Add main heading
    elif para.paragraph_format.style_name == "Heading 2":
        # Add subheading
```

## การสร้างสารบัญ

ตอนนี้เราได้กำหนดหัวข้อและหัวข้อย่อยแล้ว เรามาสร้างสารบัญกันดีกว่า เราจะสร้างส่วนใหม่ที่จุดเริ่มต้นของเอกสารและเติมด้วยเนื้อหาที่เหมาะสม

```python
# Create a new section for the table of contents
toc_section = doc.sections.insert_before(doc.sections[0])
toc_body = toc_section.body

# Add the title of the table of contents
toc_title = toc_body.append_paragraph("Table of Contents")
toc_title.paragraph_format.style_name = "Table of Contents Title"
```

## การปรับแต่งสารบัญ

คุณสามารถปรับแต่งลักษณะที่ปรากฏของสารบัญได้โดยการปรับแบบอักษร สไตล์ และการจัดรูปแบบ อย่าลืมใช้การจัดรูปแบบที่สอดคล้องกันทั่วทั้งเอกสารเพื่อให้ดูสวยงาม

```python
# Customize the appearance of the table of contents
for para in toc_body.get_child_nodes(asposewords.NodeType.PARAGRAPH, False):
    para.paragraph_format.style_name = "TOC Entries"
```

## การเพิ่มไฮเปอร์ลิงก์

หากต้องการทำให้สารบัญเป็นแบบโต้ตอบ ให้เพิ่มไฮเปอร์ลิงก์ที่ช่วยให้ผู้อ่านข้ามไปยังส่วนที่เกี่ยวข้องในเอกสารได้โดยตรง

```python
# Add hyperlinks to headings
for heading in headings:
    entry = toc_body.append_paragraph(heading.text)
    entry.paragraph_format.style_name = "TOC Entries"
    entry.hyperlink = "#" + heading.get_text().replace(" ", "_")
```

## จัดแต่งทรงผมสารบัญ

การกำหนดสไตล์สารบัญเกี่ยวข้องกับการกำหนดสไตล์ย่อหน้าที่เหมาะสมสำหรับชื่อเรื่อง รายการ และองค์ประกอบอื่นๆ

```python
# Define styles for the table of contents
toc_title.style.name = "Table of Contents Title"
doc.styles.add_style("Table of Contents Title", asposewords.StyleType.PARAGRAPH)
```

## การอัปเดตสารบัญ

หากคุณทำการเปลี่ยนแปลงโครงสร้างเอกสารของคุณ คุณสามารถอัปเดตสารบัญเพื่อแสดงการเปลี่ยนแปลงเหล่านั้นได้อย่างง่ายดาย

```python
# Update the table of contents
doc.update_fields()
```

## ทำให้กระบวนการเป็นอัตโนมัติ

เพื่อประหยัดเวลาและรับประกันความสอดคล้อง ให้พิจารณาสร้างสคริปต์ที่สร้างและอัปเดตสารบัญสำหรับเอกสารของคุณโดยอัตโนมัติ

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

คุณสามารถเพิ่มหมายเลขหน้าลงในสารบัญเพื่อให้ผู้อ่านทราบบริบทเพิ่มเติมเกี่ยวกับตำแหน่งที่จะค้นหาส่วนที่เฉพาะเจาะจงได้

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

การสร้างสารบัญที่ครอบคลุมโดยใช้ Aspose.Words สำหรับ Python สามารถปรับปรุงประสบการณ์ผู้ใช้เอกสารของคุณได้อย่างมาก ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถปรับปรุงการนำทางเอกสาร ให้การเข้าถึงส่วนสำคัญได้อย่างรวดเร็ว และนำเสนอเนื้อหาของคุณในลักษณะที่มีการจัดระเบียบและเป็นมิตรกับผู้อ่านมากขึ้น

## คำถามที่พบบ่อย

### ฉันจะกำหนดหัวข้อย่อยภายในสารบัญได้อย่างไร?

หากต้องการกำหนดหัวเรื่องย่อย ให้ใช้รูปแบบย่อหน้าที่เหมาะสมในเอกสารของคุณ เช่น "หัวเรื่อง 3" หรือ "หัวเรื่อง 4" สคริปต์จะรวมเนื้อหาเหล่านั้นไว้ในสารบัญโดยอัตโนมัติตามลำดับชั้น

### ฉันสามารถเปลี่ยนขนาดตัวอักษรของรายการสารบัญได้หรือไม่

อย่างแน่นอน! ปรับแต่งสไตล์ "รายการ TOC" โดยการปรับขนาดตัวอักษรและคุณลักษณะการจัดรูปแบบอื่นๆ เพื่อให้เข้ากับความสวยงามของเอกสารของคุณ

### เป็นไปได้ไหมที่จะสร้างสารบัญสำหรับเอกสารที่มีอยู่?

ใช่ คุณสามารถสร้างสารบัญสำหรับเอกสารที่มีอยู่ได้ เพียงโหลดเอกสารโดยใช้ Aspose.Words ทำตามขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ และอัปเดตสารบัญตามต้องการ

### ฉันจะลบสารบัญออกจากเอกสารของฉันได้อย่างไร

หากคุณตัดสินใจที่จะลบสารบัญ เพียงลบส่วนที่ประกอบด้วยสารบัญ อย่าลืมอัปเดตหมายเลขหน้าที่เหลือเพื่อให้สอดคล้องกับการเปลี่ยนแปลง