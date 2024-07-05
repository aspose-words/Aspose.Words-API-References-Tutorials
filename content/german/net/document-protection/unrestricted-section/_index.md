---
title: Uneingeschränkter Abschnitt im Word-Dokument
linktitle: Uneingeschränkter Abschnitt im Word-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET uneingeschränkte Abschnitte in einem Word-Dokument definieren.
type: docs
weight: 10
url: /de/net/document-protection/unrestricted-section/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der uneingeschränkten Abschnittsfunktion von Aspose.Words für .NET. Mit dieser Funktion können Sie bestimmte Abschnitte in einem Word-Dokument definieren, die nicht geschützt sind, auch wenn der Rest des Dokuments geschützt ist. Befolgen Sie die folgenden Schritte:

## Schritt 1: Erstellen des Dokuments und der Abschnitte

Beginnen Sie mit der Erstellung einer Instanz der Document-Klasse und eines DocumentBuilder-Objekts:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Dem Dokument Inhalt hinzufügen
Verwenden Sie das DocumentBuilder-Objekt, um dem Dokument Inhalt hinzuzufügen und Abschnittsumbrüche einzufügen:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Schritt 3: Dokument und Abschnitte schützen

Der Abschnittsschutz funktioniert nur, wenn der Dokumentschutz aktiviert ist und nur das Bearbeiten von Formularfeldern zulässig ist. Sie können das Dokument mit der Protect()-Methode des Document-Objekts schützen:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Achten Sie darauf, die richtige Schutzart anzugeben und das gewünschte Passwort festzulegen.

## Schritt 4: Schutz für einen bestimmten Abschnitt deaktivieren

Standardmäßig sind alle Abschnitte geschützt, Sie können den Schutz für einen bestimmten Abschnitt jedoch selektiv deaktivieren, indem Sie die Eigenschaft ProtectedForForms des Section-Objekts verwenden:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

In diesem Beispiel ist der Schutz für den ersten Abschnitt deaktiviert.

## Schritt 5: Speichern Sie das Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Geben Sie unbedingt den richtigen Pfad und Dateinamen an, um das Dokument mit uneingeschränkten Abschnitten zu speichern.

### Beispielquellcode für uneingeschränkten Abschnitt mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für den uneingeschränkten Abschnitt mit Aspose.Words für .NET:


```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Fügen Sie zwei Abschnitte mit etwas Text ein.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Der Abschnittsschutz funktioniert nur, wenn der Dokumentschutz aktiviert ist und nur das Bearbeiten in Formularfeldern zulässig ist.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Standardmäßig sind alle Abschnitte geschützt, aber wir können den Schutz selektiv deaktivieren.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET problemlos uneingeschränkte Abschnitte in Ihrem Word-Dokument definieren.

## Abschluss

In diesem Tutorial haben wir die uneingeschränkte Abschnittsfunktion von Aspose.Words für .NET untersucht, die es ermöglicht, dass bestimmte Abschnitte in einem Word-Dokument ungeschützt bleiben, während der Rest des Dokuments geschützt ist. Indem Sie die angegebenen Schritte befolgen, können Sie problemlos Abschnitte in Ihrem Dokument definieren, in denen Benutzer den Inhalt frei bearbeiten können, während der Schutz für andere Abschnitte erhalten bleibt. Aspose.Words für .NET bietet leistungsstarke Funktionen zum Schutz und zur Anpassung von Dokumenten und gibt Ihnen Kontrolle über die Bearbeitungsberechtigungen in Ihren Word-Dokumenten.

### FAQs zum uneingeschränkten Abschnitt im Word-Dokument

#### F: Was sind uneingeschränkte Abschnitte in Aspose.Words für .NET?

A: Uneingeschränkte Abschnitte in Aspose.Words für .NET sind bestimmte Abschnitte innerhalb eines Word-Dokuments, die nicht geschützt sind, auch wenn der Rest des Dokuments geschützt ist. Diese Abschnitte ermöglichen es Benutzern, den Inhalt darin zu ändern, während der Schutz für die übrigen Teile des Dokuments erhalten bleibt.

#### F: Wie kann ich mit Aspose.Words für .NET uneingeschränkte Abschnitte erstellen?

A: Um mit Aspose.Words für .NET uneingeschränkte Abschnitte in einem Word-Dokument zu erstellen, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine Instanz des`Document` Klasse und eine`DocumentBuilder` Objekt.
2.  Verwenden Sie die`DocumentBuilder` um dem Dokument Inhalt hinzuzufügen und Abschnittsumbrüche einzufügen.
3.  Schützen Sie das Dokument mit dem`Protect` Methode der`Document` Objekt und geben Sie den gewünschten Schutztyp und das Kennwort an.
4.  Deaktivieren Sie den Schutz für einen bestimmten Abschnitt, indem Sie den`ProtectedForForms` Eigentum des entsprechenden`Section` Einwände erheben gegen`false`.
5. Speichern Sie das geänderte Dokument.

#### F: Kann ich in einem Word-Dokument mehrere uneingeschränkte Abschnitte haben?

 A: Ja, Sie können mehrere uneingeschränkte Abschnitte in einem Word-Dokument haben. Indem Sie den Schutz für bestimmte Abschnitte selektiv deaktivieren, indem Sie`ProtectedForForms` Eigentum der`Section`-Objekt können Sie mehrere Abschnitte definieren, in denen Benutzer den Inhalt frei ändern können, während andere Abschnitte geschützt bleiben.

#### F4. Kann ich den Schutz eines Abschnitts entfernen, der ursprünglich geschützt war?
 Ja, Sie können den Schutz eines Abschnitts aufheben, der ursprünglich geschützt war, indem Sie`ProtectedForForms` Eigentum des entsprechenden`Section` Einwände erheben gegen`false`. Dadurch können Benutzer den Inhalt innerhalb dieses bestimmten Abschnitts ohne Einschränkungen bearbeiten.

#### F: Welche Schutzarten können auf ein Word-Dokument angewendet werden?

A: Aspose.Words für .NET bietet verschiedene Schutztypen, die auf ein Word-Dokument angewendet werden können, darunter:
- NoProtection: Es wird kein Schutz angewendet.
- AllowOnlyRevisions: Benutzer können nur Überarbeitungen am Dokument vornehmen.
- AllowOnlyComments: Benutzer können dem Dokument nur Kommentare hinzufügen.
- AllowOnlyFormFields: Benutzer können nur Formularfelder im Dokument bearbeiten.
- Schreibgeschützt: Das Dokument ist schreibgeschützt und kann nicht bearbeitet werden.


