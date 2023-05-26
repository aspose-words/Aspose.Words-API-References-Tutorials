---
title: Passwortschutz
linktitle: Passwortschutz
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Ihre Word-Dokumente mit Aspose.Words für .NET mit einem Passwort schützen.
type: docs
weight: 10
url: /de/net/document-protection/password-protection/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Passwortschutzfunktion von Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument mit einem Passwort schützen, um dessen Vertraulichkeit zu gewährleisten. Folgen Sie den unteren Schritten:

## Schritt 1: Dokument erstellen und Schutz anwenden

Erstellen Sie zunächst eine Instanz der Document-Klasse:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Passwortschutz anwenden

Anschließend können Sie mithilfe der Protect()-Methode des Document-Objekts einen Kennwortschutz anwenden:

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

Ersetzen Sie „Passwort“ unbedingt durch das tatsächliche Passwort, das Sie zum Schutz des Dokuments verwenden möchten.

## Schritt 3: Speichern des geschützten Dokuments

Abschließend können Sie das geschützte Dokument mit der Save()-Methode des Document-Objekts speichern:

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen zum Speichern des geschützten Dokuments angeben.

### Beispielquellcode für den Passwortschutz mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für den Passwortschutz mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	//Wenden Sie den Dokumentenschutz an.
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

Denken Sie daran, „IHR DOKUMENTENVERZEICHNIS“ durch das Verzeichnis Ihrer Dokumente und „Passwort“ durch das tatsächliche Passwort zu ersetzen, das Sie verwenden möchten.

