---
title: Docx mit Passwort verschlüsseln
linktitle: Docx mit Passwort verschlüsseln
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine DOCX-Datei mit einem Kennwort verschlüsseln. Vollständiges Tutorial zur Dokumentensicherheit.
type: docs
weight: 10
url: /de/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
In diesem Tutorial untersuchen wir den bereitgestellten C#-Quellcode, um eine DOCX-Datei mit einem Kennwort unter Verwendung von Aspose.Words für .NET zu verschlüsseln. Mit dieser Funktion können Sie Ihr Dokument schützen, indem Sie es nur mit einem angegebenen Kennwort zugänglich machen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Dokument einlegen

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In diesem Schritt laden wir das Dokument mit dem`Document` Methode und Übergabe des Pfads an die zu ladende DOCX-Datei.

## Schritt 3: OOXML-Sicherungsoptionen konfigurieren

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

 In diesem Schritt konfigurieren wir OOXML-Speicheroptionen, indem wir eine neue`OoxmlSaveOptions` Objekt. Wir geben das gewünschte Passwort zur Verschlüsselung des Dokuments an, indem wir den`Password` Eigenschaft zu Ihrem benutzerdefinierten Passwort.

## Schritt 4: Dokument mit Passwort verschlüsseln

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 Im letzten Schritt speichern wir das Dokument mit dem`Save` -Methode und Übergabe des Pfades zur Ausgabedatei mit der`.docx` Erweiterung, zusammen mit den angegebenen Speicheroptionen.

Jetzt können Sie den Quellcode ausführen, um Ihr DOCX-Dokument mit einem Passwort zu verschlüsseln. Die resultierende Datei wird im angegebenen Verzeichnis unter dem Namen „WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx“ gespeichert. Bewahren Sie Ihr Passwort gut auf, da es zum Öffnen des verschlüsselten Dokuments benötigt wird.

### Beispiel-Quellcode zum Verschlüsseln von Docx mit Passwort unter Verwendung von Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktion zum Verschlüsseln einer DOCX-Datei mit einem Kennwort mithilfe von Aspose.Words für .NET untersucht. Wir haben gelernt, wie wir unsere Dokumente schützen können, indem wir sie nur mit einem bestimmten Kennwort zugänglich machen.

Die Dokumentenverschlüsselung ist eine wesentliche Sicherheitsmaßnahme zum Schutz vertraulicher Informationen. Dank Aspose.Words für .NET können wir diese Funktionalität problemlos zu unseren Anwendungen hinzufügen.

Indem Sie die angegebenen Schritte befolgen, können Sie die Kennwortverschlüsselung in Ihre Aspose.Words für .NET-Projekte integrieren und die Vertraulichkeit Ihrer Dokumente gewährleisten.

Experimentieren Sie mit den anderen Funktionen von Aspose.Words für .NET, um Ihre Anwendungen mit erweiterten Funktionen zur Dokumentbearbeitung zu bereichern.
