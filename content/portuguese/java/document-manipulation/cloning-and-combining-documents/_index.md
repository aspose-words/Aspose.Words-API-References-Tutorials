---
title: Clonando e combinando documentos em Aspose.Words para Java
linktitle: Clonando e Combinando Documentos
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como clonar e combinar documentos em Aspose.Words for Java. Guia passo a passo com exemplos de código-fonte.
type: docs
weight: 27
url: /pt/java/document-manipulation/cloning-and-combining-documents/
---

## Introdução à clonagem e combinação de documentos em Aspose.Words para Java

Neste tutorial, exploraremos como clonar e combinar documentos usando Aspose.Words for Java. Abordaremos vários cenários, incluindo clonagem de um documento, inserção de documentos em pontos de substituição, marcadores e durante operações de mala direta.

## Etapa 1: clonar um documento

 Para clonar um documento em Aspose.Words for Java, você pode usar o`deepClone()` método. Aqui está um exemplo simples:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "CloneAndCombineDocuments.CloningDocument.docx");
```

Este código criará um clone profundo do documento original e o salvará como um novo arquivo.

## Passo 2: Inserindo Documentos em Pontos de Substituição

Você pode inserir documentos em pontos de substituição específicos em outro documento. Veja como você pode fazer isso:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

 Neste exemplo, usamos um`FindReplaceOptions` objeto para especificar um manipulador de retorno de chamada para a substituição. O`InsertDocumentAtReplaceHandler` classe lida com a lógica de inserção.

## Passo 3: Inserindo Documentos nos Favoritos

Para inserir um documento em um marcador específico em outro documento, você pode usar o seguinte código:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
Document subDoc = new Document("Your Directory Path" + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

 Aqui, encontramos o marcador por nome e usamos o`insertDocument` método para inserir o conteúdo do`subDoc` documento no local do marcador.

## Etapa 4: Inserir documentos durante a mala direta

Você pode inserir documentos durante uma operação de mala direta em Aspose.Words for Java. Veja como:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { "Your Directory Path" + "Document insertion 2.docx" });
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

 Neste exemplo, definimos um retorno de chamada de mesclagem de campo usando o`InsertDocumentAtMailMergeHandler` classe para tratar a inserção do documento especificado pelo campo "Documento_1".

## Conclusão

clonagem e combinação de documentos em Aspose.Words for Java pode ser realizada usando várias técnicas. Se você precisa clonar um documento, inserir conteúdo em pontos de substituição, marcadores ou durante a mala direta, o Aspose.Words oferece recursos poderosos para manipular documentos sem problemas.

## Perguntas frequentes

### Como faço para clonar um documento em Aspose.Words for Java?

 Você pode clonar um documento em Aspose.Words for Java usando o`deepClone()` método. Aqui está um exemplo:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "ClonedDocument.docx");
```

### Como posso inserir um documento em um marcador?

 Para inserir um documento em um marcador no Aspose.Words for Java, você pode encontrar o marcador por nome e usar o`insertDocument` método para inserir o conteúdo. Aqui está um exemplo:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
Document subDoc = new Document("Your Directory Path" + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CombinedDocument.docx");
```

### Como insiro documentos durante a mala direta no Aspose.Words for Java?

Você pode inserir documentos durante a mala direta em Aspose.Words for Java definindo um campo de retorno de chamada de mesclagem e especificando o documento a ser inserido. Aqui está um exemplo:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { "Your Directory Path" + "DocumentToInsert.docx" });
mainDoc.save("Your Directory Path" + "MergedDocument.docx");
```

 Neste exemplo, o`InsertDocumentAtMailMergeHandler`classe lida com a lógica de inserção para o "DocumentField" durante a mala direta.