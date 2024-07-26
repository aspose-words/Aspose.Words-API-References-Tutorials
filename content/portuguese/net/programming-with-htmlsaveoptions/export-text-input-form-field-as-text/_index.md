---
title: Exportar campo de formulário de entrada de texto como texto
linktitle: Exportar campo de formulário de entrada de texto como texto
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como exportar campos de formulário de entrada de texto como texto simples usando Aspose.Words for .NET com este guia passo a passo abrangente.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## Introdução

Então, você está mergulhando no mundo do Aspose.Words for .NET? Escolha incrível! Se você deseja aprender como exportar um campo de formulário de entrada de texto como texto, você está no lugar certo. Esteja você apenas começando ou aprimorando suas habilidades, este guia irá orientá-lo em tudo o que você precisa saber. Vamos começar, certo?

## Pré-requisitos

Antes de mergulharmos no âmago da questão, vamos ter certeza de que você tem tudo o que precisa para seguir em frente sem problemas:

-  Aspose.Words for .NET: Baixe e instale a versão mais recente em[aqui](https://releases.aspose.com/words/net/).
- IDE: Visual Studio ou qualquer ambiente de desenvolvimento C#.
- Conhecimento básico de C#: compreensão da sintaxe básica de C# e conceitos de programação orientada a objetos.
- Documento: um exemplo de documento do Word (`Rendering.docx`) com campos de formulário de entrada de texto.

## Importar namespaces

Em primeiro lugar, você precisa importar os namespaces necessários. Eles são como os blocos de construção que fazem tudo funcionar perfeitamente.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

Tudo bem, agora que temos nossos namespaces prontos, vamos entrar em ação!

## Etapa 1: configurar o projeto

Antes de entrarmos no código, vamos ter certeza de que nosso projeto está configurado corretamente.

## Criando o Projeto

1. Abra o Visual Studio: comece abrindo o Visual Studio ou seu ambiente de desenvolvimento C# preferido.
2.  Crie um novo projeto: navegue até`File > New > Project` . Selecione`Console App (.NET Core)` ou qualquer outro tipo de projeto relevante.
3.  Nomeie seu projeto: dê ao seu projeto um nome significativo, algo como`AsposeWordsExportExample`.

## Adicionando Aspose.Words

1.  Gerenciar pacotes NuGet: clique com o botão direito em seu projeto no Solution Explorer e selecione`Manage NuGet Packages`.
2.  Pesquise Aspose.Words: No Gerenciador de Pacotes NuGet, pesquise`Aspose.Words`.
3.  Instale Aspose.Words: Clique em`Install` para adicionar a biblioteca Aspose.Words ao seu projeto.

## Etapa 2: carregue o documento do Word

Agora que nosso projeto está configurado, vamos carregar o documento Word que contém os campos do formulário de entrada de texto.

1. Especifique o diretório do documento: Defina o caminho para o diretório onde seu documento está armazenado.
2.  Carregue o documento: use o`Document` class para carregar seu documento do Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: preparar o diretório de exportação

Antes de exportarmos, vamos garantir que nosso diretório de exportação esteja pronto. É aqui que nosso arquivo HTML e imagens serão salvos.

1. Defina o Diretório de Exportação: Especifique o caminho onde os arquivos exportados serão salvos.
2. Verifique e limpe o diretório: certifique-se de que o diretório exista e esteja vazio.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## Etapa 4: configurar opções de salvamento

É aqui que a mágica acontece. Precisamos configurar nossas opções de salvamento para exportar o campo do formulário de entrada de texto como texto simples.

1.  Criar opções de salvamento: Inicialize um novo`HtmlSaveOptions` objeto.
2.  Definir opção de exportação de texto: configure o`ExportTextInputFormFieldAsText`propriedade para`true`.
3. Definir Pasta de Imagens: Defina a pasta onde as imagens serão salvas.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## Etapa 5: salve o documento como HTML

Finalmente, vamos salvar o documento do Word como um arquivo HTML usando nossas opções de salvamento configuradas.

1. Defina o Caminho de Saída: Especifique o caminho onde o arquivo HTML será salvo.
2.  Salve o documento: use o`Save` método do`Document`classe para exportar o documento.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## Conclusão

E aí está! Você exportou com sucesso um campo de formulário de entrada de texto como texto simples usando Aspose.Words for .NET. Este guia deveria ter fornecido uma abordagem clara e passo a passo para realizar essa tarefa. Lembre-se de que a prática leva à perfeição, então continue experimentando diferentes opções e configurações para ver o que mais você pode fazer com o Aspose.Words.

## Perguntas frequentes

### Posso exportar outros tipos de campos de formulário usando o mesmo método?

 Sim, você pode exportar outros tipos de campos de formulário configurando diferentes propriedades do`HtmlSaveOptions` aula.

### E se meu documento tiver imagens?

 As imagens serão salvas na pasta de imagens especificada. Certifique-se de definir o`ImagesFolder` propriedade no`HtmlSaveOptions`.

### Preciso de uma licença para Aspose.Words?

 Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/) ou compre uma licença[aqui](https://purchase.aspose.com/buy).

### Posso personalizar o HTML exportado?

 Absolutamente! Aspose.Words oferece várias opções para personalizar a saída HTML. Consulte o[documentação](https://reference.aspose.com/words/net/) para mais detalhes.

### O Aspose.Words é compatível com o .NET Core?

Sim, Aspose.Words é compatível com .NET Core, .NET Framework e outras plataformas .NET.
