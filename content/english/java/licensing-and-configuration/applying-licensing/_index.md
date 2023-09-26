---
title: Applying Licensing to Aspose.Words for Java
linktitle: Applying Licensing to Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 10
url: /java/licensing-and-configuration/applying-licensing/
---

## Complete Source Code
```java
        License license = new License();
        // This line attempts to set a license from several locations relative to the executable and Aspose.Words.dll.
        // You can also use the additional overload to load a license from a stream, this is useful,
        // for instance, when the license is stored as an embedded resource.
        try
        {
            license.setLicense("Aspose.Words.lic");
            System.out.println("License set successfully.");
        }
        catch (Exception e)
        {
            // We do not ship any license with this example,
            // visit the Aspose site to obtain either a temporary or permanent license. 
            System.out.println("\nThere was an error setting the license: " + e.getMessage());
        }
    }
    @Test
    public void applyLicenseFromStream() throws Exception
    {
        License license = new License();
        try
        {
            license.setLicense(new FileInputStream(new File("Aspose.Words.lic")));
            System.out.println("License set successfully.");
        }
        catch (Exception e)
        {
            // We do not ship any license with this example,
            // visit the Aspose site to obtain either a temporary or permanent license. 
            System.out.println("\nThere was an error setting the license: " + e.getMessage());
        }
    }
    @Test
    public void applyMeteredLicense() {
        try
        {
            Metered metered = new Metered();
            metered.setMeteredKey("*****", "*****");
            Document doc = new Document(getMyDir() + "Document.docx");
            System.out.println(doc.getPageCount());
        }
        catch (Exception e)
        {
            System.out.println("\nThere was an error setting the license: " + e.getMessage());
        }
```
