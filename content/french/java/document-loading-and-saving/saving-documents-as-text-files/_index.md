---
title: Enregistrement de documents sous forme de fichiers texte dans Aspose.Words pour Java
linktitle: Enregistrement de documents sous forme de fichiers texte
second_title: API de traitement de documents Java Aspose.Words
description: Découvrez comment enregistrer des documents sous forme de fichiers texte dans Aspose.Words pour Java. Suivez notre guide étape par étape avec des exemples de code Java.
type: docs
weight: 24
url: /fr/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Introduction à l'enregistrement de documents sous forme de fichiers texte dans Aspose.Words pour Java

Dans ce didacticiel, nous explorerons comment enregistrer des documents sous forme de fichiers texte à l'aide de la bibliothèque Aspose.Words pour Java. Aspose.Words est une API Java puissante pour travailler avec des documents Word et offre diverses options pour enregistrer des documents dans différents formats, y compris du texte brut. Nous couvrirons les étapes pour y parvenir et fournirons un exemple de code Java en cours de route.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Kit de développement Java (JDK) installé sur votre système.
-  Bibliothèque Aspose.Words pour Java intégrée à votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/java/).
- Connaissance de base de la programmation Java.

## Étape 1 : Créer un document

Pour enregistrer un document sous forme de fichier texte, nous devons d'abord créer un document à l'aide d'Aspose.Words. Voici un simple extrait de code Java pour créer un document avec du contenu :

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

Dans ce code, nous créons un nouveau document et y ajoutons du texte, y compris du texte dans différentes langues.

## Étape 2 : définir les options d'enregistrement du texte

Ensuite, nous devons définir les options d'enregistrement du texte qui spécifient comment le document doit être enregistré en tant que fichier texte. Nous pouvons configurer divers paramètres tels que l'ajout de marques de bidi, l'indentation de liste, etc. Regardons deux exemples :

### Exemple 1 : Ajout de marques Bidi

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 Dans cet exemple, nous créons un`TxtSaveOptions` objet et définissez le`AddBidiMarks`propriété à`true` pour inclure des marques bidi dans la sortie texte.

### Exemple 2 : Utilisation du caractère de tabulation pour l'indentation de liste

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Ici, nous configurons les options de sauvegarde pour utiliser un caractère de tabulation pour l'indentation de la liste avec un nombre de 1.

## Étape 3 : Enregistrez le document sous forme de texte

Maintenant que nous avons défini les options d'enregistrement du texte, nous pouvons enregistrer le document en tant que fichier texte. Le code suivant montre comment procéder :

```java
doc.save("output.txt", saveOptions);
```

 Remplacer`"output.txt"` avec le chemin de fichier souhaité où vous souhaitez enregistrer le fichier texte.

## Code source complet pour enregistrer des documents sous forme de fichiers texte dans Aspose.Words pour Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Créez une liste avec trois niveaux d'indentation.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Créez une liste avec trois niveaux d'indentation.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Conclusion

Dans ce didacticiel, nous avons appris à enregistrer des documents sous forme de fichiers texte dans Aspose.Words pour Java. Nous avons couvert les étapes pour créer un document, définir les options d'enregistrement du texte et enregistrer le document au format texte. Aspose.Words offre une grande flexibilité en matière d'enregistrement de documents, vous permettant d'adapter la sortie à vos besoins spécifiques.

## FAQ

### Comment ajouter des marques bidi à la sortie texte ?

 Pour ajouter des marques bidi à la sortie texte, définissez le`AddBidiMarks` propriété de`TxtSaveOptions` à`true`. Par exemple:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### Puis-je personnaliser le caractère d’indentation de la liste ?

 Oui, vous pouvez personnaliser le caractère d'indentation de la liste en configurant le`ListIndentation` propriété de`TxtSaveOptions`. Par exemple, pour utiliser un caractère de tabulation pour l'indentation de liste, vous pouvez procéder comme suit :

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Aspose.Words for Java est-il adapté à la gestion de texte multilingue ?

Oui, Aspose.Words for Java est adapté à la gestion de texte multilingue. Il prend en charge différentes langues et codages de caractères, ce qui en fait un choix polyvalent pour travailler avec des documents dans différentes langues.

### Comment puis-je accéder à davantage de documentation et de ressources pour Aspose.Words pour Java ?

 Vous pouvez trouver une documentation et des ressources complètes pour Aspose.Words pour Java sur le site Web de documentation Aspose :[Documentation Aspose.Words pour Java](https://reference.aspose.com/words/java/).

### Où puis-je télécharger Aspose.Words pour Java ?

 Vous pouvez télécharger la bibliothèque Aspose.Words pour Java depuis le site Web Aspose :[Télécharger Aspose.Words pour Java](https://releases.aspose.com/words/java/).