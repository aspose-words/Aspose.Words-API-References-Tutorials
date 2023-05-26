---
title: Leggi le proprietà di Active XControl
linktitle: Leggi le proprietà di Active XControl
second_title: Riferimento all'API Aspose.Words per .NET
description: Leggi le proprietà dei controlli ActiveX in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

In questa guida dettagliata, ti mostreremo come leggere le proprietà dei controlli ActiveX in un documento Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: inizializzazione del documento

 Il primo passo è inizializzare il file`Document` oggetto caricando il documento Word contenente i controlli ActiveX. Assicurati di sostituire`MyDir` con il percorso effettivo della directory contenente il documento.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Passaggio 2: ripristinare i controlli ActiveX

 In questo passaggio, itereremo attraverso ciascuno`Shape` del documento per recuperare i controlli ActiveX e leggerne le proprietà.

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

### Codice sorgente di esempio per la lettura delle proprietà di Active XControl utilizzando Aspose.Words per .NET

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

