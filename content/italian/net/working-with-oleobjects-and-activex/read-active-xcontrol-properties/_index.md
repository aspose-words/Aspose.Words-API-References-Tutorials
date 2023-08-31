---
title: Leggi le proprietà XControl attive dal file Word
linktitle: Leggi le proprietà XControl attive dal file Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Leggi le proprietà dei controlli ActiveX in un file Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

In questa guida passo passo, ti mostreremo come leggere le proprietà dei controlli ActiveX in un file Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output di markdown.

## Passaggio 1: inizializzazione del documento

 Il primo passo è inizializzare il file`Document` oggetto caricando il documento Word contenente i controlli ActiveX. Assicurati di sostituire`MyDir` con il percorso effettivo della directory contenente il documento.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Passaggio 2: ripristina i controlli ActiveX

 In questo passaggio, ripeteremo ciascuno di essi`Shape` del documento per recuperare i controlli ActiveX e leggerne le proprietà.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Codice sorgente di esempio per la lettura delle proprietà Active XControl utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per leggere le proprietà dei controlli ActiveX utilizzando Aspose.Words per .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## Conclusione

Questa guida ti ha mostrato come leggere le proprietà dei controlli ActiveX in un file Word utilizzando Aspose.Words per .NET. Seguendo i passaggi descritti è possibile inizializzare il documento, recuperare i controlli ActiveX e leggerne le proprietà. Utilizza il codice di esempio fornito come punto di partenza e personalizzalo in base alle tue esigenze specifiche.

La lettura delle proprietà dei controlli ActiveX consente di estrarre informazioni importanti dai file Word contenenti questi controlli. Aspose.Words per .NET offre potenti funzionalità per l'elaborazione di parole con controlli ActiveX e automatizzando l'elaborazione dei documenti.

### Domande frequenti

#### D: Qual è il primo passaggio per leggere le proprietà dei controlli ActiveX in un file Word?

 R: Il primo passo è inizializzare il file`Document` oggetto caricando il documento Word contenente i controlli ActiveX. Assicurati di sostituire`MyDir` con il percorso effettivo della directory contenente il documento.

#### D: Come posso inserire i controlli ActiveX nel documento?

 R: Per recuperare i controlli ActiveX, è necessario scorrere ciascuno di essi`Shape` del documento e verificare se si tratta di un controllo ActiveX. Usa il`OleFormat` proprietà di`Shape` per accedere al`OleControl` oggetto e recuperare le proprietà necessarie.

#### D: quali proprietà dei controlli ActiveX posso leggere?

R: Puoi leggere varie proprietà dei controlli ActiveX, come didascalia, valore, stato abilitato o disabilitato, tipo e childNode associati al controllo.

#### D: Come posso ottenere il numero totale di controlli ActiveX nel documento?

 R: Per ottenere il numero totale di controlli ActiveX nel documento, puoi utilizzare il file`GetChildNodes` metodo del`Document` oggetto che specifica il`NodeType.Shape` digitare e includere i nodi figlio.