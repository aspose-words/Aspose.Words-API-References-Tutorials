---
title: Alterar fonte de cultura de atualização de campo
linktitle: Alterar fonte de cultura de atualização de campo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como alterar a fonte da cultura de atualização do campo em Aspose.Words for .NET com este guia. Controle facilmente a formatação de datas com base em diferentes culturas.
type: docs
weight: 10
url: /pt/net/working-with-fields/change-field-update-culture-source/
---
## Introdução

Neste tutorial, vamos mergulhar no mundo do Aspose.Words for .NET e explorar como alterar a fonte da cultura de atualização do campo. Se você estiver lidando com documentos do Word que incluem campos de data e precisar controlar como essas datas são formatadas com base em diferentes culturas, este guia é para você. Vamos percorrer o processo passo a passo, garantindo que você compreenda cada conceito e possa aplicá-lo de forma eficaz em seus projetos.

## Pré-requisitos

Antes de entrarmos no código, certifique-se de ter o seguinte:

-  Aspose.Words for .NET: você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
- Ambiente de Desenvolvimento: Qualquer IDE compatível com .NET (por exemplo, Visual Studio).
- Conhecimento básico de C#: Este tutorial pressupõe que você tenha um conhecimento fundamental de programação C#.

## Importar namespaces

Primeiro, vamos importar os namespaces necessários para o nosso projeto. Isso garantirá que tenhamos acesso a todas as classes e métodos necessários fornecidos pelo Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Agora, vamos dividir o exemplo em várias etapas para ajudá-lo a entender como alterar a fonte da cultura de atualização do campo no Aspose.Words for .NET.

## Etapa 1: inicializar o documento

 O primeiro passo é criar uma nova instância do`Document` aula e um`DocumentBuilder`. Isso estabelece a base para construir e manipular nosso documento do Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir campos com localidade específica

A seguir, precisamos inserir campos no documento. Neste exemplo, inseriremos dois campos de data. Definiremos a localidade da fonte como alemão (LocaleId = 1031) para demonstrar como a cultura afeta o formato da data.

```csharp
builder.Font.LocaleId = 1031; // Alemão
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

## Etapa 3: definir a origem da cultura de atualização de campo

 Para controlar a cultura utilizada na atualização dos campos, definimos o`FieldUpdateCultureSource` propriedade do`FieldOptions`aula. Esta propriedade determina se a cultura é obtida do código do campo ou do documento.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

## Etapa 4: executar mala direta

Agora precisamos executar uma mala direta para preencher os campos com dados reais. Neste exemplo, definiremos o segundo campo de data (`Date2`) até 1º de janeiro de 2011.

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

## Etapa 5: salve o documento

Finalmente, salvamos o documento no diretório especificado. Esta etapa conclui o processo de alteração da origem da cultura de atualização de campo.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusão

E aí está! Você alterou com êxito a origem da cultura de atualização do campo em Aspose.Words for .NET. Seguindo essas etapas, você pode garantir que seus documentos do Word exibam datas e outros valores de campo de acordo com as configurações de cultura especificadas. Isto pode ser particularmente útil ao gerar documentos para um público internacional.

## Perguntas frequentes

###  Qual é o propósito de definir o`LocaleId`?
 O`LocaleId` especifica as configurações de cultura do texto, o que afeta como as datas e outros dados sensíveis à localidade são formatados.

### Posso usar uma localidade diferente do alemão?
 Sim, você pode definir o`LocaleId`para qualquer identificador de localidade válido. Por exemplo, 1033 para inglês (Estados Unidos).

###  O que acontece se eu não definir o`FieldUpdateCultureSource` property?
Se esta propriedade não estiver configurada, as configurações de cultura padrão do documento serão utilizadas na atualização dos campos.

### É possível atualizar campos com base na cultura do documento em vez do código do campo?
 Sim, você pode definir`FieldUpdateCultureSource` para`FieldUpdateCultureSource.Document` para usar as configurações de cultura do documento.

### Como formato datas em um padrão diferente?
 Você pode alterar o padrão de formato de data no`InsertField` método modificando o`\\@` valor de troca.