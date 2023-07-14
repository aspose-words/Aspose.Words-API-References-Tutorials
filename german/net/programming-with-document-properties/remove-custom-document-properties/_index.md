---
title: Benutzerdefinierte Dokumenteigenschaften entfernen
linktitle: Benutzerdefinierte Dokumenteigenschaften entfernen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Entfernen benutzerdefinierter Eigenschaften aus einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/remove-custom-document-properties/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um benutzerdefinierte Eigenschaften aus einem Dokument mit Aspose.Words für .NET zu entfernen. Mit dieser Funktion können Sie eine bestimmte benutzerdefinierte Eigenschaft aus einem Dokument entfernen.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das Word-Dokument, aus dem wir die benutzerdefinierten Eigenschaften entfernen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Benutzerdefinierte Eigenschaften löschen

Entfernen wir nun eine bestimmte benutzerdefinierte Eigenschaft aus dem Dokument. Verwenden Sie den folgenden Code:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Dieser Code entfernt die benutzerdefinierte Eigenschaft „Autorisiertes Datum“ aus dem Dokument. Sie können „Autorisiertes Datum“ durch den Namen der benutzerdefinierten Eigenschaft ersetzen, die Sie entfernen möchten.

### Beispielquellcode zum Entfernen benutzerdefinierter Dokumenteigenschaften mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben`dataDir` Variable.

Sie haben jetzt erfahren, wie Sie mit Aspose.Words für .NET benutzerdefinierte Eigenschaften aus einem Dokument entfernen. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie benutzerdefinierte Eigenschaften ganz einfach aus Ihren eigenen Dokumenten entfernen.