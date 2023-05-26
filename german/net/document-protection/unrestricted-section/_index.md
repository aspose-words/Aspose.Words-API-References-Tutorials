---
title: Uneingeschränkter Abschnitt
linktitle: Uneingeschränkter Abschnitt
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET uneingeschränkte Abschnitte in einem Word-Dokument definieren.
type: docs
weight: 10
url: /de/net/document-protection/unrestricted-section/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der uneingeschränkten Abschnittsfunktion von Aspose.Words für .NET. Mit dieser Funktion können Sie bestimmte Abschnitte in einem Word-Dokument definieren, die nicht geschützt sind, selbst wenn der Rest des Dokuments geschützt ist. Folgen Sie den unteren Schritten:

## Schritt 1: Erstellen des Dokuments und der Abschnitte

Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Inhalte zum Dokument hinzufügen
Verwenden Sie das DocumentBuilder-Objekt, um dem Dokument Inhalte hinzuzufügen und Abschnittsumbrüche einzufügen:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Schritt 3: Dokument und Abschnitte schützen

Der Abschnittsschutz funktioniert nur, wenn der Dokumentenschutz aktiviert ist und nur die Bearbeitung in Formularfeldern erlaubt ist. Sie können das Dokument mit der Protect()-Methode des Document-Objekts schützen:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Stellen Sie sicher, dass Sie die richtige Schutzart angeben und das gewünschte Passwort festlegen.

## Schritt 4: Deaktivieren des Schutzes für einen bestimmten Abschnitt

Standardmäßig sind alle Abschnitte geschützt, aber Sie können den Schutz für einen bestimmten Abschnitt mithilfe der ProtectedForForms-Eigenschaft des Section-Objekts selektiv deaktivieren:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

In diesem Beispiel ist der Schutz für den ersten Abschnitt deaktiviert.

## Schritt 5: Speichern Sie das Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben, um das Dokument mit uneingeschränkten Abschnitten zu speichern.

### Beispielquellcode für einen uneingeschränkten Abschnitt mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für den uneingeschränkten Abschnitt mit Aspose.Words für .NET:


```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Fügen Sie zwei Abschnitte mit etwas Text ein.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Der Abschnittsschutz funktioniert nur, wenn der Dokumentschutz aktiviert ist und nur die Bearbeitung in Formularfeldern zulässig ist.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Standardmäßig sind alle Abschnitte geschützt, wir können den Schutz jedoch gezielt deaktivieren.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach uneingeschränkte Abschnitte in Ihrem Word-Dokument definieren.

