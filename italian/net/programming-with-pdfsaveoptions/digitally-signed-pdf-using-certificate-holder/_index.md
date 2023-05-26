---
title: Pdf firmato digitalmente utilizzando il titolare del certificato
linktitle: Pdf firmato digitalmente utilizzando il titolare del certificato
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come firmare digitalmente un PDF utilizzando un titolare di certificato con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

In questo tutorial, ti guideremo attraverso i passaggi per creare un PDF firmato digitalmente utilizzando un certificato con Aspose.Words per .NET. La firma digitale aggiunge un livello di sicurezza e integrità al documento PDF. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e aggiunta di contenuto

Inizia creando un'istanza della classe Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: aggiungere contenuto al documento

 Quindi usa il`DocumentBuilder` per aggiungere contenuto al documento. Ad esempio, per aggiungere un paragrafo contenente il testo "Test PDF firmato", utilizzare l'estensione`Writeln` metodo:

```csharp
builder.Writeln("Test Signed PDF.");
```

È possibile aggiungere altri elementi di contenuto secondo necessità.

## Passaggio 3: imposta le opzioni di salvataggio del PDF

Crea un'istanza della classe PdfSaveOptions e specifica i dettagli della firma digitale:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Assicurati di specificare il percorso corretto per il certificato e la password associata. Puoi anche personalizzare il motivo e la posizione della firma.

## Passaggio 4: salva il documento come PDF con firma digitale

 Usa il`Save` metodo per salvare il documento come PDF specificando le opzioni di salvataggio:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF con firma digitale.

Seguendo questi passaggi, puoi facilmente creare un PDF firmato digitalmente con un certificato utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Pdf con firma digitale utilizzando il titolare del certificato utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per Pdf firmato digitalmente utilizzando il titolare del certificato da un documento che utilizza Aspose.Words per .NET:

```csharp

            // Il percorso della directory dei documenti.
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
