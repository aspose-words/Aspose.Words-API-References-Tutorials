---
title: Word 문서의 읽기 전용 보호
linktitle: Word 문서의 읽기 전용 보호
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 읽기 전용을 보호하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-protection/read-only-protection/
---
이 튜토리얼에서는 Aspose.Words for .NET의 읽기 전용 보호 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 Word 문서를 읽기 전용으로 만들어 무단 수정을 방지할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 생성 및 보호 적용

Document 클래스와 DocumentBuilder 개체의 인스턴스를 만드는 것부터 시작합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 문서에 콘텐츠 쓰기
DocumentBuilder 객체를 사용하여 문서에 내용을 씁니다.

```csharp
builder.Write("Open document as read-only");
```

## 3단계: 비밀번호를 설정하고 문서를 읽기 전용으로 설정

WriteProtection 객체의 SetPassword() 속성을 사용하여 문서의 비밀번호를 설정합니다.

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

"MyPassword"를 사용하려는 실제 비밀번호로 바꾸십시오.

## 4단계: 읽기 전용 문서 적용

ReadOnlyRecommended 속성을 true로 설정하여 문서를 읽기 전용으로 만듭니다.

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## 5단계: 읽기 전용 보호 적용 및 문서 저장

마지막으로 Document 개체의 Protect() 메서드를 사용하여 읽기 전용 보호를 적용합니다.

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

보호된 문서를 저장하려면 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하는 읽기 전용 보호의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하는 읽기 전용 보호의 전체 소스 코드입니다.

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// 최대 15자 길이의 비밀번호를 입력하세요.
doc.WriteProtection.SetPassword("MyPassword");

// 문서를 읽기 전용으로 만듭니다.
doc.WriteProtection.ReadOnlyRecommended = true;

// 읽기 전용으로 쓰기 보호를 적용합니다.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

다음 단계를 따르면 문서를 쉽게 보호할 수 있습니다.

## 결론

이 튜토리얼에서는 무단 수정을 방지하기 위해 Word 문서를 읽기 전용으로 만들 수 있는 Aspose.Words for .NET의 읽기 전용 보호 기능을 살펴보았습니다. 제공된 단계를 따르면 문서에 읽기 전용 보호를 쉽게 적용하고 보안을 강화할 수 있습니다. 읽기 전용 보호는 편집 기능을 제한하여 문서 내용의 무결성과 정확성을 보장하는 데 도움이 됩니다. Aspose.Words for .NET은 문서 보호를 처리하는 강력하고 유연한 API를 제공하고 Word 문서를 사용자 정의하고 보호하는 다양한 기타 기능을 지원합니다.

### Word 문서의 읽기 전용 보호에 대한 FAQ

#### Q: Aspose.Words for .NET의 읽기 전용 보호란 무엇입니까?

A: Aspose.Words for .NET의 읽기 전용 보호는 Word 문서를 읽기 전용으로 만들어 무단 수정을 방지할 수 있는 기능입니다. 문서가 읽기 전용으로 설정되면 사용자는 문서를 열고 볼 수 있지만 내용을 변경할 수는 없습니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에 읽기 전용 보호를 적용하려면 어떻게 해야 합니까?

A: .NET용 Aspose.Words를 사용하여 Word 문서에 읽기 전용 보호를 적용하려면 다음 단계를 따르세요.
1.  인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 물체.
2.  사용`DocumentBuilder` 문서에 내용을 쓰려면
3.  다음을 사용하여 문서의 비밀번호를 설정하세요.`SetPassword` 의 방법`WriteProtection` 물체.
4.  설정`ReadOnlyRecommended` 의 재산`WriteProtection` 반대하다`true` 문서를 읽기 전용으로 여는 것이 좋습니다.
5.  다음을 사용하여 읽기 전용 보호를 적용합니다.`Protect` 의 방법`Document` 객체, 지정`ProtectionType` ~처럼`ReadOnly`.
6.  다음을 사용하여 보호된 문서를 저장하세요.`Save` 의 방법`Document` 물체.

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서에서 읽기 전용 보호를 제거할 수 있습니까?

A: 예, Aspose.Words for .NET을 사용하여 Word 문서에서 읽기 전용 보호를 제거할 수 있습니다. 이렇게 하려면 다음을 사용할 수 있습니다.`Unprotect` 의 방법`Document` 문서에서 기존 보호를 제거하는 클래스입니다.

#### Q: Word 문서에서 읽기 전용 보호를 위해 다른 비밀번호를 설정할 수 있나요?

 A: 아니요, Aspose.Words for .NET의 읽기 전용 보호에서는 특히 읽기 전용 보호를 위해 별도의 비밀번호를 설정할 수 없습니다. 비밀번호는 다음을 사용하여 설정합니다.`SetPassword` 의 방법`WriteProtection` 개체는 읽기 전용 및 읽기-쓰기 보호를 포함하여 전체 문서 보호에 적용됩니다.

#### Q: 사용자가 Word 문서에서 읽기 전용 보호를 우회할 수 있습니까?

A: Word 문서의 읽기 전용 보호는 우발적이거나 무단 수정을 방지하기 위한 것입니다. 일정 수준의 보호 기능을 제공하지만 충분한 기술 지식이 있거나 편집 권한이 있는 사용자는 이를 우회할 수 있습니다. 그러나 읽기 전용 보호는 억제책 역할을 하며 문서의 무결성을 유지하는 데 도움이 됩니다.