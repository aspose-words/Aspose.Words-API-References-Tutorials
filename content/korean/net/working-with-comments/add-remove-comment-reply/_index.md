---
title: 추가 댓글 답글 삭제
linktitle: 추가 댓글 답글 삭제
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 댓글 답글을 추가하고 제거하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-comments/add-remove-comment-reply/
---

이 포괄적인 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 댓글 답글을 추가하고 제거하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 댓글 답글을 관리하고 요구 사항에 따라 맞춤 설정할 수 있게 됩니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 문서 로드
시작하려면 Document 클래스를 사용하여 주석이 포함된 문서를 로드합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## 2단계: 댓글 액세스 및 답글 관리
그런 다음 NodeType.Comment 매개 변수와 함께 GetChild 메서드를 사용하여 문서의 주석에 액세스합니다.

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

댓글에서 답글을 제거하려면 RemoveReply 메서드를 사용하고 원하는 답글 인덱스를 제공하세요.

```csharp
comment.RemoveReply(comment.Replies[0]);
```

댓글에 새 답변을 추가하려면 AddReply 메서드를 사용하고 작성자 이름, 작성자 이니셜, 날짜 및 시간, 답변 텍스트를 제공하세요.

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## 3단계: 문서 저장
주석 응답을 추가하거나 제거한 후 Document 클래스의 Save 메서드를 사용하여 문서를 파일에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### .NET용 Aspose.Words를 사용하여 댓글 응답 추가 및 제거를 위한 예제 소스 코드
다음은 .NET용 Aspose.Words를 사용하여 댓글 답글을 추가하고 제거하기 위한 전체 소스 코드입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## 결론
축하해요! Aspose.Words for .NET을 사용하여 Word 문서에서 주석 응답을 추가하고 제거하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 댓글 응답을 관리하고 요구 사항에 따라 사용자 정의할 수 있습니다.

댓글 답글을 사용하면 문서 내에서 공동 토론과 피드백을 얻을 수 있습니다. 다양한 응답 작성자, 이니셜, 날짜 및 텍스트를 실험하여 문서 내에서 공동 작업과 커뮤니케이션을 강화하세요.

### FAQ

#### Q: .NET용 Aspose.Words에 어떻게 설명을 추가할 수 있나요?

 A: .NET용 Aspose.Words에 주석을 추가하려면 다음을 사용할 수 있습니다.`Comment.AddComment` 주석 텍스트와 문서에 주석을 추가할 위치를 지정하는 방법입니다.

#### Q: .NET용 Aspose.Words에서 주석을 어떻게 제거할 수 있나요?

 A: .NET용 Aspose.Words에서 주석을 제거하려면 다음을 사용할 수 있습니다.`Comment.Remove` 지정하는 방법`Comment` 제거하려는 개체.

#### Q: Aspose.Words for .NET의 댓글에 답글을 달 수 있나요?

 A: 예, Aspose.Words for .NET에서 다음을 사용하여 댓글에 회신할 수 있습니다.`Comment.AddReply` 회신 텍스트와 이를 문서에 추가할 위치를 지정하는 메서드입니다.

#### Q: .NET용 Aspose.Words의 기존 댓글에 어떻게 액세스할 수 있나요?

 A: 다음을 사용하여 .NET용 Aspose.Words의 기존 주석에 액세스할 수 있습니다.`CommentCollection` 의 재산`Document`물체. 이렇게 하면 문서에 있는 모든 주석을 찾아볼 수 있습니다.

#### Q: .NET용 Aspose.Words에서 주석 텍스트를 편집할 수 있나요?

 A: 예, Aspose.Words for .NET에 액세스하여 주석 텍스트를 편집할 수 있습니다.`Comment.Text` 해당 속성`Comment` 개체를 수정하고 필요에 따라 텍스트를 수정합니다.