---
title: Word 문서 병합
linktitle: 문서 병합
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 여러 Word 문서를 병합하는 방법을 알아보세요. 이 강력한 API는 문서 병합 프로세스를 단순화하여 효율적이고 간단하게 만듭니다.
type: docs
weight: 10
url: /ko/net/split-document/merge-documents/
---

이 튜토리얼에서는 Aspose.Words for .NET의 문서 병합 기능을 사용하여 여러 Word 문서를 병합하는 방법을 안내합니다. 소스 코드를 이해하고 모든 소스 문서가 포함된 병합 문서를 얻으려면 아래 단계를 따르세요.

## 1단계: 병합할 문서 검색

문서를 병합하기 전에 병합할 원본 문서를 찾아야 합니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// 병합할 문서를 검색합니다.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## 2단계: 문서 병합

이제 문서를 하나씩 병합하여 최종 병합 문서를 만듭니다. 방법은 다음과 같습니다.

```csharp
// 결과 문서의 첫 번째 부분을 엽니다.
Document sourceDoc = new Document(sourceDocumentPath);

// 새 결과 문서를 만듭니다.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// 문서를 하나씩 병합하세요.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### .NET용 Aspose.Words를 사용하여 문서 병합을 위한 예제 소스 코드

다음은 .NET용 Aspose.Words의 문서 병합 기능에 대한 전체 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 병합에 사용되는 문서를 찾습니다.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// 결과 문서의 첫 번째 부분을 엽니다.
Document sourceDoc = new Document(sourceDocumentPath);

// 새 결과 문서를 만듭니다.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// 문서 부분을 하나씩 병합합니다.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## 결론

축하해요! Aspose.Words for .NET의 문서 병합 기능을 사용하여 여러 Word 문서를 병합하는 방법을 배웠습니다. 제공된 소스 코드를 따르면 각 소스 문서의 서식을 유지하면서 별도의 문서를 하나의 병합 문서로 결합할 수 있습니다.

문서 병합은 여러 소스의 정보를 통합하거나 개별 부분에서 통합 문서를 만들 때 유용할 수 있습니다. Aspose.Words for .NET은 문서 병합 프로세스를 단순화하여 효율적이고 간단하게 만드는 강력한 API를 제공합니다.

문서 처리 기능을 향상하고 작업 흐름을 간소화하기 위해 Aspose.Words for .NET에서 제공하는 다른 기능을 자유롭게 탐색해 보세요.

### 자주 묻는 질문

#### 서식이 다른 문서를 어떻게 병합할 수 있나요?

 문서를 병합할 때 Aspose.Words for .NET은 각 소스 문서의 서식을 유지하는 옵션을 제공합니다. 을 사용하여`ImportFormatMode.KeepSourceFormatting` 옵션을 선택하면 병합된 문서는 원본 문서의 형식을 유지합니다. 병합된 문서 전체에 일관된 서식을 적용하려면 문서를 병합한 후 Aspose.Words API를 사용하여 서식을 수정할 수 있습니다.

#### 다른 형식의 문서를 병합할 수 있나요?

예, Aspose.Words for .NET은 DOCX, DOC, RTF 등을 포함한 다양한 형식의 문서 병합을 지원합니다. 다양한 형식의 문서를 Aspose.Words API에 로드하고 원래 형식에 관계없이 단일 문서로 병합할 수 있습니다.

#### 표, 이미지 등 복잡한 구조의 문서를 병합할 수 있나요?

전적으로! Aspose.Words for .NET은 표, 이미지, 머리글, 바닥글 등을 포함한 복잡한 구조의 문서를 병합할 수 있습니다. API는 각 문서 콘텐츠의 무결성과 레이아웃을 유지하면서 병합 프로세스를 처리합니다.

#### 페이지 방향이나 크기가 다른 문서를 병합할 수 있습니까?

예, Aspose.Words for .NET은 병합 프로세스 중에 페이지 방향이나 크기가 다른 문서를 처리합니다. 결과로 병합된 문서는 원본 문서의 다양한 페이지 방향과 크기를 수용합니다.