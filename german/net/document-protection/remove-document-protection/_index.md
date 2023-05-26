---
title: Entfernen Sie den Dokumentenschutz
linktitle: Entfernen Sie den Dokumentenschutz
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Schutz aus einem Word-Dokument entfernen.
type: docs
weight: 10
url: /de/net/document-protection/remove-document-protection/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Aufheben des Dokumentschutzes von Aspose.Words für .NET. Mit dieser Funktion können Sie den Schutz eines Word-Dokuments aufheben, um es für die weitere Bearbeitung zugänglich zu machen. Folgen Sie den unteren Schritten:

## Schritt 1: Erstellen des Dokuments und Hinzufügen von Inhalten

Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Inhalte zum Dokument hinzufügen

Verwenden Sie das DocumentBuilder-Objekt, um dem Dokument Inhalte hinzuzufügen:

```csharp
builder.Writeln("Text added to a document.");
```

## Schritt 3: Dokumentschutz aufheben

Um den Schutz des Dokuments aufzuheben, können Sie die Unprotect()-Methode des Document-Objekts verwenden. Sie können wählen, ob Sie den Schutz ohne Passwort oder mit korrektem Passwort entfernen möchten. Passwortlosen Schutz entfernen:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Stellen Sie sicher, dass Sie „newPassword“ durch das richtige Dokumentkennwort ersetzen.

## Schritt 4: Speichern Sie das Dokument ohne Schutz

Abschließend speichern Sie das Dokument ungeschützt mit der Save()-Methode des Document-Objekts:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben, um das Dokument ungeschützt zu speichern.

### Beispielquellcode zum Entfernen des Dokumentenschutzes mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Aufheben des Dokumentschutzes mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Text added to a document.");

	// Der Schutz von Dokumenten kann entweder ohne Passwort oder mit dem richtigen Passwort entfernt werden.
	doc.Unprotect();
	doc.Protect(ProtectionType.ReadOnly, "newPassword");
	doc.Unprotect("newPassword");

	doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Wenn Sie diese Schritte befolgen, können Sie den Schutz von Word-Dokumenten mit Aspose.Words für .NET ganz einfach entfernen.
