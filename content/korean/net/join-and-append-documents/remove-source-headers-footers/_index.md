---
title: 소스 헤더 바닥글 제거
linktitle: 소스 헤더 바닥글 제거
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 머리글과 바닥글을 제거하는 방법을 알아보세요. 단계별 가이드를 통해 문서 관리를 단순화하세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/remove-source-headers-footers/
---
## 소개

이 포괄적인 가이드에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 머리글과 바닥글을 효과적으로 제거하는 방법을 자세히 살펴보겠습니다. 머리글과 바닥글은 일반적으로 Word 문서의 페이지 번호 매기기, 문서 제목 또는 기타 반복되는 내용에 사용됩니다. 문서를 병합하든 서식을 정리하든 이 프로세스를 익히면 문서 관리 작업을 간소화할 수 있습니다. .NET용 Aspose.Words를 사용하여 이를 달성하는 단계별 프로세스를 살펴보겠습니다.

## 전제조건

튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.

1. 개발 환경: Visual Studio 또는 기타 .NET 개발 환경이 설치되어 있습니다.
2.  .NET용 Aspose.Words: .NET용 Aspose.Words를 다운로드하여 설치했는지 확인하세요. 그렇지 않다면, 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/words/net/).
3. 기본 지식: C# 프로그래밍 및 .NET 프레임워크 기본 사항에 대한 지식.

## 네임스페이스 가져오기

코딩을 시작하기 전에 C# 파일에서 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Words;
```

## 1단계: 원본 문서 로드

먼저 머리글과 바닥글을 제거하려는 소스 문서를 로드해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 소스 문서가 있는 문서 디렉터리의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## 2단계: 대상 문서 만들기 또는 로드

 수정된 콘텐츠를 배치할 대상 문서를 아직 만들지 않은 경우 새 문서를 만들 수 있습니다.`Document` 반대하거나 기존 항목을 로드합니다.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3단계: 섹션에서 머리글 및 바닥글 지우기

소스 문서의 각 섹션을 반복합니다(`srcDoc`) 머리글과 바닥글을 지웁니다.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## 4단계: LinkToPrevious 설정 관리

대상 문서에서 머리글과 바닥글이 계속되는 것을 방지하려면(`dstDoc` ),`LinkToPrevious` 머리글 및 바닥글 설정이 다음으로 설정되어 있습니다.`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## 5단계: 수정된 문서를 대상 문서에 추가

마지막으로 소스 문서에서 수정된 내용을 추가합니다(`srcDoc`)을 대상 문서(`dstDoc`) 소스 형식을 유지하면서.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6단계: 결과 문서 저장

머리글과 바닥글이 제거된 최종 문서를 지정된 디렉터리에 저장합니다.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

## 결론

Aspose.Words for .NET을 사용하여 Word 문서에서 머리글과 바닥글을 제거하는 것은 문서 관리 작업을 크게 향상시킬 수 있는 간단한 프로세스입니다. 위에 설명된 단계를 따르면 세련되고 전문적인 모습을 위해 문서를 효율적으로 정리할 수 있습니다.

## FAQ

### 특정 섹션에서만 머리글과 바닥글을 제거할 수 있나요?
예, 필요에 따라 섹션을 반복하고 선택적으로 머리글과 바닥글을 지울 수 있습니다.

### .NET용 Aspose.Words는 여러 문서에서 머리글과 바닥글 제거를 지원합니까?
물론 Aspose.Words for .NET을 사용하면 여러 문서의 머리글과 바닥글을 조작할 수 있습니다.

###  설정하는 것을 잊어버리면 어떻게 되나요?`LinkToPrevious` to `false`?
원본 문서의 머리글과 바닥글은 대상 문서까지 계속될 수 있습니다.

### 다른 서식에 영향을 주지 않고 프로그래밍 방식으로 머리글과 바닥글을 제거할 수 있나요?
예, .NET용 Aspose.Words를 사용하면 문서의 나머지 서식을 유지하면서 머리글과 바닥글을 제거할 수 있습니다.

### .NET용 Aspose.Words에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 방문하다[.NET 문서용 Aspose.Words](https://reference.aspose.com/words/net/) 자세한 API 참조 및 예시를 확인하세요.
