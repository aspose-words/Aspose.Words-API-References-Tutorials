---
title: Pdf firmado digitalmente usando el titular del certificado
linktitle: Pdf firmado digitalmente usando el titular del certificado
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a firmar digitalmente un PDF con un titular de certificado con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

En este tutorial, lo guiaremos a través de los pasos para crear un PDF firmado digitalmente usando un certificado con Aspose.Words para .NET. La firma digital agrega una capa de seguridad e integridad al documento PDF. Siga los pasos a continuación:

## Paso 1: Crear el documento y agregar contenido

Comience creando una instancia de la clase Documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Agregar contenido al documento

 Luego usa el`DocumentBuilder` para agregar contenido al documento. Por ejemplo, para agregar un párrafo que contenga el texto "PDF firmado de prueba", use el`Writeln` método:

```csharp
builder.Writeln("Test Signed PDF.");
```

Puede agregar otros elementos de contenido según sea necesario.

## Paso 3: Configure las opciones de guardado de PDF

Cree una instancia de la clase PdfSaveOptions y especifique los detalles de la firma digital:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Asegúrese de especificar la ruta correcta a su certificado y la contraseña asociada. También puede personalizar el motivo y la ubicación de la firma.

## Paso 4: Guarde el documento como PDF firmado digitalmente

 Utilizar el`Save` para guardar el documento como PDF especificando las opciones de guardado:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF firmado digitalmente.

Siguiendo estos pasos, puede crear fácilmente un PDF firmado digitalmente con un certificado usando Aspose.Words para .NET.

### Código fuente de ejemplo para Pdf firmado digitalmente usando el titular del certificado usando Aspose.Words para .NET

Aquí está el código fuente completo del PDF firmado digitalmente usando el titular del certificado de un documento usando Aspose.Words para .NET:

```csharp

            // La ruta al directorio de documentos.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
