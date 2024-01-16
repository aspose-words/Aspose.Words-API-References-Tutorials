---
title: Remover restrição somente leitura
linktitle: Remover restrição somente leitura
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como remover a restrição somente leitura de um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/document-protection/remove-read-only-restriction/
---
Neste tutorial, orientaremos você nas etapas para usar o recurso de remoção de restrição somente leitura do Aspose.Words for .NET. Este recurso permite remover a restrição somente leitura de um documento do Word para torná-lo editável. Siga os passos abaixo:

## Passo 1: Criando o Documento e Configurando a Proteção

Comece criando uma instância da classe Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Defina uma senha para o documento usando a propriedade SetPassword() do objeto WriteProtection:

Certifique-se de substituir “MyPassword” pela senha real que você usou para proteger o documento.

## Etapa 2: remover a restrição somente leitura

Para remover a restrição somente leitura, defina a propriedade ReadOnlyRecommended como false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Etapa 3: aplicar proteção irrestrita

Finalmente, aplique proteção irrestrita usando o método Protect() do objeto Document:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para salvar o documento sem a restrição somente leitura.

### Exemplo de código-fonte para remover restrição somente leitura usando Aspose.Words for .NET

Aqui está o código-fonte completo para remover a restrição somente leitura usando Aspose.Words for .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Digite uma senha com até 15 caracteres.
doc.WriteProtection.SetPassword("MyPassword");

//Remova a opção somente leitura.
doc.WriteProtection.ReadOnlyRecommended = false;

// Aplique proteção contra gravação sem qualquer proteção.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Seguindo essas etapas, você pode remover facilmente a restrição somente leitura de um documento do Word com Aspose.Words for .NET.


## Conclusão

Neste tutorial, aprendemos como remover a restrição somente leitura de um documento do Word usando Aspose.Words for .NET. Seguindo as etapas fornecidas, você pode remover facilmente a restrição e tornar o documento editável novamente. Aspose.Words for .NET oferece um conjunto abrangente de recursos para gerenciar proteção e restrições de documentos, proporcionando flexibilidade e controle sobre os recursos de segurança e edição de seus documentos Word.

### Perguntas frequentes

#### P: Qual é a restrição somente leitura no Aspose.Words for .NET?

R: A restrição somente leitura no Aspose.Words for .NET refere-se a um recurso que permite definir um documento do Word como somente leitura, evitando que os usuários façam quaisquer modificações no conteúdo ou na formatação. Essa restrição ajuda a proteger a integridade do documento e garante que ele não seja modificado de forma acidental ou maliciosa.

#### P: Como posso remover a restrição somente leitura usando Aspose.Words for .NET?

R: Para remover a restrição somente leitura de um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Crie uma instância do`Document` class e defina uma senha para o documento usando o`SetPassword` método do`WriteProtection` objeto.
2.  Colocou o`ReadOnlyRecommended` propriedade do`WriteProtection` opor-se a`false` para remover a recomendação somente leitura.
3.  Aplique proteção irrestrita ao documento usando o`Protect` método do`Document` objeto com o`NoProtection` tipo de proteção.
4.  Salve o documento sem a restrição somente leitura usando o`Save` método do`Document` objeto.

#### P: Posso remover a restrição somente leitura de um documento do Word sem senha?

R: Não, você não pode remover a restrição somente leitura de um documento do Word sem fornecer a senha correta. A restrição somente leitura é definida por motivos de segurança e removê-la sem a senha prejudicaria o propósito de proteger a integridade do documento.

#### P: Posso remover a restrição somente leitura de um documento do Word com a senha errada?

R: Não, você não pode remover a restrição somente leitura de um documento do Word com a senha errada. A senha correta deve ser fornecida para remover a restrição somente leitura e tornar o documento editável novamente. Isto garante que apenas usuários autorizados com a senha correta possam modificar o documento.

#### P: É possível remover outros tipos de proteção de documentos usando Aspose.Words for .NET?

R: Sim, Aspose.Words for .NET fornece vários métodos para remover outros tipos de proteção de documentos, como proteção por senha, proteção de formulário ou restrições de edição de documentos. Dependendo do tipo de proteção aplicada ao documento, você pode usar os métodos e propriedades correspondentes fornecidos pelo Aspose.Words para remover a proteção específica e tornar o documento editável.
