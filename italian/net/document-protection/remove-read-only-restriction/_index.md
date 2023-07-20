---
title: Rimuovi la restrizione di sola lettura
linktitle: Rimuovi la restrizione di sola lettura
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come rimuovere la restrizione di sola lettura da un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-protection/remove-read-only-restriction/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare Aspose.Words per la funzionalità di rimozione delle restrizioni di sola lettura .NET. Questa funzione consente di rimuovere la restrizione di sola lettura da un documento di Word per renderlo modificabile. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e impostazione della protezione

Inizia creando un'istanza della classe Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Impostare una password per il documento utilizzando la proprietà SetPassword() dell'oggetto WriteProtection:

Assicurati di sostituire "MyPassword" con la password effettiva che hai utilizzato per proteggere il documento.

## Passaggio 2: rimuovere la restrizione di sola lettura

Per rimuovere la restrizione di sola lettura, imposta la proprietà ReadOnlyRecommended su false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Passaggio 3: applica la protezione illimitata

Infine, applica la protezione illimitata utilizzando il metodo Protect() dell'oggetto Document:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento senza la restrizione di sola lettura.

### Codice sorgente di esempio per rimuovere la restrizione di sola lettura utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per rimuovere la restrizione di sola lettura utilizzando Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Inserisci una password di massimo 15 caratteri.
doc.WriteProtection.SetPassword("MyPassword");

//Rimuovi l'opzione di sola lettura.
doc.WriteProtection.ReadOnlyRecommended = false;

// Applicare la protezione da scrittura senza alcuna protezione.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Seguendo questi passaggi, puoi rimuovere facilmente la restrizione di sola lettura da un documento di Word con Aspose.Words per .NET.


## Conclusione

In questo tutorial, abbiamo imparato come rimuovere la restrizione di sola lettura da un documento di Word utilizzando Aspose.Words per .NET. Seguendo i passaggi forniti, puoi rimuovere facilmente la restrizione e rendere nuovamente modificabile il documento. Aspose.Words per .NET offre un set completo di funzionalità per la gestione della protezione e delle restrizioni dei documenti, fornendo flessibilità e controllo sulla sicurezza e capacità di modifica dei documenti Word.

### FAQ

#### D: Qual è la restrizione di sola lettura in Aspose.Words per .NET?

R: La restrizione di sola lettura in Aspose.Words per .NET si riferisce a una funzionalità che consente di impostare un documento Word come di sola lettura, impedendo agli utenti di apportare modifiche al contenuto o alla formattazione. Questa restrizione aiuta a proteggere l'integrità del documento e garantisce che non venga modificato accidentalmente o intenzionalmente.

#### D: Come posso rimuovere la restrizione di sola lettura utilizzando Aspose.Words per .NET?

R: Per rimuovere la restrizione di sola lettura da un documento Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Crea un'istanza di`Document` class e impostare una password per il documento utilizzando il file`SetPassword` metodo del`WriteProtection` oggetto.
2.  Impostare il`ReadOnlyRecommended` proprietà del`WriteProtection` opporsi a`false` per rimuovere il consiglio di sola lettura.
3.  Applica protezione illimitata al documento utilizzando il file`Protect` metodo del`Document` oggetto con il`NoProtection` tipo di protezione.
4.  Salvare il documento senza la restrizione di sola lettura utilizzando il file`Save` metodo del`Document` oggetto.

#### D: Posso rimuovere la restrizione di sola lettura da un documento Word senza password?

R: No, non puoi rimuovere la restrizione di sola lettura da un documento Word senza fornire la password corretta. La restrizione di sola lettura è impostata per motivi di sicurezza e rimuoverla senza la password comprometterebbe lo scopo di proteggere l'integrità del documento.

#### D: Posso rimuovere la restrizione di sola lettura da un documento Word con la password errata?

R: No, non puoi rimuovere la restrizione di sola lettura da un documento Word con la password errata. È necessario fornire la password corretta per rimuovere la restrizione di sola lettura e rendere nuovamente modificabile il documento. Ciò garantisce che solo gli utenti autorizzati con la password corretta possano modificare il documento.

#### D: È possibile rimuovere altri tipi di protezione dei documenti utilizzando Aspose.Words per .NET?

R: Sì, Aspose.Words per .NET fornisce vari metodi per rimuovere altri tipi di protezione dei documenti, come la protezione con password, la protezione dei moduli o le restrizioni alla modifica dei documenti. A seconda del tipo di protezione applicata al documento, è possibile utilizzare i metodi e le proprietà corrispondenti forniti da Aspose.Words per rimuovere la protezione specifica e rendere modificabile il documento.
