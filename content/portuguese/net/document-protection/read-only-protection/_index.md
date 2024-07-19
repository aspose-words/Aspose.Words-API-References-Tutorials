---
title: Proteção somente leitura em documento do Word
linktitle: Proteção somente leitura em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como proteger seus documentos do Word aplicando proteção somente leitura usando Aspose.Words for .NET. Siga nosso guia passo a passo.
type: docs
weight: 10
url: /pt/net/document-protection/read-only-protection/
---
## Introdução

Quando se trata de gerenciar documentos do Word, há momentos em que você precisa torná-los somente leitura para proteger seu conteúdo. Seja para compartilhar informações importantes sem o risco de edições acidentais ou para garantir a integridade de documentos legais, a proteção somente leitura é um recurso valioso. Neste tutorial, exploraremos como implementar a proteção somente leitura em um documento do Word usando Aspose.Words for .NET. Orientaremos você em cada etapa de maneira detalhada e envolvente, garantindo que você possa acompanhar facilmente.

## Pré-requisitos

Antes de mergulharmos no código, existem alguns pré-requisitos que você precisa ter em vigor:

1.  Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words for .NET instalada. Você pode baixá-lo no[Página de lançamentos do Aspose](https://releases.aspose.com/words/net/).
2. Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento com .NET instalado. Visual Studio é uma boa escolha.
3. Compreensão básica de C#: Este tutorial pressupõe que você tenha um conhecimento básico de programação C#.

## Importar namespaces

Primeiro, vamos ter certeza de que importamos os namespaces necessários. Isso é crucial porque nos permite acessar as classes e métodos que precisamos do Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: configurar o documento

Nesta etapa, criaremos um novo documento e um construtor de documentos. Isso constitui a base de nossas operações.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Escreva algum texto no documento.
builder.Write("Open document as read-only");
```

Explicação:

- Começamos definindo o caminho do diretório onde o documento será salvo.
-  Um novo`Document` objeto é criado e um`DocumentBuilder` está associado a ele.
- Usando o construtor, adicionamos uma linha simples de texto ao documento.

## Etapa 2: definir a senha de proteção contra gravação

Em seguida, precisamos definir uma senha para proteção contra gravação. Essa senha pode ter até 15 caracteres.

```csharp
//Digite uma senha com até 15 caracteres.
doc.WriteProtection.SetPassword("MyPassword");
```

Explicação:

-  O`SetPassword` método é chamado no`WriteProtection` propriedade do documento.
- Fornecemos uma senha ("MyPassword" neste caso) que será necessária para remover a proteção.

## Etapa 3: ativar a recomendação somente leitura

Nesta etapa, tornamos o documento recomendado somente leitura. Isso significa que quando o documento for aberto, o usuário solicitará que o abra no modo somente leitura.

```csharp
// Faça o documento como recomendado somente leitura.
doc.WriteProtection.ReadOnlyRecommended = true;
```

Explicação:

-  O`ReadOnlyRecommended` propriedade está definida como`true`.
- Isso solicitará que os usuários abram o documento no modo somente leitura, embora possam optar por ignorar a recomendação.

## Etapa 4: aplicar proteção somente leitura

Finalmente, aplicamos a proteção somente leitura ao documento. Esta etapa reforça a proteção.

```csharp
// Aplique proteção contra gravação como somente leitura.
doc.Protect(ProtectionType.ReadOnly);
```

Explicação:

-  O`Protect` método é chamado no documento com`ProtectionType.ReadOnly` como o argumento.
- Este método reforça a proteção somente leitura, evitando qualquer modificação no documento sem a senha.

## Etapa 5: salve o documento

última etapa é salvar o documento com as configurações de proteção aplicadas.

```csharp
// Salve o documento protegido.
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Explicação:

-  O`Save` O método é chamado no documento, especificando o caminho e o nome do arquivo.
- O documento é salvo com a proteção somente leitura ativada.

## Conclusão

E aí está! Você criou com sucesso um documento do Word protegido somente leitura usando Aspose.Words for .NET. Este recurso garante que o conteúdo do seu documento permaneça intacto e inalterado, proporcionando uma camada extra de segurança. Esteja você compartilhando informações confidenciais ou documentos legais, a proteção somente leitura é uma ferramenta indispensável em seu arsenal de gerenciamento de documentos.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, modificar, converter e proteger documentos do Word programaticamente usando C# ou outras linguagens .NET.

### Posso remover a proteção somente leitura de um documento?
 Sim, você pode remover a proteção somente leitura usando o`Unprotect` método e fornecendo a senha correta.

### senha definida no documento está criptografada?
Sim, Aspose.Words criptografa a senha para garantir a segurança do documento protegido.

### Posso aplicar outros tipos de proteção usando Aspose.Words for .NET?
Sim, Aspose.Words for .NET oferece suporte a vários tipos de proteção, incluindo permitir apenas comentários, preencher formulários ou rastrear alterações.

### Existe um teste gratuito disponível para Aspose.Words for .NET?
 Sim, você pode baixar uma versão de avaliação gratuita no site[Página de lançamentos do Aspose](https://releases.aspose.com/).