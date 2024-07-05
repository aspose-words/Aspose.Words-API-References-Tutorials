---
title: Schreibschutz entfernen
linktitle: Schreibschutz entfernen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die schreibgeschützte Einschränkung aus einem Word-Dokument entfernen.
type: docs
weight: 10
url: /de/net/document-protection/remove-read-only-restriction/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Entfernen der schreibgeschützten Einschränkung von Aspose.Words für .NET. Mit dieser Funktion können Sie die schreibgeschützte Einschränkung aus einem Word-Dokument entfernen, um es bearbeitbar zu machen. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument erstellen und Schutz festlegen

Beginnen Sie mit der Erstellung einer Instanz der Klasse „Document“:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Legen Sie mit der SetPassword()-Eigenschaft des WriteProtection-Objekts ein Kennwort für das Dokument fest:

Ersetzen Sie „MyPassword“ unbedingt durch das tatsächliche Passwort, das Sie zum Schutz des Dokuments verwendet haben.

## Schritt 2: Schreibschutz entfernen

Um die Schreibschutzbeschränkung aufzuheben, setzen Sie die Eigenschaft ReadOnlyRecommended auf „false“:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Schritt 3: Uneingeschränkten Schutz anwenden

Wenden Sie abschließend mit der Protect()-Methode des Document-Objekts uneingeschränkten Schutz an:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Geben Sie unbedingt den richtigen Pfad und Dateinamen an, um das Dokument ohne die Schreibschutzbeschränkung zu speichern.

### Beispielquellcode zum Entfernen der Nur-Lese-Beschränkung mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Entfernen der schreibgeschützten Einschränkung mit Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Geben Sie ein maximal 15 Zeichen langes Passwort ein.
doc.WriteProtection.SetPassword("MyPassword");

//Entfernen Sie die schreibgeschützte Option.
doc.WriteProtection.ReadOnlyRecommended = false;

// Schreibschutz ohne jeglichen Schutz anwenden.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Indem Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET die schreibgeschützte Einschränkung aus einem Word-Dokument ganz einfach entfernen.


## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die schreibgeschützte Einschränkung aus einem Word-Dokument entfernt. Indem Sie die angegebenen Schritte befolgen, können Sie die Einschränkung problemlos entfernen und das Dokument wieder bearbeitbar machen. Aspose.Words für .NET bietet einen umfassenden Satz von Funktionen zum Verwalten von Dokumentschutz und -beschränkungen und bietet Ihnen Flexibilität und Kontrolle über die Sicherheit und Bearbeitungsfunktionen Ihrer Word-Dokumente.

### Häufig gestellte Fragen

#### F: Was ist die schreibgeschützte Einschränkung in Aspose.Words für .NET?

A: Die schreibgeschützte Einschränkung in Aspose.Words für .NET bezieht sich auf eine Funktion, mit der Sie ein Word-Dokument als schreibgeschützt festlegen können, sodass Benutzer keine Änderungen am Inhalt oder an der Formatierung vornehmen können. Diese Einschränkung schützt die Integrität des Dokuments und stellt sicher, dass es nicht versehentlich oder böswillig geändert wird.

#### F: Wie kann ich die schreibgeschützte Einschränkung mit Aspose.Words für .NET entfernen?

A: Um die schreibgeschützte Einschränkung aus einem Word-Dokument mit Aspose.Words für .NET zu entfernen, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine Instanz des`Document` Klasse und legen Sie ein Kennwort für das Dokument fest.`SetPassword` Methode der`WriteProtection` Objekt.
2.  Legen Sie die`ReadOnlyRecommended` Eigentum der`WriteProtection` Einwände erheben gegen`false` um die schreibgeschützte Empfehlung zu entfernen.
3.  Wenden Sie uneingeschränkten Schutz auf das Dokument an mit dem`Protect` Methode der`Document` Objekt mit dem`NoProtection` Schutzart.
4.  Speichern Sie das Dokument ohne Schreibschutz mit dem`Save` Methode der`Document` Objekt.

#### F: Kann ich die Schreibschutzbeschränkung für ein Word-Dokument ohne Kennwort aufheben?

A: Nein, Sie können die Schreibschutzbeschränkung eines Word-Dokuments nicht aufheben, ohne das richtige Kennwort anzugeben. Die Schreibschutzbeschränkung wurde aus Sicherheitsgründen festgelegt und das Aufheben ohne Kennwort würde den Zweck des Schutzes der Dokumentintegrität untergraben.

#### F: Kann ich die Lesebeschränkung aus einem Word-Dokument mit dem falschen Kennwort entfernen?

A: Nein, Sie können die Schreibschutzbeschränkung eines Word-Dokuments nicht mit dem falschen Passwort entfernen. Um die Schreibschutzbeschränkung zu entfernen und das Dokument wieder bearbeitbar zu machen, muss das richtige Passwort eingegeben werden. Dadurch wird sichergestellt, dass nur autorisierte Benutzer mit dem richtigen Passwort das Dokument ändern können.

#### F: Ist es möglich, andere Arten von Dokumentenschutz mit Aspose.Words für .NET zu entfernen?

A: Ja, Aspose.Words für .NET bietet verschiedene Methoden zum Entfernen anderer Arten von Dokumentschutz, wie z. B. Kennwortschutz, Formularschutz oder Einschränkungen bei der Dokumentbearbeitung. Abhängig von der Art des auf das Dokument angewendeten Schutzes können Sie die entsprechenden von Aspose.Words bereitgestellten Methoden und Eigenschaften verwenden, um den spezifischen Schutz zu entfernen und das Dokument bearbeitbar zu machen.
