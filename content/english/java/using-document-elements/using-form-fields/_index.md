---
title: Using Form Fields in Aspose.Words for Java
linktitle: Using Form Fields in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 14
url: /java/using-document-elements/using-form-fields/
---

## Complete Source Code
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        String[] items = { "One", "Two", "Three" };
        builder.insertComboBox("DropDown", items, 0);
    }
    @Test
    public void formFieldsWorkWithProperties() throws Exception
    {
        Document doc = new Document(getMyDir() + "Form fields.docx");
        FormField formField = doc.getRange().getFormFields().get(3);
        if (formField.getType() == FieldType.FIELD_FORM_TEXT_INPUT)
            formField.setResult("My name is " + formField.getName());
    }
    @Test
    public void formFieldsGetFormFieldsCollection() throws Exception
    {
        Document doc = new Document(getMyDir() + "Form fields.docx");
        FormFieldCollection formFields = doc.getRange().getFormFields();
    }
    @Test
    public void formFieldsGetByName() throws Exception
    {
        Document doc = new Document(getMyDir() + "Form fields.docx");
        FormFieldCollection documentFormFields = doc.getRange().getFormFields();
        FormField formField1 = documentFormFields.get(3);
        FormField formField2 = documentFormFields.get("Text2");
        formField1.getFont().setSize(20.0);
        formField2.getFont().setColor(Color.RED);
```
