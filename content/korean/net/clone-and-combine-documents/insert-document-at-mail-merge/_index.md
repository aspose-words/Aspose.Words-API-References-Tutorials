---
title: 편지 병합 시 문서 삽입
linktitle: 편지 병합 시 문서 삽입
second_title: Aspose.Words 문서 처리 API
description: 이 포괄적인 단계별 튜토리얼에서 .NET용 Aspose.Words를 사용하여 메일 병합 필드에 문서를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## 소개

.NET용 Aspose.Words를 사용하여 문서 자동화의 세계에 오신 것을 환영합니다! 메일 병합 작업 중에 기본 문서 내의 특정 필드에 문서를 동적으로 삽입하는 방법에 대해 궁금한 적이 있습니까? 글쎄, 당신은 바로 이곳에 있습니다. 이 튜토리얼은 Aspose.Words for .NET을 사용하여 편지 병합 필드에 문서를 삽입하는 과정을 단계별로 안내합니다. 이는 각 조각이 완벽하게 제자리에 맞춰져 있는 퍼즐을 맞추는 것과 같습니다. 그럼, 뛰어 들어 봅시다!

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1.  .NET용 Aspose.Words: 다음을 수행할 수 있습니다.[여기서 최신 버전을 다운로드하세요](https://releases.aspose.com/words/net/) . 라이센스를 구매해야 하는 경우 그렇게 할 수 있습니다.[여기](https://purchase.aspose.com/buy) . 또는[임시 면허증](https://purchase.aspose.com/temporary-license/) 아니면[무료 시험판](https://releases.aspose.com/).
2. 개발 환경: Visual Studio 또는 기타 C# IDE.
3. C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 이 튜토리얼을 쉽게 만들 수 있습니다.

## 네임스페이스 가져오기

먼저, 필요한 네임스페이스를 가져와야 합니다. 이는 프로젝트의 구성 요소와 같습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

프로세스를 관리 가능한 단계로 나누어 보겠습니다. 각 단계는 이전 단계를 기반으로 구축되어 완벽한 솔루션으로 이어집니다.

## 1단계: 디렉터리 설정

문서 삽입을 시작하기 전에 문서 디렉터리 경로를 정의해야 합니다. 여기에 귀하의 문서가 저장됩니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 주 문서 로드

다음으로 기본 문서를 로드합니다. 이 문서에는 다른 문서가 삽입될 병합 필드가 포함되어 있습니다.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## 3단계: 필드 병합 콜백 설정

병합 프로세스를 처리하려면 콜백 함수를 설정해야 합니다. 이 함수는 지정된 병합 필드에 문서를 삽입하는 역할을 합니다.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## 4단계: 메일 병합 실행

이제 메일 병합을 실행할 차례입니다. 이것이 바로 마법이 일어나는 곳입니다. 병합 필드와 이 필드에 삽입되어야 하는 문서를 지정합니다.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## 5단계: 문서 저장

편지 병합이 완료되면 수정된 문서를 저장하게 됩니다. 이 새 문서에는 원하는 위치에 콘텐츠가 바로 삽입됩니다.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## 6단계: 콜백 핸들러 생성

콜백 핸들러는 병합 필드에 대한 특별한 처리를 수행하는 클래스입니다. 필드 값에 지정된 문서를 로드하고 현재 병합 필드에 삽입합니다.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## 7단계: 문서 삽입

이 메서드는 지정된 문서를 현재 단락이나 표 셀에 삽입합니다.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 메일 병합 작업 중에 특정 필드에 문서를 성공적으로 삽입했습니다. 이 강력한 기능을 사용하면 특히 대용량 문서를 처리할 때 많은 시간과 노력을 절약할 수 있습니다. 당신을 위해 모든 무거운 짐을 들어주는 개인 비서가 있다고 생각하십시오. 그러니 한번 시도해 보십시오. 즐거운 코딩하세요!

## FAQ

### 서로 다른 병합 필드에 여러 문서를 삽입할 수 있나요?
 그래 넌 할수있어. 적절한 병합 필드와 해당 문서 경로를 지정하기만 하면 됩니다.`MailMerge.Execute` 방법.

### 삽입된 문서를 기본 문서와 다르게 포맷할 수 있나요?
 전적으로! 당신은 사용할 수 있습니다`ImportFormatMode` 매개변수`NodeImporter` 서식을 제어합니다.

### 병합 필드 이름이 동적이면 어떻게 되나요?
동적 병합 필드 이름을 콜백 핸들러에 매개변수로 전달하여 처리할 수 있습니다.

### 다른 파일 형식에 이 방법을 사용할 수 있나요?
예, Aspose.Words는 DOCX, PDF 등을 포함한 다양한 파일 형식을 지원합니다.

### 문서 삽입 과정에서 발생하는 오류는 어떻게 처리하나요?
발생할 수 있는 예외를 관리하려면 콜백 핸들러에서 오류 처리를 구현하세요.