---
title: Encrypt Docx With Password
linktitle: Encrypt Docx With Password
second_title: Aspose.Words for .NET API Reference
description: Learn how to encrypt a DOCX file with a password using Aspose.Words for .NET. Complete tutorial for document security.
type: docs
weight: 10
url: /net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
In this tutorial, we will explore the provided C# source code to encrypt a DOCX file with a password using Aspose.Words for .NET. This feature allows you to protect your document by making it accessible only with a specified password.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Loading the document

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

In this step, we load the document using the `Document` method and passing the path to the DOCX file to load.

## Step 3: Configuring OOXML backup options

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

In this step, we configure OOXML save options by creating a new `OoxmlSaveOptions` object. We specify the desired password to encrypt the document by setting the `Password` property to your custom password.

## Step 4: Encrypting the document with password

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

In this last step, we save the document using the `Save` method and passing the path to the output file with the `.docx` extension, along with the specified save options.

Now you can run the source code to encrypt your DOCX document with a password. The resulting file will be saved in the specified directory with the name "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx". Be sure to keep your password safe, as it will be needed to open the encrypted document.

### Sample source code for Encrypt Docx With Password using Aspose.Words for .NET 

```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Conclusion

In this tutorial, we explored the functionality of encrypting a DOCX file with a password using Aspose.Words for .NET. We learned how to protect our documents by making them accessible only with a specified password.

Document encryption is an essential security measure to protect sensitive information. Thanks to Aspose.Words for .NET, we can easily add this functionality to our applications.

By following the steps provided, you can integrate password encryption into your Aspose.Words for .NET projects and ensure the confidentiality of your documents.

Feel free to experiment with other features offered by Aspose.Words for .NET to enrich your applications with advanced document manipulation features.

