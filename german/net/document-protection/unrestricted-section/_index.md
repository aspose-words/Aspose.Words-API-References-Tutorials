---
title: Uneingeschränkter Abschnitt im Word-Dokument
linktitle: Uneingeschränkter Abschnitt im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

//Standardmäßig sind alle Abschnitte geschützt, wir können den Schutz jedoch gezielt deaktivieren.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach uneingeschränkte Abschnitte in Ihrem Word-Dokument definieren.

## Abschluss

In diesem Tutorial haben wir die uneingeschränkte Abschnittsfunktion von Aspose.Words für .NET untersucht, die es ermöglicht, dass bestimmte Abschnitte in einem Word-Dokument ungeschützt bleiben, während der Rest des Dokuments geschützt ist. Indem Sie die bereitgestellten Schritte befolgen, können Sie ganz einfach Abschnitte in Ihrem Dokument definieren, in denen Benutzer den Inhalt frei bearbeiten können, während der Schutz anderer Abschnitte erhalten bleibt. Aspose.Words für .NET bietet leistungsstarke Funktionen für den Dokumentenschutz und die individuelle Anpassung, sodass Sie die Bearbeitungsberechtigungen in Ihren Word-Dokumenten steuern können.

### FAQs zum uneingeschränkten Abschnitt in Word-Dokumenten

#### F: Was sind uneingeschränkte Abschnitte in Aspose.Words für .NET?

A: Uneingeschränkte Abschnitte in Aspose.Words für .NET sind bestimmte Abschnitte innerhalb eines Word-Dokuments, die nicht geschützt sind, selbst wenn der Rest des Dokuments geschützt ist. In diesen Abschnitten können Benutzer den darin enthaltenen Inhalt ändern und gleichzeitig den Schutz der übrigen Teile des Dokuments aufrechterhalten.

#### F: Wie kann ich mit Aspose.Words für .NET uneingeschränkte Abschnitte erstellen?

A: Um mit Aspose.Words für .NET uneingeschränkte Abschnitte in einem Word-Dokument zu erstellen, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine Instanz von`Document` Klasse und a`DocumentBuilder` Objekt.
2.  Benutzen Sie die`DocumentBuilder` um Inhalte zum Dokument hinzuzufügen und Abschnittsumbrüche einzufügen.
3.  Schützen Sie das Dokument mit dem`Protect` Methode der`Document` Objekt unter Angabe der gewünschten Schutzart und des Passworts.
4.  Deaktivieren Sie den Schutz für einen bestimmten Abschnitt, indem Sie Folgendes festlegen`ProtectedForForms` Eigentum des entsprechenden`Section` widersprechen`false`.
5. Speichern Sie das geänderte Dokument.

#### F: Kann ich in einem Word-Dokument mehrere uneingeschränkte Abschnitte haben?

 A: Ja, Sie können in einem Word-Dokument mehrere uneingeschränkte Abschnitte haben. Durch selektives Deaktivieren des Schutzes für bestimmte Abschnitte mithilfe von`ProtectedForForms` Eigentum der`Section`Objekt können Sie mehrere Abschnitte definieren, in denen Benutzer den Inhalt frei ändern können, während andere Abschnitte geschützt bleiben.

#### Q4. Kann ich den Schutz von einem Abschnitt entfernen, der ursprünglich geschützt war?
 Ja, Sie können den Schutz von einem Abschnitt entfernen, der ursprünglich geschützt war, indem Sie Folgendes festlegen`ProtectedForForms` Eigentum des entsprechenden`Section` widersprechen`false`. Dadurch können Benutzer den Inhalt innerhalb dieses bestimmten Abschnitts ohne Einschränkungen bearbeiten.

#### F: Welche Schutzarten können auf ein Word-Dokument angewendet werden?

A: Aspose.Words für .NET bietet verschiedene Schutztypen, die auf ein Word-Dokument angewendet werden können, darunter:
- NoProtection: Es wird kein Schutz angewendet.
- AllowOnlyRevisions: Benutzer können nur Änderungen am Dokument vornehmen.
- AllowOnlyComments: Benutzer können dem Dokument nur Kommentare hinzufügen.
- AllowOnlyFormFields: Benutzer können nur Formularfelder im Dokument bearbeiten.
- ReadOnly: Das Dokument ist schreibgeschützt und es ist keine Bearbeitung möglich.


