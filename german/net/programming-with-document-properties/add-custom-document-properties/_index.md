---
title: Fügen Sie benutzerdefinierte Dokumenteigenschaften hinzu
linktitle: Fügen Sie benutzerdefinierte Dokumenteigenschaften hinzu
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Hinzufügen benutzerdefinierter Eigenschaften zu einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/add-custom-document-properties/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um mit Aspose.Words für .NET benutzerdefinierte Eigenschaften zu einem Dokument hinzuzufügen. Mit dieser Funktion können Sie dem Dokument benutzerdefinierte Informationen hinzufügen.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das Word-Dokument, dem wir benutzerdefinierte Eigenschaften hinzufügen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Benutzerdefinierte Eigenschaften hinzufügen

Fügen wir nun dem Dokument benutzerdefinierte Eigenschaften hinzu. Verwenden Sie den folgenden Code, um die Eigenschaften hinzuzufügen:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Dieser Code prüft zunächst, ob die Eigenschaft „Autorisiert“ bereits in den benutzerdefinierten Eigenschaften vorhanden ist. Wenn es vorhanden ist, wird der Prozess unterbrochen. Andernfalls werden die benutzerdefinierten Eigenschaften dem Dokument hinzugefügt.

### Beispielquellcode für das Hinzufügen benutzerdefinierter Dokumenteigenschaften mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben`dataDir` Variable.

Sie haben jetzt gelernt, wie Sie mit Aspose.Words für .NET benutzerdefinierte Eigenschaften zu einem Dokument hinzufügen. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie ganz einfach Ihre eigenen benutzerdefinierten Eigenschaften zu Ihren Dokumenten hinzufügen.