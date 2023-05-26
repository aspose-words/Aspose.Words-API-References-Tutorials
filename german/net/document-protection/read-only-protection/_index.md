---
title: Nur-Lese-Schutz
linktitle: Nur-Lese-Schutz
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Ihre schreibgeschützten Word-Dokumente mit Aspose.Words für .NET schützen.
type: docs
weight: 10
url: /de/net/document-protection/read-only-protection/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Leseschutzfunktion von Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument schreibgeschützt machen, um unbefugte Änderungen zu verhindern. Folgen Sie den unteren Schritten:

## Schritt 1: Dokument erstellen und Schutz anwenden

Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Schreiben Sie Inhalte in das Dokument
Verwenden Sie das DocumentBuilder-Objekt, um Inhalte in das Dokument zu schreiben:

```csharp
builder.Write("Open document as read-only");
```

## Schritt 3: Passwort festlegen und Dokument schreibgeschützt machen

Legen Sie mithilfe der SetPassword()-Eigenschaft des WriteProtection-Objekts ein Kennwort für das Dokument fest:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Ersetzen Sie „MyPassword“ unbedingt durch das tatsächliche Passwort, das Sie verwenden möchten.

## Schritt 4: Schreibgeschütztes Dokument anwenden

Machen Sie das Dokument schreibgeschützt, indem Sie die ReadOnlyRecommended-Eigenschaft auf true setzen:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Schritt 5: Wenden Sie den Leseschutz an und speichern Sie das Dokument

Wenden Sie abschließend den schreibgeschützten Schutz mit der Protect()-Methode des Document-Objekts an:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen zum Speichern des geschützten Dokuments angeben.

### Beispielquellcode für den Leseschutz mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für den schreibgeschützten Schutz mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	// Geben Sie ein bis zu 15 Zeichen langes Passwort ein.
	doc.WriteProtection.SetPassword("MyPassword");

	// Machen Sie das Dokument schreibgeschützt.
	doc.WriteProtection.ReadOnlyRecommended = true;

	// Wenden Sie den Schreibschutz als schreibgeschützt an.
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Wenn Sie diese Schritte befolgen, können Sie Ihre Dokumente ganz einfach schützen

