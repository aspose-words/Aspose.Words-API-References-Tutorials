---
title: Variablen abrufen
linktitle: Variablen abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Abrufen von Dokumentvariablen mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/get-variables/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Variablen aus einem Dokument mit Aspose.Words für .NET abzurufen. Mit dieser Funktion können Sie auf in einem Dokument definierte Variablen zugreifen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, aus dem wir die Variablen abrufen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Variablen abrufen

Nun werden wir die im Dokument definierten Variablen abrufen. Verwenden Sie den folgenden Code:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Dieser Code durchläuft jedes Schlüssel-Wert-Paar in den Dokumentvariablen und ruft den Namen und den Wert jeder Variable ab. Die Variablen werden dann verkettet, um die Informationen für jede Variable anzuzeigen.

### Beispielquellcode zum Abrufen von Variablen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET Variablen aus einem Dokument abrufen. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie problemlos auf Variablen aus Ihren eigenen Dokumenten zugreifen und diese anzeigen.