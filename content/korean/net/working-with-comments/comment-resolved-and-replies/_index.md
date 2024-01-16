---
title: 해결된 댓글 및 답변
linktitle: 해결된 댓글 및 답변
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 댓글과 답변을 해결하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-comments/comment-resolved-and-replies/
---

이 포괄적인 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 댓글과 답변을 해결하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 댓글 해결을 관리하고 댓글 상태와 답변을 업데이트할 수 있게 됩니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 문서 로드 및 설명 액세스
시작하려면 Document 클래스를 사용하여 주석이 포함된 문서를 로드하고 주석 컬렉션에 액세스합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## 2단계: 댓글 및 답변 해결
다음으로 댓글과 답변을 반복하여 해결됨으로 표시합니다.

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

위 코드에서는 상위 댓글에 액세스하고 해당 답변을 반복합니다. 상위 댓글 ID와 해결 상태를 검색할 수 있습니다. 그런 다음 해결 방법을 나타내기 위해 각 댓글 답변의 "완료" 표시를 업데이트합니다.

## 3단계: 문서 저장
주석을 해결하고 상태를 업데이트한 후 Document 클래스의 Save 메서드를 사용하여 수정된 문서를 파일에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### .NET용 Aspose.Words를 사용하여 댓글 및 응답을 해결하기 위한 예제 소스 코드
다음은 .NET용 Aspose.Words를 사용하여 댓글과 답변을 해결하기 위한 전체 소스 코드입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
문서 파일 경로 및 추가 사용자 정의를 포함하여 특정 요구 사항에 따라 코드를 조정해야 합니다.

## 결론
축하해요! Aspose.Words for .NET을 사용하여 Word 문서에서 댓글과 답변을 해결하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 요구 사항에 따라 댓글 해결을 관리하고 댓글 상태와 답변을 업데이트할 수 있습니다.

댓글 해결은 문서 내의 피드백을 추적하고 관리하는 데 도움이 됩니다. 다양한 댓글 상태를 실험하고 맞춤설정하여 문서의 공동 작업 및 검토 프로세스를 개선하세요.

### FAQ

#### Q: .NET용 Aspose.Words에서 주석을 어떻게 해결합니까?

 A: Aspose.Words for .NET에서 주석을 해결하려면 다음을 사용할 수 있습니다.`Comment.Resolve` 지정하는 방법`Comment` 해결하려는 개체. 이렇게 하면 댓글이 해결된 것으로 표시되고 최종 문서에서 숨겨집니다.

#### Q: Aspose.Words for .NET에서 해결된 댓글에 답글을 어떻게 추가하나요?

 A: 해결된 댓글은 기본적으로 최종 문서에 숨겨져 있지만 다음을 사용하여 해결된 댓글에 답글을 추가할 수 있습니다.`Comment.AddReply` 응답 텍스트와 이를 추가할 위치를 지정하는 방법입니다.

#### Q: .NET용 Aspose.Words에서 해결된 댓글을 어떻게 볼 수 있나요?

 A: 기본적으로 해결된 댓글은 최종 문서에 숨겨집니다. 그러나 다음을 사용하여 표시할 수 있습니다.`CommentOptions.ShowResolvedComments` 의 재산`Document` 개체를 설정하고`true`.

#### Q: Aspose.Words for .NET에서 답글을 포함한 모든 댓글을 숨기려면 어떻게 해야 합니까?

 A: Aspose.Words for .NET에서 회신을 포함한 모든 댓글을 숨기려면 다음을 사용할 수 있습니다.`CommentOptions.CommentDisplayMode` 의 재산`Document` 개체를 설정하고`CommentDisplayMode.None`.

#### Q: Aspose.Words for .NET에서 해결된 댓글의 텍스트를 편집할 수 있나요?

 A: 예, Aspose.Words for .NET에 액세스하여 해결된 댓글의 텍스트를 편집할 수 있습니다.`Comment.Text` 해당 속성`Comment` 개체를 수정하고 필요에 따라 텍스트를 수정합니다.