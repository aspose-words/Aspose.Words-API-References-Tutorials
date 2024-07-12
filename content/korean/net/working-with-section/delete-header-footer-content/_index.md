---
title: 머리글 바닥글 내용 삭제
linktitle: 머리글 바닥글 내용 삭제
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 머리글 및 바닥글 콘텐츠를 제거하는 방법을 알아봅니다.
type: docs
weight: 10
url: /ko/net/working-with-section/delete-header-footer-content/
---

이 튜토리얼에서는 .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서에서 머리글 및 바닥글 내용을 제거하는 방법을 보여 드리겠습니다. 머리글과 바닥글에서 콘텐츠를 제거하는 것은 문서에서 이러한 요소를 재설정하거나 제거하려는 경우 유용할 수 있습니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리
- 제거하려는 머리글과 바닥글이 포함된 Word 문서

## 1단계: 문서 디렉터리 정의
 먼저, Word 문서 위치에 대한 디렉터리 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서를 로드하고 해당 섹션으로 이동합니다.
 다음으로 Word 문서를`Document` 수업. 인덱스 0을 사용하여 문서의 첫 번째 섹션에 액세스합니다.

```csharp
// 문서를 로드하세요
Document doc = new Document(dataDir + "Document.docx");

// 섹션에 액세스
Section section = doc.Sections[0];
```

## 3단계: 머리글 및 바닥글 콘텐츠 삭제
 섹션에서 머리글과 바닥글 내용을 제거하려면 다음을 사용합니다.`ClearHeadersFooters` 방법.

```csharp
section.ClearHeadersFooters();
```

### .NET용 Aspose.Words를 사용하여 머리글 바닥글 콘텐츠 삭제를 위한 샘플 소스 코드 

```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 머리글과 바닥글 내용을 제거하는 방법을 살펴보았습니다. 머리글과 바닥글에서 콘텐츠를 제거하면 문서에서 해당 특정 요소를 재설정하거나 제거할 수 있습니다. 특정 요구 사항에 따라 이 기능을 자유롭게 사용자 정의하고 사용하세요.

### 머리글 바닥글 콘텐츠 삭제에 대한 FAQ

#### Q: .NET용 Aspose.Words에서 문서 디렉터리를 설정하는 방법은 무엇입니까?

A: 문서가 포함된 디렉터리의 경로를 설정하려면`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요. 수행 방법은 다음과 같습니다.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### Q: .NET용 Aspose.Words에서 문서 및 액세스 섹션을 로드하는 방법은 무엇입니까?

 A: Word 문서를 인스턴스로 로드하려면`Document` 클래스라는`doc` 인덱스 0을 사용하여 문서의 첫 번째 섹션에 액세스하려면 다음 코드를 사용할 수 있습니다.

```csharp
// 문서를 로드하세요
Document doc = new Document(dataDir + "Document.docx");

// 섹션에 액세스
Section section = doc.Sections[0];
```

#### Q: .NET용 Aspose.Words에서 머리글과 바닥글 내용을 제거하는 방법은 무엇입니까?

 A: 섹션에서 머리글과 바닥글 내용을 제거하려면`ClearHeadersFooters` 방법:

```csharp
section.ClearHeadersFooters();
```

#### Q: 수정된 문서를 Aspose.Words for .NET에 어떻게 저장하나요?

A: 머리글과 바닥글 내용을 삭제한 후 다음 코드를 사용하여 수정된 문서를 파일로 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```