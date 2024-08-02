---
title: Inserir campo TOA sem Document Builder
linktitle: Inserir campo TOA sem Document Builder
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um campo TOA sem usar um construtor de documentos no Aspose.Words for .NET. Siga nosso guia passo a passo para gerenciar com eficiência citações legais.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-toafield-without-document-builder/
---
## Introdução

Criar um campo Tabela de Autoridades (TOA) em um documento do Word pode parecer como montar um quebra-cabeça complexo. No entanto, com a ajuda do Aspose.Words for .NET, o processo se torna tranquilo e direto. Neste artigo, orientaremos você nas etapas para inserir um campo TOA sem usar um construtor de documentos, facilitando o gerenciamento de suas citações e referências legais em seus documentos do Word.

## Pré-requisitos

Antes de mergulhar no tutorial, vamos abordar o essencial de que você precisa:

-  Aspose.Words for .NET: Certifique-se de ter a versão mais recente instalada. Você pode baixá-lo no[Aspor site](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: um IDE compatível com .NET como o Visual Studio.
- Conhecimento básico de C#: Compreender a sintaxe e os conceitos básicos de C# será útil.
- Exemplo de documento do Word: Crie ou tenha um documento de amostra pronto onde deseja inserir o campo TOA.

## Importar namespaces

Para começar, você precisará importar os namespaces necessários da biblioteca Aspose.Words. Esta configuração garante que você tenha acesso a todas as classes e métodos necessários para manipulação de documentos.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Vamos dividir o processo em etapas simples e fáceis de seguir. Orientaremos você em cada etapa, explicando o que cada trecho de código faz e como ele contribui para a criação do campo TOA.

## Etapa 1: inicializar o documento

 Primeiro, você precisa criar uma instância do`Document` aula. Este objeto representa o documento do Word em que você está trabalhando.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

Este código inicializa um novo documento do Word. Você pode pensar nisso como a criação de uma tela em branco à qual adicionará seu conteúdo.

## Etapa 2: Criar e configurar o campo TA

A seguir, adicionaremos um campo TA (Tabela de Autoridades). Este campo marca as entradas que aparecerão no TOA.

```csharp
Paragraph para = new Paragraph(doc);

// Queremos inserir campos TA e TOA assim:
// { TA \c 1 \l "Valor 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

Aqui está um detalhamento:
- Parágrafo para = novo Parágrafo(doc);: Cria um novo parágrafo dentro do documento.
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);: Adiciona um campo TA ao parágrafo. O`FieldType.FieldTOAEntry` especifica que este é um campo de entrada do TOA.
- fieldTA.EntryCategory = "1";: Define a categoria de entrada. Isto é útil para categorizar diferentes tipos de entradas.
- fieldTA.LongCitation = "Value 0";: Especifica o texto longo da citação. Este é o texto que aparecerá no TOA.
- doc.FirstSection.Body.AppendChild(para);: Acrescenta o parágrafo com o campo TA ao corpo do documento.

## Etapa 3: adicione o campo TOA

Agora, inseriremos o campo TOA real que compila todas as entradas do TA em uma tabela.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

Nesta etapa:
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);: Adiciona um campo TOA ao parágrafo.
- fieldToa.EntryCategory = "1";: Filtra as entradas para incluir apenas aquelas marcadas com categoria "1".

## Etapa 4: atualize o campo TOA

Após inserir o campo TOA, você precisa atualizá-lo para garantir que ele reflita as entradas mais recentes.

```csharp
fieldToa.Update();
```

Este comando atualiza o campo TOA, garantindo que todas as entradas marcadas sejam exibidas corretamente na tabela.

## Etapa 5: salve o documento

Por fim, salve seu documento com o campo TOA recém-adicionado.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 Esta linha de código salva o documento no diretório especificado. Certifique-se de substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde você deseja salvar seu arquivo.

## Conclusão

E aí está! Você adicionou com êxito um campo TOA a um documento do Word sem usar um construtor de documentos. Seguindo essas etapas, você pode gerenciar citações com eficiência e criar tabelas de autoridades abrangentes em seus documentos legais. Aspose.Words for .NET torna esse processo tranquilo e eficiente, fornecendo as ferramentas para lidar com tarefas complexas de documentos com facilidade.

## Perguntas frequentes

### Posso adicionar vários campos TA com categorias diferentes?
 Sim, você pode adicionar vários campos TA com categorias diferentes definindo o`EntryCategory`propriedade em conformidade.

### Como posso personalizar a aparência do TOA?
Você pode personalizar a aparência do TOA modificando as propriedades do campo TOA, como formatação de entrada e rótulos de categoria.

### É possível atualizar o campo TOA automaticamente?
 Embora você possa atualizar manualmente o campo TOA usando o`Update` método, Aspose.Words atualmente não oferece suporte a atualizações automáticas em alterações de documentos.

### Posso adicionar campos TA programaticamente em partes específicas do documento?
Sim, você pode adicionar campos TA em locais específicos, inserindo-os nos parágrafos ou seções desejadas.

### Como lidar com vários campos TOA em um único documento?
 Você pode gerenciar vários campos TOA atribuindo diferentes`EntryCategory` valores e garantindo que cada campo TOA filtre as entradas com base em sua categoria.