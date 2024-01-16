---
title: Proteção somente leitura em documento do Word
linktitle: Proteção somente leitura em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como proteger seus documentos somente leitura no Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/document-protection/read-only-protection/
---
Neste tutorial, iremos guiá-lo através das etapas para usar o recurso de proteção somente leitura do Aspose.Words for .NET. Este recurso permite que você torne um documento do Word somente leitura para evitar modificações não autorizadas. Siga os passos abaixo:

## Etapa 1: Criando o Documento e Aplicando Proteção

Comece criando uma instância da classe Document e um objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: Escreva o conteúdo no documento
Use o objeto DocumentBuilder para gravar conteúdo no documento:

```csharp
builder.Write("Open document as read-only");
```

## Etapa 3: definir a senha e tornar o documento somente leitura

Defina uma senha para o documento usando a propriedade SetPassword() do objeto WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Certifique-se de substituir “MyPassword” pela senha real que deseja usar.

## Etapa 4: aplicar documento somente leitura

Torne o documento somente leitura definindo a propriedade ReadOnlyRecommended como true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Etapa 5: aplique proteção somente leitura e salve o documento

Finalmente, aplique proteção somente leitura usando o método Protect() do objeto Document:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para salvar o documento protegido.

### Exemplo de código-fonte para proteção somente leitura usando Aspose.Words for .NET

Aqui está o código-fonte completo para proteção somente leitura usando Aspose.Words for .NET:

```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Digite uma senha com até 15 caracteres.
doc.WriteProtection.SetPassword("MyPassword");

// Torne o documento somente leitura.
doc.WriteProtection.ReadOnlyRecommended = true;

// Aplique proteção contra gravação como somente leitura.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Seguindo estas etapas, você pode proteger facilmente seus documentos

## Conclusão

Neste tutorial, exploramos o recurso de proteção somente leitura do Aspose.Words for .NET, que permite tornar documentos do Word somente leitura para evitar modificações não autorizadas. Seguindo as etapas fornecidas, você pode aplicar facilmente proteção somente leitura aos seus documentos e aumentar sua segurança. A proteção somente leitura ajuda a garantir a integridade e a precisão do conteúdo do seu documento, restringindo os recursos de edição. Aspose.Words for .NET fornece uma API poderosa e flexível para lidar com a proteção de documentos e oferece suporte a vários outros recursos para personalizar e proteger seus documentos do Word.

### Perguntas frequentes sobre proteção somente leitura em documentos do Word

#### P: O que é proteção somente leitura no Aspose.Words for .NET?

R: A proteção somente leitura no Aspose.Words for .NET é um recurso que permite tornar um documento do Word somente leitura, evitando modificações não autorizadas. Quando um documento é definido como somente leitura, os usuários podem abrir e visualizar o documento, mas não podem fazer alterações em seu conteúdo.

#### P: Como posso aplicar proteção somente leitura a um documento do Word usando Aspose.Words for .NET?

R: Para aplicar proteção somente leitura a um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Crie uma instância do`Document` aula e um`DocumentBuilder` objeto.
2.  Use o`DocumentBuilder` para escrever conteúdo no documento.
3.  Defina uma senha para o documento usando o`SetPassword` método do`WriteProtection` objeto.
4.  Colocou o`ReadOnlyRecommended` propriedade do`WriteProtection` opor-se a`true` para recomendar a abertura do documento como somente leitura.
5.  Aplique proteção somente leitura usando o`Protect` método do`Document` objeto, especificando o`ProtectionType` como`ReadOnly`.
6.  Salve o documento protegido usando o`Save` método do`Document` objeto.

#### P: Posso remover a proteção somente leitura de um documento do Word usando Aspose.Words for .NET?

R: Sim, você pode remover a proteção somente leitura de um documento do Word usando Aspose.Words for .NET. Para fazer isso, você pode usar o`Unprotect` método do`Document` class, que remove qualquer proteção existente do documento.

#### P: Posso definir uma senha diferente para proteção somente leitura em um documento do Word?

 R: Não, a proteção somente leitura no Aspose.Words for .NET não permite que você defina uma senha separada especificamente para proteção somente leitura. A senha definida usando o`SetPassword` método do`WriteProtection` O objeto se aplica à proteção geral do documento, incluindo proteção somente leitura e leitura-gravação.

#### P: Os usuários podem ignorar a proteção somente leitura em um documento do Word?

R: A proteção somente leitura em um documento do Word tem como objetivo desencorajar e impedir modificações acidentais ou não autorizadas. Embora forneça um nível de proteção, pode ser contornado por usuários com conhecimento técnico suficiente ou permissões de edição. No entanto, a proteção somente leitura serve como impedimento e ajuda a manter a integridade do documento.