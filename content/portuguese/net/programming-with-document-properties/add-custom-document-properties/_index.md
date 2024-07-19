---
title: Adicionar propriedades personalizadas do documento
linktitle: Adicionar propriedades personalizadas do documento
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar propriedades personalizadas de documentos em arquivos do Word usando Aspose.Words for .NET. Siga nosso guia passo a passo para aprimorar seus documentos com metadados adicionais.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/add-custom-document-properties/
---
## Introdução

Ei! Você está mergulhando no mundo do Aspose.Words for .NET e se perguntando como adicionar propriedades personalizadas de documentos aos seus arquivos do Word? Bem, você veio ao lugar certo! As propriedades personalizadas podem ser extremamente úteis para armazenar metadados adicionais que não são cobertos pelas propriedades integradas. Seja autorizando um documento, adicionando um número de revisão ou até mesmo inserindo datas específicas, as propriedades personalizadas ajudam você. Neste tutorial, orientaremos você nas etapas para adicionar essas propriedades perfeitamente usando Aspose.Words for .NET. Pronto para começar? Vamos mergulhar!

## Pré-requisitos

Antes de entrarmos no código, vamos ter certeza de que você tem tudo o que precisa:

1.  Biblioteca Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words for .NET. Você pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: um IDE como o Visual Studio.
3. Conhecimento básico de C#: Este tutorial pressupõe que você tenha um conhecimento básico de C# e .NET.
4.  Documento de amostra: tenha um documento do Word de amostra pronto, chamado`Properties.docx`, que você modificará.

## Importar namespaces

Antes de começarmos a codificar, precisamos importar os namespaces necessários. Esta é uma etapa crucial para garantir que seu código tenha acesso a todas as funcionalidades disponibilizadas pelo Aspose.Words.

```csharp
using System;
using Aspose.Words;
```

## Etapa 1: configurando o caminho do documento

 Em primeiro lugar, precisamos configurar o caminho para o nosso documento. É aqui que especificaremos a localização do nosso`Properties.docx` arquivo.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Neste trecho, substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o seu documento. Esta etapa é crucial porque permite que o programa localize e abra seu arquivo Word.

## Etapa 2: Acessando propriedades personalizadas do documento

A seguir, vamos acessar as propriedades personalizadas do documento do Word. É aqui que todos os seus metadados personalizados serão armazenados.

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
```

Ao fazer isso, conseguimos controlar a coleção de propriedades personalizadas, com a qual trabalharemos nas etapas a seguir.

## Etapa 3: verificação de propriedades existentes

Antes de adicionar novas propriedades, é uma boa ideia verificar se uma determinada propriedade já existe. Isso evita qualquer duplicação desnecessária.

```csharp
if (customDocumentProperties["Authorized"] != null) return;
```

Esta linha verifica se a propriedade “Autorizado” já existe. Se isso acontecer, o programa sairá do método antecipadamente para evitar a adição de propriedades duplicadas.

## Etapa 4: adicionar uma propriedade booleana

Agora, vamos adicionar nossa primeira propriedade personalizada – um valor booleano para indicar se o documento está autorizado.

```csharp
customDocumentProperties.Add("Authorized", true);
```

 Esta linha adiciona uma propriedade customizada chamada "Autorizado" com um valor de`true`. Simples e direto!

## Etapa 5: adicionando uma propriedade String

A seguir, adicionaremos outra propriedade personalizada para especificar quem autorizou o documento.

```csharp
customDocumentProperties.Add("Authorized By", "John Smith");
```

Aqui, estamos adicionando uma propriedade chamada “Autorizado por” com o valor “John Smith”. Sinta-se à vontade para substituir “John Smith” por qualquer outro nome de sua preferência.

## Etapa 6: adicionar uma propriedade de data

Vamos adicionar uma propriedade para armazenar a data de autorização. Isso ajuda a controlar quando o documento foi autorizado.

```csharp
customDocumentProperties.Add("Authorized Date", DateTime.Today);
```

 Este snippet adiciona uma propriedade chamada "Data Autorizada" com a data atual como valor. O`DateTime.Today`propriedade busca automaticamente a data de hoje.

## Etapa 7: adicionar um número de revisão

Também podemos adicionar uma propriedade para controlar o número de revisão do documento. Isto é particularmente útil para controle de versão.

```csharp
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
```

Aqui, estamos adicionando uma propriedade chamada “Revisão Autorizada” e atribuindo a ela o número de revisão atual do documento.

## Etapa 8: Adicionar uma propriedade numérica

Por último, vamos adicionar uma propriedade numérica para armazenar uma quantia autorizada. Pode ser qualquer coisa, desde um valor orçamentário até um valor de transação.

```csharp
customDocumentProperties.Add("Authorized Amount", 123.45);
```

 Esta linha adiciona uma propriedade chamada "Valor Autorizado" com um valor de`123.45`. Novamente, sinta-se à vontade para substituí-lo por qualquer número que atenda às suas necessidades.

## Conclusão

aí está! Você adicionou com êxito propriedades de documento personalizadas a um documento do Word usando Aspose.Words for .NET. Essas propriedades podem ser extremamente úteis para armazenar metadados adicionais específicos às suas necessidades. Esteja você rastreando detalhes de autorização, números de revisão ou valores específicos, as propriedades personalizadas fornecem uma solução flexível.

Lembre-se de que a chave para dominar o Aspose.Words for .NET é a prática. Portanto, continue experimentando diferentes propriedades e veja como elas podem aprimorar seus documentos. Boa codificação!

## Perguntas frequentes

### O que são propriedades personalizadas de documentos?
As propriedades personalizadas do documento são metadados que você pode adicionar a um documento do Word para armazenar informações adicionais que não são cobertas pelas propriedades internas.

### Posso adicionar outras propriedades além de strings e números?
Sim, você pode adicionar vários tipos de propriedades, incluindo objetos booleanos, de data e até objetos personalizados.

### Como posso acessar essas propriedades em um documento do Word?
As propriedades personalizadas podem ser acessadas programaticamente usando Aspose.Words ou visualizadas diretamente no Word por meio das propriedades do documento.

### É possível editar ou excluir propriedades personalizadas?
Sim, você pode editar ou excluir facilmente propriedades personalizadas usando métodos semelhantes fornecidos por Aspose.Words.

### As propriedades personalizadas podem ser usadas para filtrar documentos?
Absolutamente! As propriedades personalizadas são excelentes para categorizar e filtrar documentos com base em metadados específicos.
