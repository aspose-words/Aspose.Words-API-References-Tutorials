---
title: 추가 댓글 답글 삭제
linktitle: 추가 댓글 답글 삭제
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 댓글 답글을 추가하고 제거하는 방법을 알아보세요. 이 단계별 가이드를 통해 문서 공동작업을 강화하세요.
type: docs
weight: 10
url: /ko/net/working-with-comments/add-remove-comment-reply/
---
## 소개

Word 문서에서 주석과 답변을 사용하여 작업하면 문서 검토 프로세스가 크게 향상될 수 있습니다. .NET용 Aspose.Words를 사용하면 이러한 작업을 자동화하여 작업 흐름을 더욱 효율적이고 간소화할 수 있습니다. 이 튜토리얼에서는 댓글 답글을 추가하고 제거하는 과정을 안내하고 이 기능을 익히기 위한 단계별 가이드를 제공합니다.

## 전제 조건

코드를 살펴보기 전에 다음 사항을 확인하세요.

-  .NET용 Aspose.Words: 다음에서 다운로드하여 설치하세요.[여기](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio 또는 .NET을 지원하는 기타 IDE.
- C#에 대한 기본 지식: C# 프로그래밍에 대한 지식이 필수적입니다.

## 네임스페이스 가져오기

시작하려면 C# 프로젝트에서 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using Aspose.Words;
```

## 1단계: Word 문서 로드

먼저, 관리하려는 댓글이 포함된 Word 문서를 로드해야 합니다. 이 예에서는 디렉터리에 "Comments.docx"라는 문서가 있다고 가정합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## 2단계: 첫 번째 댓글에 액세스

다음으로 문서의 첫 번째 댓글에 액세스합니다. 이 댓글이 댓글 추가 및 삭제 대상이 됩니다.

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

## 3단계: 기존 답변 삭제

댓글에 이미 답글이 있으면 삭제하는 것이 좋습니다. 댓글의 첫 번째 답글을 삭제하는 방법은 다음과 같습니다.

```csharp
comment.RemoveReply(comment.Replies[0]);
```

## 4단계: 새 답장 추가

이제 댓글에 새로운 답글을 추가해 보겠습니다. 작성자 이름, 이니셜, 답변 날짜 및 시간, 답변 텍스트를 지정할 수 있습니다.

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## 5단계: 업데이트된 문서 저장

마지막으로 수정된 문서를 디렉터리에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## 결론

Word 문서의 댓글 응답을 프로그래밍 방식으로 관리하면 특히 광범위한 검토를 처리할 때 많은 시간과 노력을 절약할 수 있습니다. Aspose.Words for .NET은 이 프로세스를 간단하고 효율적으로 만듭니다. 이 가이드에 설명된 단계를 따르면 주석 답글을 쉽게 추가 및 제거하여 문서 공동 작업 환경을 향상시킬 수 있습니다.

## FAQ

### 단일 댓글에 여러 개의 답글을 추가하려면 어떻게 해야 하나요?

 다음을 호출하여 단일 댓글에 여러 개의 답글을 추가할 수 있습니다.`AddReply` 동일한 주석 개체에 대해 여러 번 메서드를 사용합니다.

### 각 답변의 작성자 세부정보를 맞춤설정할 수 있나요?

 예, 작성자 이름, 이니셜, 각 답변의 날짜 및 시간을 지정할 수 있습니다.`AddReply` 방법.

### 댓글의 모든 답글을 한 번에 삭제할 수 있나요?

모든 응답을 제거하려면 다음을 반복해야 합니다.`Replies` 댓글을 수집하고 각 댓글을 개별적으로 제거합니다.

### 문서의 특정 섹션에 있는 댓글에 액세스할 수 있나요?

 예, 다음을 사용하여 문서의 섹션을 탐색하고 각 섹션 내의 댓글에 액세스할 수 있습니다.`GetChild` 방법.

### .NET용 Aspose.Words는 다른 주석 관련 기능을 지원합니까?

예, Aspose.Words for .NET은 새 주석 추가, 주석 속성 설정 등 다양한 주석 관련 기능에 대한 광범위한 지원을 제공합니다.