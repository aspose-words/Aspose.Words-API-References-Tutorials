---
title: Entfernen Sie die Lesebeschränkung
linktitle: Entfernen Sie die Lesebeschränkung
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Lesebeschränkung aus einem Word-Dokument entfernen.
type: docs
weight: 10
url: /de/net/document-protection/remove-read-only-restriction/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Entfernen der schreibgeschützten Einschränkung von Aspose.Words für .NET. Mit dieser Funktion können Sie die Lesebeschränkung aus einem Word-Dokument entfernen, um es bearbeitbar zu machen. Folgen Sie den unteren Schritten:

## Schritt 1: Erstellen des Dokuments und Festlegen des Schutzes

Erstellen Sie zunächst eine Instanz der Document-Klasse:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Legen Sie mithilfe der SetPassword()-Eigenschaft des WriteProtection-Objekts ein Kennwort für das Dokument fest:

Ersetzen Sie „MyPassword“ unbedingt durch das tatsächliche Passwort, das Sie zum Schutz des Dokuments verwendet haben.

## Schritt 2: Entfernen Sie die Lesebeschränkung

Um die Lesebeschränkung zu entfernen, legen Sie die ReadOnlyRecommended-Eigenschaft auf „false“ fest:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Schritt 3: Uneingeschränkten Schutz anwenden

Wenden Sie abschließend uneingeschränkten Schutz mit der Protect()-Methode des Document-Objekts an:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben, um das Dokument ohne die schreibgeschützte Beschränkung zu speichern.

### Beispielquellcode zum Entfernen der Nur-Lese-Einschränkung mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Entfernen der Lesebeschränkung mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	// Geben Sie ein bis zu 15 Zeichen langes Passwort ein.
	doc.WriteProtection.SetPassword("MyPassword");

	// Entfernen Sie die schreibgeschützte Option.
	doc.WriteProtection.ReadOnlyRecommended = false;

	// Schreibschutz ohne Schutz anwenden.
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach die Lesebeschränkung aus einem Word-Dokument entfernen.

