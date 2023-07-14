---
title: Entfernen Sie die Lesebeschränkung
linktitle: Entfernen Sie die Lesebeschränkung
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

//Entfernen Sie die schreibgeschützte Option.
doc.WriteProtection.ReadOnlyRecommended = false;

// Schreibschutz ohne Schutz anwenden.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach die Lesebeschränkung aus einem Word-Dokument entfernen.


## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Lesebeschränkung aus einem Word-Dokument entfernt. Indem Sie die bereitgestellten Schritte befolgen, können Sie die Einschränkung einfach aufheben und das Dokument wieder bearbeitbar machen. Aspose.Words für .NET bietet umfassende Funktionen zur Verwaltung des Dokumentschutzes und der Einschränkungen und bietet Ihnen so Flexibilität und Kontrolle über die Sicherheit und Bearbeitungsmöglichkeiten Ihrer Word-Dokumente.

### FAQs

#### F: Was ist die schreibgeschützte Einschränkung in Aspose.Words für .NET?

A: Die schreibgeschützte Beschränkung in Aspose.Words für .NET bezieht sich auf eine Funktion, mit der Sie ein Word-Dokument als schreibgeschützt festlegen können, sodass Benutzer keine Änderungen am Inhalt oder an der Formatierung vornehmen können. Diese Einschränkung trägt zum Schutz der Integrität des Dokuments bei und stellt sicher, dass es nicht versehentlich oder in böswilliger Absicht geändert wird.

#### F: Wie kann ich die Lesebeschränkung mit Aspose.Words für .NET entfernen?

A: Um die Lesebeschränkung aus einem Word-Dokument mithilfe von Aspose.Words für .NET zu entfernen, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine Instanz von`Document` Klasse und legen Sie mit dem ein Passwort für das Dokument fest`SetPassword` Methode der`WriteProtection` Objekt.
2.  Stellen Sie die ein`ReadOnlyRecommended`Eigentum der`WriteProtection` widersprechen`false` um die schreibgeschützte Empfehlung zu entfernen.
3.  Wenden Sie mit dem uneingeschränkten Schutz auf das Dokument an`Protect` Methode der`Document` Objekt mit dem`NoProtection` Schutzart.
4.  Speichern Sie das Dokument ohne die Lesebeschränkung mit`Save` Methode der`Document` Objekt.

#### F: Kann ich die Lesebeschränkung aus einem Word-Dokument ohne Passwort entfernen?

A: Nein, Sie können die Lesebeschränkung nicht aus einem Word-Dokument entfernen, ohne das richtige Passwort anzugeben. Die Lesebeschränkung dient Sicherheitszwecken. Wenn Sie sie ohne Kennwort entfernen, würde dies den Zweck des Schutzes der Dokumentintegrität beeinträchtigen.

#### F: Kann ich die Lesebeschränkung aus einem Word-Dokument mit dem falschen Passwort entfernen?

A: Nein, Sie können die Lesebeschränkung nicht aus einem Word-Dokument mit dem falschen Passwort entfernen. Um die Lesebeschränkung aufzuheben und das Dokument wieder bearbeitbar zu machen, muss das richtige Passwort angegeben werden. Dadurch wird sichergestellt, dass nur autorisierte Benutzer mit dem richtigen Passwort das Dokument ändern können.

#### F: Ist es möglich, andere Arten des Dokumentschutzes mit Aspose.Words für .NET zu entfernen?

A: Ja, Aspose.Words für .NET bietet verschiedene Methoden zum Entfernen anderer Arten des Dokumentschutzes, wie z. B. Passwortschutz, Formularschutz oder Einschränkungen bei der Dokumentbearbeitung. Abhängig von der Art des auf das Dokument angewendeten Schutzes können Sie die entsprechenden von Aspose.Words bereitgestellten Methoden und Eigenschaften verwenden, um den spezifischen Schutz zu entfernen und das Dokument bearbeitbar zu machen.
