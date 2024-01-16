---
title: Usando dados XML em Aspose.Words para Java
linktitle: Usando dados XML
second_title: API de processamento de documentos Java Aspose.Words
description: Desbloqueie o poder do Aspose.Words para Java. Aprenda manipulação de dados XML, mala direta e sintaxe de bigode com tutoriais passo a passo.
type: docs
weight: 12
url: /pt/java/document-manipulation/using-xml-data/
---

## Introdução ao uso de dados XML em Aspose.Words para Java

Neste guia, exploraremos como trabalhar com dados XML usando Aspose.Words for Java. Você aprenderá como realizar operações de mala direta, incluindo malas diretas aninhadas, e utilizar a sintaxe Moustache com um DataSet. Forneceremos instruções passo a passo e exemplos de código-fonte para ajudá-lo a começar.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:
- [Aspose.Words para Java](https://products.aspose.com/words/java/) instalado.
- Exemplos de arquivos de dados XML para clientes, pedidos e fornecedores.
- Exemplos de documentos do Word para destinos de mala direta.

## Mala direta com dados XML

### 1. Mala direta básica

Para realizar uma mala direta básica com dados XML, siga estas etapas:

```java
DataSet customersDs = new DataSet();
customersDs.readXml("Your Directory Path" + "Mail merge data - Customers.xml");
Document doc = new Document("Your Directory Path" + "Mail merge destinations - Registration complete.docx");
doc.getMailMerge().execute(customersDs.getTables().get("Customer"));
doc.save("Your Directory Path" + "BasicMailMerge.docx");
```

### 2. Mala direta aninhada

Para malas diretas aninhadas, use o seguinte código:

```java
DataSet pizzaDs = new DataSet();
pizzaDs.readXml("Your Directory Path" + "Mail merge data - Orders.xml");
Document doc = new Document("Your Directory Path" + "Mail merge destinations - Invoice.docx");
doc.getMailMerge().setTrimWhitespaces(false);
doc.getMailMerge().executeWithRegions(pizzaDs);
doc.save("Your Directory Path" + "NestedMailMerge.docx");
```

## Sintaxe do bigode usando DataSet

Para aproveitar a sintaxe do Moustache com um DataSet, siga estas etapas:

```java
DataSet ds = new DataSet();
ds.readXml("Your Directory Path" + "Mail merge data - Vendors.xml");
Document doc = new Document("Your Directory Path" + "Mail merge destinations - Vendor.docx");
doc.getMailMerge().setUseNonMergeFields(true);
doc.getMailMerge().executeWithRegions(ds);
doc.save("Your Directory Path" + "MustacheSyntaxUsingDataSet.docx");
```

## Conclusão

Neste guia abrangente, exploramos como usar dados XML de maneira eficaz com Aspose.Words for Java. Você aprendeu como executar várias operações de mala direta, incluindo mala direta básica, mala direta aninhada e como utilizar a sintaxe Moustache com um DataSet. Essas técnicas permitem automatizar a geração e personalização de documentos com facilidade.

## Perguntas frequentes

### Como posso preparar meus dados XML para mala direta?

Certifique-se de que seus dados XML sigam a estrutura necessária, com tabelas e relacionamentos definidos, conforme mostrado nos exemplos fornecidos.

### Posso personalizar o comportamento de corte para valores de mala direta?

 Sim, você pode controlar se os espaços em branco iniciais e finais são cortados durante a mala direta usando`doc.getMailMerge().setTrimWhitespaces(false)`.

### Qual é a sintaxe do Moustache e quando devo usá-la?

 A sintaxe do Moustache permite formatar campos de mala direta de uma forma mais flexível. Usar`doc.getMailMerge().setUseNonMergeFields(true)` para ativar a sintaxe do bigode.