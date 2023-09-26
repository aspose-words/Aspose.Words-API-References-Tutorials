---
title: Using Textboxes in Aspose.Words for Java
linktitle: Using Textboxes in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 24
url: /java/using-document-elements/using-textboxes/
---

## Complete Source Code
```java
        Document doc = new Document();
        Shape shape1 = new Shape(doc, ShapeType.TEXT_BOX);
        Shape shape2 = new Shape(doc, ShapeType.TEXT_BOX);
        TextBox textBox1 = shape1.getTextBox();
        TextBox textBox2 = shape2.getTextBox();
        if (textBox1.isValidLinkTarget(textBox2))
            textBox1.setNext(textBox2);
    }
    @Test
    public void checkSequence() throws Exception
    {
        Document doc = new Document();
        Shape shape = new Shape(doc, ShapeType.TEXT_BOX);
        TextBox textBox = shape.getTextBox();
        if (textBox.getNext() != null && textBox.getPrevious() == null)
        {
            System.out.println("The head of the sequence");
        }
        if (textBox.getNext() != null && textBox.getPrevious() != null)
        {
            System.out.println("The Middle of the sequence.");
        }
        if (textBox.getNext() == null && textBox.getPrevious() != null)
        {
            System.out.println("The Tail of the sequence.");
        }
    }
    @Test
    public void breakALink() throws Exception
    {
        Document doc = new Document();
        Shape shape = new Shape(doc, ShapeType.TEXT_BOX);
        TextBox textBox = shape.getTextBox();
        // Break a forward link.
        textBox.breakForwardLink();
        // Break a forward link by setting a null.
        textBox.setNext(null);
        // Break a link, which leads to this textbox
        if (textBox.getPrevious() != null)
            textBox.getPrevious().breakForwardLink();
```
