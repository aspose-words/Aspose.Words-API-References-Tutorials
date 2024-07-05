---
title: Hinzufügen benutzerdefinierter Dokumenteigenschaften
linktitle: Hinzufügen benutzerdefinierter Dokumenteigenschaften
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Hinzufügen benutzerdefinierter Eigenschaften zu einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/add-custom-document-properties/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um einem Dokument mit Aspose.Words für .NET benutzerdefinierte Eigenschaften hinzuzufügen. Mit dieser Funktion können Sie dem Dokument benutzerdefinierte Informationen hinzufügen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, dem wir benutzerdefinierte Eigenschaften hinzufügen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

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

Dieser Code prüft zunächst, ob die Eigenschaft „Autorisiert“ bereits in den benutzerdefinierten Eigenschaften vorhanden ist. Wenn dies der Fall ist, wird der Vorgang abgebrochen. Andernfalls werden die benutzerdefinierten Eigenschaften dem Dokument hinzugefügt.

### Beispielquellcode zum Hinzufügen benutzerdefinierter Dokumenteigenschaften mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
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

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET einem Dokument benutzerdefinierte Eigenschaften hinzufügen. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie Ihren Dokumenten ganz einfach Ihre eigenen benutzerdefinierten Eigenschaften hinzufügen.