---
title: Docx mit Passwort verschlüsseln
linktitle: Docx mit Passwort verschlüsseln
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine DOCX-Datei mit einem Passwort verschlüsseln. Vollständiges Tutorial zur Dokumentensicherheit.
type: docs
weight: 10
url: /de/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um eine DOCX-Datei mit einem Passwort mithilfe von Aspose.Words für .NET zu verschlüsseln. Mit dieser Funktion können Sie Ihr Dokument schützen, indem Sie es nur mit einem angegebenen Passwort zugänglich machen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Verweise hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Laden des Dokuments

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In diesem Schritt laden wir das Dokument mit`Document` -Methode und Übergabe des Pfads zur zu ladenden DOCX-Datei.

## Schritt 3: OOXML-Sicherungsoptionen konfigurieren

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

In diesem Schritt konfigurieren wir die OOXML-Speicheroptionen, indem wir eine neue erstellen`OoxmlSaveOptions` Objekt. Wir geben das gewünschte Passwort zum Verschlüsseln des Dokuments an, indem wir das festlegen`Password` -Eigenschaft Ihrem benutzerdefinierten Passwort zu.

## Schritt 4: Verschlüsseln des Dokuments mit Passwort

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 In diesem letzten Schritt speichern wir das Dokument mit`Save` -Methode und Übergabe des Pfads zur Ausgabedatei mit der`.docx` Erweiterung zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um Ihr DOCX-Dokument mit einem Passwort zu verschlüsseln. Die resultierende Datei wird im angegebenen Verzeichnis mit dem Namen „WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx“ gespeichert. Bewahren Sie Ihr Passwort unbedingt sicher auf, da es zum Öffnen des verschlüsselten Dokuments benötigt wird.

### Beispielquellcode für „Docx mit Passwort verschlüsseln“ mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktionalität der Verschlüsselung einer DOCX-Datei mit einem Passwort mithilfe von Aspose.Words für .NET untersucht. Wir haben gelernt, wie wir unsere Dokumente schützen können, indem wir sie nur mit einem festgelegten Passwort zugänglich machen.

Die Dokumentenverschlüsselung ist eine wesentliche Sicherheitsmaßnahme zum Schutz sensibler Informationen. Dank Aspose.Words für .NET können wir diese Funktionalität problemlos zu unseren Anwendungen hinzufügen.

Indem Sie die bereitgestellten Schritte befolgen, können Sie die Passwortverschlüsselung in Ihre Aspose.Words für .NET-Projekte integrieren und die Vertraulichkeit Ihrer Dokumente sicherstellen.

Experimentieren Sie ruhig mit anderen Funktionen von Aspose.Words für .NET, um Ihre Anwendungen mit erweiterten Funktionen zur Dokumentbearbeitung zu bereichern.
