---
title: Usando opções de limpeza em Aspose.Words para Java
linktitle: Usando opções de limpeza
second_title: API de processamento de documentos Java Aspose.Words
description: Melhore a clareza do documento com opções de limpeza Aspose.Words para Java. Aprenda como remover parágrafos vazios, regiões não utilizadas e muito mais.
type: docs
weight: 10
url: /pt/java/document-manipulation/using-cleanup-options/
---

## Introdução ao uso de opções de limpeza em Aspose.Words para Java

Neste tutorial, exploraremos como usar opções de limpeza em Aspose.Words for Java para manipular e limpar documentos durante o processo de mala direta. As opções de limpeza permitem controlar vários aspectos da limpeza de documentos, como remoção de parágrafos vazios, regiões não utilizadas e muito mais.

## Pré-requisitos

 Antes de começarmos, certifique-se de ter a biblioteca Aspose.Words for Java integrada ao seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/words/java/).

## Etapa 1: remover parágrafos vazios

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserir campos de mesclagem
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Definir opções de limpeza
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Ativar parágrafos de limpeza com sinais de pontuação
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Executar mala direta
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// Salve o documento
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

Neste exemplo, criamos um novo documento, inserimos campos de mesclagem e definimos as opções de limpeza para remover parágrafos vazios. Além disso, habilitamos a remoção de parágrafos com sinais de pontuação. Depois de executar a mala direta, o documento é salvo com a limpeza especificada aplicada.

## Passo 2: Removendo Regiões Não Mescladas

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Defina opções de limpeza para remover regiões não utilizadas
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Executar mala direta com regiões
doc.getMailMerge().executeWithRegions(data);

// Salve o documento
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

Neste exemplo, abrimos um documento existente com regiões de mesclagem, definimos as opções de limpeza para remover regiões não utilizadas e, em seguida, executamos a mala direta com dados vazios. Este processo remove automaticamente as regiões não utilizadas do documento.

## Passo 3: Removendo Campos Vazios

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Defina opções de limpeza para remover campos vazios
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Executar mala direta
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Salve o documento
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

Neste exemplo, abrimos um documento com campos de mesclagem, definimos as opções de limpeza para remover campos vazios e executamos a mala direta com dados. Após a mesclagem, todos os campos vazios serão removidos do documento.

## Etapa 4: remoção de campos não utilizados

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Defina opções de limpeza para remover campos não utilizados
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Executar mala direta
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Salve o documento
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

Neste exemplo, abrimos um documento com campos de mesclagem, definimos as opções de limpeza para remover campos não utilizados e executamos a mala direta com dados. Após a mesclagem, todos os campos não utilizados serão removidos do documento.

## Etapa 5: remoção de campos contendo

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Defina opções de limpeza para remover campos contendo
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Executar mala direta
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Salve o documento
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

Neste exemplo, abrimos um documento com campos de mesclagem, definimos as opções de limpeza para remover os campos contidos e executamos a mala direta com os dados. Após a mesclagem, os próprios campos serão removidos do documento.

## Etapa 6: Removendo linhas vazias da tabela

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Defina opções de limpeza para remover linhas vazias da tabela
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Executar mala direta
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Salve o documento
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

Neste exemplo, abrimos um documento com uma tabela e campos de mesclagem, definimos as opções de limpeza para remover linhas vazias da tabela e executamos a mala direta com os dados. Após a mesclagem, todas as linhas vazias da tabela serão removidas do documento.

## Conclusão

Neste tutorial, você aprendeu como usar opções de limpeza em Aspose.Words for Java para manipular e limpar documentos durante o processo de mala direta. Essas opções fornecem controle refinado sobre a limpeza de documentos, permitindo criar documentos sofisticados e personalizados com facilidade.

## Perguntas frequentes

### Quais são as opções de limpeza no Aspose.Words for Java?

As opções de limpeza em Aspose.Words for Java são configurações que permitem controlar vários aspectos da limpeza de documentos durante o processo de mala direta. Eles permitem remover elementos desnecessários, como parágrafos vazios, regiões não utilizadas e muito mais, garantindo que seu documento final seja bem estruturado e refinado.

### Como posso remover parágrafos vazios do meu documento?

 Para remover parágrafos vazios do seu documento usando Aspose.Words for Java, você pode definir o`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` opção como verdadeira. Isso eliminará automaticamente os parágrafos sem conteúdo, resultando em um documento mais limpo.

###  Qual é o propósito do`REMOVE_UNUSED_REGIONS` cleanup option?

 O`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` A opção é usada para remover regiões em um documento que não possui dados correspondentes durante o processo de mala direta. Ajuda a manter seu documento organizado, eliminando espaços reservados não utilizados.

### Posso remover linhas vazias da tabela de um documento usando Aspose.Words for Java?

 Sim, você pode remover linhas vazias da tabela de um documento definindo o`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`opção de limpeza como verdadeira. Isso excluirá automaticamente todas as linhas da tabela que não contenham dados, garantindo uma tabela bem estruturada em seu documento.

###  O que acontece quando eu defino o`REMOVE_CONTAINING_FIELDS` option?

 Configurando o`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` A opção removerá todo o campo de mesclagem, incluindo o parágrafo que o contém, do documento durante o processo de mala direta. Isto é útil quando você deseja eliminar campos de mesclagem e seus textos associados.

### Como posso remover campos de mesclagem não utilizados do meu documento?

 Para remover campos de mesclagem não utilizados de um documento, você pode definir o`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` opção como verdadeira. Isso eliminará automaticamente os campos de mesclagem que não são preenchidos durante a mala direta, resultando em um documento mais limpo.

###  Qual é a diferença entre`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 O`REMOVE_EMPTY_FIELDS` A opção remove campos de mesclagem que não possuem dados ou estão vazios durante o processo de mala direta. Por outro lado, o`REMOVE_UNUSED_FIELDS` opção remove campos de mesclagem que não são preenchidos com dados durante a mesclagem. A escolha entre eles depende se você deseja remover campos sem conteúdo ou aqueles que não são utilizados na operação de mesclagem específica.

### Como posso ativar a remoção de parágrafos com sinais de pontuação?

 Para permitir a remoção de parágrafos com sinais de pontuação, você pode definir o`cleanupParagraphsWithPunctuationMarks` opção como true e especifique os sinais de pontuação a serem considerados para limpeza. Isso permite que você crie um documento mais refinado, removendo parágrafos desnecessários apenas com pontuação.

### Posso personalizar as opções de limpeza no Aspose.Words for Java?

Sim, você pode personalizar as opções de limpeza de acordo com suas necessidades específicas. Você pode escolher quais opções de limpeza aplicar e configurá-las de acordo com os requisitos de limpeza do documento, garantindo que o documento final atenda aos padrões desejados.