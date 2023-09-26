---
title: Using XML Data in Aspose.Words for Java
linktitle: Using XML Data in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 12
url: /java/document-manipulation/using-xml-data/
---

## Complete Source Code
```java
        DataSet customersDs = new DataSet();
        customersDs.readXml(getMyDir() + "Mail merge data - Customers.xml");
        Document doc = new Document(getMyDir() + "Mail merge destinations - Registration complete.docx");
        doc.getMailMerge().execute(customersDs.getTables().get("Customer"));
        doc.save(getArtifactsDir() + "WorkingWithXmlData.XmlMailMerge.docx");
    }
    @Test
    public void nestedMailMerge() throws Exception
    {
        // The Datatable.TableNames and the DataSet.Relations are defined implicitly by .NET through ReadXml.
        DataSet pizzaDs = new DataSet();
        pizzaDs.readXml(getMyDir() + "Mail merge data - Orders.xml");
        Document doc = new Document(getMyDir() + "Mail merge destinations - Invoice.docx");
        // Trim trailing and leading whitespaces mail merge values.
        doc.getMailMerge().setTrimWhitespaces(false);
        doc.getMailMerge().executeWithRegions(pizzaDs);
        doc.save(getArtifactsDir() + "WorkingWithXmlData.NestedMailMerge.docx");
    }
    @Test
    public void mustacheSyntaxUsingDataSet() throws Exception
    {
        DataSet ds = new DataSet();
        ds.readXml(getMyDir() + "Mail merge data - Vendors.xml");
        Document doc = new Document(getMyDir() + "Mail merge destinations - Vendor.docx");
        doc.getMailMerge().setUseNonMergeFields(true);
        doc.getMailMerge().executeWithRegions(ds);
        doc.save(getArtifactsDir() + "WorkingWithXmlData.MustacheSyntaxUsingDataSet.docx");
```
