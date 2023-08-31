---
title: Variablen abrufen
linktitle: Variablen abrufen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Abrufen von Dokumentvariablen mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/get-variables/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um Variablen aus einem Dokument mit Aspose.Words für .NET abzurufen. Mit dieser Funktion können Sie auf in einem Dokument definierte Variablen zugreifen.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das Word-Dokument, aus dem wir die Variablen abrufen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Variablen abrufen

Jetzt rufen wir die im Dokument definierten Variablen ab. Verwenden Sie den folgenden Code:

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

Dieser Code durchläuft jedes Schlüssel-Wert-Paar in den Dokumentvariablen und ruft den Namen und Wert jeder Variablen ab. Die Variablen werden dann verkettet, um die Informationen für jede Variable anzuzeigen.

### Beispielquellcode für Get Variables mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
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

 Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben`dataDir` Variable.

Sie haben jetzt gelernt, wie Sie mit Aspose.Words für .NET Variablen aus einem Dokument abrufen. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie problemlos auf Variablen in Ihren eigenen Dokumenten zugreifen und diese anzeigen.