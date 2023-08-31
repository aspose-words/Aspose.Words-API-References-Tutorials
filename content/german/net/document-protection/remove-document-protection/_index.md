---
title: Entfernen Sie den Dokumentschutz im Word-Dokument
linktitle: Entfernen Sie den Dokumentschutz im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Schutz in einem Word-Dokument entfernen.
type: docs
weight: 10
url: /de/net/document-protection/remove-document-protection/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Aufheben des Dokumentschutzes von Aspose.Words für .NET. Mit dieser Funktion können Sie den Schutz in einem Word-Dokument entfernen, um es für die weitere Bearbeitung zugänglich zu machen. Folgen Sie den unteren Schritten:

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

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie den Dokumentschutz in einem Word-Dokument mit Aspose.Words für .NET entfernen. Indem Sie die bereitgestellten Schritte befolgen, können Sie den Schutz eines Dokuments ganz einfach aufheben und es für die weitere Bearbeitung zugänglich machen. Aspose.Words für .NET bietet eine leistungsstarke API, mit der Sie Dokumentschutzeinstellungen bearbeiten und die Sicherheitsstufe für Ihre Word-Dokumente anpassen können. Durch das Entfernen des Dokumentschutzes haben Sie die Flexibilität, den Inhalt und die Formatierung des Dokuments nach Bedarf zu ändern.

### FAQs zum Entfernen des Dokumentschutzes in Word-Dokumenten

#### F: Was ist Dokumentenschutz in Aspose.Words für .NET?

A: Der Dokumentschutz in Aspose.Words für .NET bezieht sich auf die Funktion, mit der Sie Sicherheitsmaßnahmen auf ein Word-Dokument anwenden können, um Bearbeitung, Formatierung und Inhaltsänderungen einzuschränken. Es trägt dazu bei, die Integrität und Vertraulichkeit des Dokuments sicherzustellen.

#### F: Wie kann ich den Dokumentenschutz mit Aspose.Words für .NET entfernen?

A: Um den Dokumentenschutz mit Aspose.Words für .NET zu entfernen, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine Instanz von`Document` Klasse und a`DocumentBuilder` Objekt.
2.  Benutzen Sie die`DocumentBuilder` um dem Dokument Inhalte hinzuzufügen.
3.  Ruf den`Unprotect` Methode der`Document` Objekt, um jeglichen vorhandenen Schutz aus dem Dokument zu entfernen. Dies kann ohne Passwort oder durch Angabe des richtigen Passwortes erfolgen.
4.  Speichern Sie das ungeschützte Dokument mit`Save` Methode der`Document` Objekt.

#### F: Kann ich den Schutz eines Word-Dokuments ohne Passwort entfernen?

 A: Ja, Sie können den Schutz eines Word-Dokuments ohne Passwort mit Aspose.Words für .NET entfernen. Durch den Anruf`Unprotect` Methode der`Document`Wenn Sie ein Objekt ohne Angabe eines Kennworts öffnen, können Sie den Schutz des Dokuments aufheben, wenn es zuvor ohne Kennwort geschützt war.

#### F: Wie kann ich den Schutz eines Word-Dokuments mit einem Passwort aufheben?

 A: Um den Schutz von einem Word-Dokument zu entfernen, das mit einem Passwort geschützt war, müssen Sie beim Aufrufen das richtige Passwort angeben`Unprotect` Methode der`Document` Objekt. Dadurch wird sichergestellt, dass nur Benutzer mit dem richtigen Passwort den Schutz aufheben und auf das Dokument zur Bearbeitung zugreifen können.

#### F: Kann ich bestimmte Schutztypen aus einem Word-Dokument entfernen?

 A: Ja, mit Aspose.Words für .NET können Sie bestimmte Schutztypen selektiv aus einem Word-Dokument entfernen. Durch den Anruf`Unprotect` Methode der`Document` Objekt können Sie den gewünschten Schutztyp entfernen, z. B. den Leseschutz oder den Formularschutz, während andere Schutztypen intakt bleiben.