---
title: Entfernen benutzerdefinierter Dokumenteigenschaften
linktitle: Entfernen benutzerdefinierter Dokumenteigenschaften
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Entfernen benutzerdefinierter Eigenschaften aus einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-properties/remove-custom-document-properties/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um benutzerdefinierte Eigenschaften aus einem Dokument mit Aspose.Words für .NET zu entfernen. Mit dieser Funktion können Sie eine bestimmte benutzerdefinierte Eigenschaft aus einem Dokument entfernen.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Words für .NET verwiesen wird.

## Schritt 2: Dokument einlegen

In diesem Schritt laden wir das Word-Dokument, aus dem wir die benutzerdefinierten Eigenschaften entfernen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Benutzerdefinierte Eigenschaften löschen

Lassen Sie uns nun eine bestimmte benutzerdefinierte Eigenschaft aus dem Dokument entfernen. Verwenden Sie den folgenden Code:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Dieser Code entfernt die benutzerdefinierte Eigenschaft „Autorisierungsdatum“ aus dem Dokument. Sie können „Autorisierungsdatum“ durch den Namen der benutzerdefinierten Eigenschaft ersetzen, die Sie entfernen möchten.

### Beispielquellcode zum Entfernen benutzerdefinierter Dokumenteigenschaften mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Achten Sie darauf, den korrekten Dokumentpfad im`dataDir` Variable.

Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET benutzerdefinierte Eigenschaften aus einem Dokument entfernen. Indem Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie benutzerdefinierte Eigenschaften problemlos aus Ihren eigenen Dokumenten entfernen.