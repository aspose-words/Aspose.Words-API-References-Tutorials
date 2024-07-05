---
title: Dokumentschutz im Word-Dokument entfernen
linktitle: Dokumentschutz im Word-Dokument entfernen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Schutz in einem Word-Dokument entfernen.
type: docs
weight: 10
url: /de/net/document-protection/remove-document-protection/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Aufheben des Dokumentschutzes von Aspose.Words für .NET. Mit dieser Funktion können Sie den Schutz in einem Word-Dokument entfernen, um es für weitere Bearbeitungen zugänglich zu machen. Befolgen Sie die folgenden Schritte:

## Schritt 1: Erstellen des Dokuments und Hinzufügen von Inhalten

Beginnen Sie mit der Erstellung einer Instanz der Document-Klasse und eines DocumentBuilder-Objekts:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Dem Dokument Inhalt hinzufügen

Verwenden Sie das DocumentBuilder-Objekt, um dem Dokument Inhalt hinzuzufügen:

```csharp
builder.Writeln("Text added to a document.");
```

## Schritt 3: Dokumentschutz aufheben

Um den Dokumentschutz aufzuheben, können Sie die Methode Unprotect() des Document-Objekts verwenden. Sie können den Schutz wahlweise ohne oder mit korrektem Passwort aufheben. Aufheben des passwortlosen Schutzes:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Ersetzen Sie „newPassword“ unbedingt durch das richtige Dokumentkennwort.

## Schritt 4: Speichern Sie das Dokument ungeschützt

Speichern Sie das Dokument abschließend ungeschützt mit der Methode Save() des Document-Objekts:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Geben Sie unbedingt den richtigen Pfad und Dateinamen an, um das Dokument ungeschützt zu speichern.

### Beispielquellcode zum Entfernen des Dokumentenschutzes mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Aufheben des Dokumentschutzes mit Aspose.Words für .NET:

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

// Der Dokumentenschutz kann entweder ohne Kennwort oder mit dem richtigen Kennwort aufgehoben werden.
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Indem Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET den Schutz aus Word-Dokumenten ganz einfach entfernen.

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie den Dokumentschutz in einem Word-Dokument mit Aspose.Words für .NET entfernen. Indem Sie die angegebenen Schritte befolgen, können Sie den Schutz eines Dokuments ganz einfach aufheben und es für weitere Bearbeitungen zugänglich machen. Aspose.Words für .NET bietet eine leistungsstarke API, mit der Sie Dokumentschutzeinstellungen bearbeiten und die Sicherheitsstufe für Ihre Word-Dokumente anpassen können. Durch das Entfernen des Dokumentschutzes haben Sie die Flexibilität, den Dokumentinhalt und die Formatierung nach Bedarf zu ändern.

### FAQs zum Entfernen des Dokumentenschutzes in einem Word-Dokument

#### F: Was ist Dokumentenschutz in Aspose.Words für .NET?

A: Der Dokumentschutz in Aspose.Words für .NET bezieht sich auf die Funktion, mit der Sie Sicherheitsmaßnahmen auf ein Word-Dokument anwenden können, um Bearbeitung, Formatierung und Inhaltsänderungen einzuschränken. Dies trägt dazu bei, die Integrität und Vertraulichkeit des Dokuments sicherzustellen.

#### F: Wie kann ich den Dokumentenschutz mit Aspose.Words für .NET entfernen?

A: Um den Dokumentschutz mit Aspose.Words für .NET zu entfernen, können Sie diese Schritte befolgen:
1.  Erstellen Sie eine Instanz des`Document` Klasse und eine`DocumentBuilder` Objekt.
2.  Verwenden Sie die`DocumentBuilder` , um dem Dokument Inhalt hinzuzufügen.
3.  Ruf den`Unprotect` Methode der`Document` Objekt, um den vorhandenen Schutz des Dokuments zu entfernen. Dies kann ohne Kennwort oder durch Eingabe des richtigen Kennworts erfolgen.
4.  Speichern Sie das ungeschützte Dokument mit dem`Save` Methode der`Document` Objekt.

#### F: Kann ich den Schutz eines Word-Dokuments ohne Kennwort entfernen?

 A: Ja, Sie können den Schutz eines Word-Dokuments ohne Kennwort mit Aspose.Words für .NET entfernen. Durch Aufrufen des`Unprotect` Methode der`Document`-Objekt ohne Angabe eines Kennworts können Sie den Schutz des Dokuments aufheben, wenn es zuvor ohne Kennwort geschützt war.

#### F: Wie kann ich den Kennwortschutz eines Word-Dokuments aufheben?

 A: Um den Schutz eines Word-Dokuments aufzuheben, das mit einem Passwort geschützt war, müssen Sie beim Aufrufen des`Unprotect` Methode der`Document` Objekt. Dadurch wird sichergestellt, dass nur Benutzer mit dem richtigen Passwort den Schutz aufheben und zum Bearbeiten auf das Dokument zugreifen können.

#### F: Kann ich bestimmte Schutztypen aus einem Word-Dokument entfernen?

 A: Ja, mit Aspose.Words für .NET können Sie bestimmte Schutztypen selektiv aus einem Word-Dokument entfernen. Durch den Aufruf des`Unprotect` Methode der`Document` -Objekt können Sie den gewünschten Schutztyp entfernen, z. B. Nur-Lese-Schutz oder Formularschutz, während andere Schutztypen intakt bleiben.