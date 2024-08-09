---
title: Salvando documentos como formato ODT em Aspose.Words para Java
linktitle: Salvando documentos como formato ODT
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como salvar documentos no formato ODT usando Aspose.Words for Java. Garanta a compatibilidade com suítes de escritório de código aberto.
type: docs
weight: 19
url: /pt/java/document-loading-and-saving/saving-documents-as-odt-format/
---

## Introdução ao salvamento de documentos como formato ODT em Aspose.Words for Java

Neste artigo, exploraremos como salvar documentos no formato ODT (Open Document Text) usando Aspose.Words para Java. ODT é um formato de documento de padrão aberto popular usado por vários pacotes de escritório, incluindo OpenOffice e LibreOffice. Ao salvar documentos no formato ODT, você pode garantir a compatibilidade com esses pacotes de software.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Ambiente de Desenvolvimento Java: Certifique-se de ter o Java Development Kit (JDK) instalado em seu sistema.

2.  Aspose.Words para Java: Baixe e instale a biblioteca Aspose.Words para Java. Você pode encontrar o link para download[aqui](https://releases.aspose.com/words/java/).

3. Documento de amostra: tenha um documento do Word de amostra (por exemplo, "Document.docx") que deseja converter para o formato ODT.

## Etapa 1: carregue o documento

Primeiro, vamos carregar o documento do Word usando Aspose.Words for Java:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
```

 Aqui,`"Your Directory Path"` deve apontar para o diretório onde seu documento está localizado.

## Etapa 2: especificar opções de salvamento de ODT

Para salvar o documento como ODT, precisamos especificar as opções de salvamento da ODT. Além disso, podemos definir a unidade de medida do documento. O Open Office usa centímetros, enquanto o MS Office usa polegadas. Vamos configurá-lo para polegadas:

```java
OdtSaveOptions saveOptions = new OdtSaveOptions();
saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES);
```

## Etapa 3: salve o documento

Agora é hora de salvar o documento no formato ODT:

```java
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

 Aqui,`"Your Directory Path"` deve apontar para o diretório onde você deseja salvar o arquivo ODT convertido.

## Código-fonte completo para salvar documentos como formato ODT em Aspose.Words para Java

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
// O Open Office usa centímetros ao especificar comprimentos, larguras e outras formatações mensuráveis
// e propriedades de conteúdo em documentos, enquanto o MS Office usa polegadas.
OdtSaveOptions saveOptions = new OdtSaveOptions(); { saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES); }
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Conclusão

Neste artigo, aprendemos como salvar documentos no formato ODT usando Aspose.Words for Java. Isso pode ser especialmente útil quando você precisa garantir a compatibilidade com pacotes de escritório de código aberto como OpenOffice e LibreOffice.

## Perguntas frequentes

### Como posso baixar Aspose.Words para Java?

 Você pode baixar Aspose.Words para Java no site da Aspose. Visita[este link](https://releases.aspose.com/words/java/)para acessar a página de download.

### Qual é a vantagem de salvar documentos no formato ODT?

Salvar documentos no formato ODT garante compatibilidade com pacotes de escritório de código aberto como OpenOffice e LibreOffice, facilitando o acesso e a edição de seus documentos pelos usuários desses pacotes de software.

### Preciso especificar a unidade de medida ao salvar no formato ODT?

Sim, é uma boa prática especificar a unidade de medida. O Open Office usa centímetros por padrão, portanto, configurá-lo para polegadas garante uma formatação consistente.

### Posso converter vários documentos para o formato ODT em um processo em lote?

Sim, você pode automatizar a conversão de vários documentos para o formato ODT usando Aspose.Words for Java, iterando seus arquivos de documentos e aplicando o processo de conversão.

### O Aspose.Words for Java é compatível com as versões mais recentes do Java?

Aspose.Words for Java é atualizado regularmente para oferecer suporte às versões mais recentes do Java, garantindo compatibilidade e melhorias de desempenho. Certifique-se de verificar os requisitos do sistema na documentação para obter as informações mais recentes.