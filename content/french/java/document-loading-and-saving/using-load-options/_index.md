---
title: Utilisation des options de chargement dans Aspose.Words pour Java
linktitle: Utilisation des options de chargement
second_title: API de traitement de documents Java Aspose.Words
description: Maîtriser les options de chargement dans Aspose.Words pour Java. Personnalisez le chargement des documents, gérez le chiffrement, convertissez les formes, définissez les versions Word et bien plus encore pour un traitement efficace des documents Java.
type: docs
weight: 11
url: /fr/java/document-loading-and-saving/using-load-options/
---

## Introduction à l'utilisation des options de chargement dans Aspose.Words pour Java

Dans ce didacticiel, nous allons découvrir comment utiliser les options de chargement dans Aspose.Words pour Java. Les options de chargement vous permettent de personnaliser la manière dont les documents sont chargés et traités. Nous aborderons divers scénarios, notamment la mise à jour de champs modifiés, le chargement de documents chiffrés, la conversion de formes en Office Math, la définition de la version MS Word, la spécification d'un dossier temporaire, la gestion des avertissements et la conversion de métafichiers en PNG. Plongeons-nous dans le vif du sujet étape par étape.

## Mettre à jour les champs sales

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

 Cet extrait de code montre comment mettre à jour les champs modifiés dans un document.`setUpdateDirtyFields(true)` Cette méthode est utilisée pour garantir que les champs sales sont mis à jour pendant le chargement du document.

## Charger un document crypté

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

 Ici, nous chargeons un document crypté à l'aide d'un mot de passe.`LoadOptions` le constructeur accepte le mot de passe du document et vous pouvez également spécifier un nouveau mot de passe lors de l'enregistrement du document à l'aide de`OdtSaveOptions`.

## Convertir une forme en mathématiques de bureau

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx");
```

 Ce code montre comment convertir des formes en objets Office Math lors du chargement du document.`setConvertShapeToOfficeMath(true)`La méthode permet cette conversion.

## Définir la version MS Word

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

 Vous pouvez spécifier la version MS Word pour le chargement du document. Dans cet exemple, nous définissons la version sur Microsoft Word 2010 à l'aide de`setMswVersion`.

## Utiliser le dossier temporaire

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

 En définissant le dossier temporaire à l'aide de`setTempFolder`, vous pouvez contrôler où les fichiers temporaires sont stockés pendant le traitement du document.

## Rappel d'avertissement

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        // Gérez les avertissements au fur et à mesure qu'ils surviennent lors du chargement du document.
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

Ce code montre comment configurer un rappel d'avertissement pour gérer les avertissements lors du chargement d'un document. Vous pouvez personnaliser le comportement de votre application lorsque des avertissements se produisent.

## Convertir les métafichiers en PNG

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

 Pour convertir des métafichiers (par exemple, WMF) en images PNG pendant le chargement du document, vous pouvez utiliser le`setConvertMetafilesToPng(true)` méthode.

## Code source complet pour travailler avec les options de chargement dans Aspose.Words pour Java

```java
public void updateDirtyFields() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setUpdateDirtyFields(true);
	}
	Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
}
@Test
public void loadEncryptedDocument() throws Exception {
	Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
@Test
public void convertShapeToOfficeMath() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertShapeToOfficeMath(true);
	}
	Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx");
}
@Test
public void setMsWordVersion() throws Exception {
	// Créez un nouvel objet LoadOptions, qui chargera les documents selon la spécification MS Word 2019 par défaut
	// et changez la version de chargement en Microsoft Word 2010.
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setMswVersion(MsWordVersion.WORD_2010);
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
@Test
public void useTempFolder() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setTempFolder("Your Directory Path");
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
@Test
public void warningCallback() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
public static class DocumentLoadingWarningCallback implements IWarningCallback {
	public void warning(WarningInfo info) {
		//Imprime les avertissements et leurs détails au fur et à mesure qu'ils apparaissent pendant le chargement du document.
		System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
		System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
	}
}
@Test
public void convertMetafilesToPng() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertMetafilesToPng(true);
	}
	Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
@Test
public void loadChm() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setEncoding(Charset.forName("windows-1251"));
	}
	Document doc = new Document("Your Directory Path" + "HTML help.chm", loadOptions);
}
```

## Conclusion

Dans ce didacticiel, nous avons abordé divers aspects de l'utilisation des options de chargement dans Aspose.Words pour Java. Les options de chargement jouent un rôle crucial dans la personnalisation de la manière dont les documents sont chargés et traités, vous permettant d'adapter le traitement de vos documents à vos besoins spécifiques. Récapitulons les points clés abordés dans ce guide :

## FAQ

### Comment puis-je gérer les avertissements lors du chargement du document ?

 Vous pouvez configurer un rappel d'avertissement comme indiqué dans le`warningCallback()` méthode ci-dessus. Personnalisez le`DocumentLoadingWarningCallback` classe pour gérer les avertissements en fonction des exigences de votre application.

### Puis-je convertir des formes en objets Office Math lors du chargement d’un document ?

 Oui, vous pouvez convertir des formes en objets Office Math en utilisant`loadOptions.setConvertShapeToOfficeMath(true)`.

### Comment spécifier la version MS Word pour le chargement du document ?

 Utiliser`loadOptions.setMswVersion(MsWordVersion.WORD_2010)` pour spécifier la version MS Word pour le chargement du document.

###  Quel est le but de la`setTempFolder` method in Load Options?

 Le`setTempFolder`La méthode vous permet de spécifier le dossier dans lequel les fichiers temporaires sont stockés pendant le traitement du document.