---
title: Aggiungi la firma digitale al PDF utilizzando il titolare del certificato
linktitle: Aggiungi la firma digitale al PDF utilizzando il titolare del certificato
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come aggiungere la firma digitale al PDF utilizzando il titolare del certificato con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

In questo tutorial, ti guideremo attraverso i passaggi per aggiungere la firma digitale al PDF utilizzando il titolare del certificato con Aspose.Words per .NET. La firma digitale aggiunge un livello di sicurezza e integrità al documento PDF. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e aggiunta di contenuto

Inizia creando un'istanza della classe Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: aggiungere contenuto al documento

 Quindi usa il`DocumentBuilder`per aggiungere contenuto al documento. Ad esempio, per aggiungere un paragrafo contenente il testo "Test PDF firmato", utilizzare l'estensione`Writeln` metodo:

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
## Conclusione

In questo tutorial, abbiamo esplorato i passaggi per aggiungere una firma digitale a un documento PDF utilizzando un certificato con Aspose.Words per .NET. La firma digitale aggiunge uno strato di sicurezza e integrità al documento, garantendone l'autenticità e rendendo possibile il rilevamento di eventuali modifiche successive. Seguendo i passaggi indicati, è possibile creare facilmente un PDF firmato digitalmente utilizzando un certificato con Aspose.Words per .NET.

### Domande frequenti

#### D: Cos'è una firma digitale e perché è importante in un documento PDF?
R: Una firma digitale è una tecnica di sicurezza che aiuta a garantire l'autenticità, l'integrità e il non ripudio di un documento elettronico, come un file PDF. Utilizza un certificato digitale per aggiungere un livello di sicurezza al documento, che aiuta a verificare l'identità dell'autore e rilevare eventuali successive modifiche al contenuto.

#### D: Come posso aggiungere una firma digitale a un documento PDF utilizzando un certificato con Aspose.Words per .NET?
R: Per aggiungere una firma digitale a un documento PDF utilizzando un certificato con Aspose.Words per .NET, attenersi alla seguente procedura:

 Crea un'istanza di`Document` classe per rappresentare il documento.

 Usa il`DocumentBuilder` class per aggiungere il contenuto desiderato al documento.

 Crea un'istanza di`PdfSaveOptions` class e specificare i dettagli della firma digitale utilizzando il file`PdfDigitalSignatureDetails` classe. Dovrai fornire il percorso del certificato (`CertificateHolder.Create`), la password associata e il motivo e la posizione della firma.

 Usa il`Save` metodo per salvare il documento in formato PDF specificando le opzioni di salvataggio.

#### D: Come posso ottenere un certificato per aggiungere una firma digitale a un documento PDF?
R: Per ottenere un certificato per aggiungere una firma digitale a un documento PDF, in genere è possibile contattare un'autorità di certificazione (CA) o un fornitore di servizi fiduciari. Queste entità rilasciano certificati digitali dopo aver verificato la tua identità e convalidato la tua richiesta. Dopo aver ottenuto un certificato, puoi utilizzarlo nella tua applicazione per aggiungere firme digitali ai documenti PDF.

#### D: È possibile personalizzare i dettagli della firma digitale, come motivo e posizione?
 R: Sì, puoi personalizzare i dettagli della firma digitale specificando il motivo e la posizione della firma. Nel codice di esempio fornito, è possibile modificare i valori di`reason` E`location` parametri durante la creazione del file`PdfDigitalSignatureDetails` oggetto. Assicurati di fornire le informazioni appropriate per ogni parametro per riflettere il motivo e la posizione della firma nel documento PDF.