---
title: Word 문서에서 문서 보호 제거
linktitle: Word 문서에서 문서 보호 제거
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 보호를 제거하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-protection/remove-document-protection/
---
이 튜토리얼에서는 Aspose.Words for .NET의 문서 보호 해제 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 Word 문서에서 보호를 제거하여 추가 편집이 가능하도록 할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 생성 및 콘텐츠 추가

Document 클래스와 DocumentBuilder 개체의 인스턴스를 만드는 것부터 시작합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 문서에 콘텐츠 추가

DocumentBuilder 객체를 사용하여 문서에 내용을 추가합니다.

```csharp
builder.Writeln("Text added to a document.");
```

## 3단계: 문서 보호 해제

문서 보호를 해제하려면 Document 개체의 Unprotect() 메서드를 사용할 수 있습니다. 비밀번호 없이 또는 올바른 비밀번호로 보호를 제거하도록 선택할 수 있습니다. 비밀번호 없는 보호 제거:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

"newPassword"를 올바른 문서 비밀번호로 바꾸십시오.

## 4단계: 보호 없이 문서 저장

마지막으로 Document 개체의 Save() 메서드를 사용하여 보호되지 않은 문서를 저장합니다.

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

문서를 보호되지 않은 상태로 저장하려면 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 문서 보호 제거에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 문서 보호를 해제하는 전체 소스 코드입니다.

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

// 문서는 비밀번호가 없거나 올바른 비밀번호를 사용하여 보호 기능을 제거할 수 있습니다.
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

다음 단계를 따르면 Aspose.Words for .NET을 사용하여 Word 문서에서 보호 기능을 쉽게 제거할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 문서 보호를 제거하는 방법을 살펴보았습니다. 제공된 단계를 따르면 쉽게 문서 보호를 해제하고 추가 편집을 위해 문서에 액세스할 수 있습니다. Aspose.Words for .NET은 문서 보호 설정을 조작하고 Word 문서의 보안 수준을 사용자 정의할 수 있는 강력한 API를 제공합니다. 문서 보호를 제거하면 필요에 따라 문서 내용과 서식을 유연하게 수정할 수 있습니다.

### Word 문서의 문서 보호 제거에 대한 FAQ

#### Q: Aspose.Words for .NET의 문서 보호란 무엇입니까?

A: Aspose.Words for .NET의 문서 보호는 Word 문서에 보안 조치를 적용하여 편집, 서식 지정 및 콘텐츠 수정을 제한할 수 있는 기능을 의미합니다. 이는 문서의 무결성과 기밀성을 보장하는 데 도움이 됩니다.

#### Q: Aspose.Words for .NET을 사용하여 문서 보호를 어떻게 제거할 수 있나요?

A: .NET용 Aspose.Words를 사용하여 문서 보호를 제거하려면 다음 단계를 따르세요.
1.  인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 물체.
2.  사용`DocumentBuilder` 문서에 내용을 추가하려면
3.  를 불러`Unprotect` 의 방법`Document` 문서에서 기존 보호를 제거하는 데 반대합니다. 이는 비밀번호 없이 또는 올바른 비밀번호를 제공하여 수행할 수 있습니다.
4.  다음을 사용하여 보호되지 않은 문서를 저장하십시오.`Save` 의 방법`Document` 물체.

#### Q: 암호 없이 Word 문서에서 보호를 제거할 수 있나요?

 A: 예, Aspose.Words for .NET을 사용하여 비밀번호 없이 Word 문서에서 보호를 제거할 수 있습니다. 전화로`Unprotect` 의 방법`Document`암호를 제공하지 않고 개체를 삭제하는 경우 이전에 암호 없이 문서를 보호한 경우 문서에서 보호를 제거할 수 있습니다.

#### Q: 암호를 사용하여 Word 문서의 보호를 제거하려면 어떻게 해야 합니까?

 A: 비밀번호로 보호된 Word 문서에서 보호를 제거하려면 전화를 걸 때 올바른 비밀번호를 제공해야 합니다.`Unprotect` 의 방법`Document` 물체. 이렇게 하면 올바른 비밀번호를 가진 사용자만 보호를 제거하고 편집을 위해 문서에 액세스할 수 있습니다.

#### Q: Word 문서에서 특정 보호 유형을 제거할 수 있나요?

 A: 예, .NET용 Aspose.Words를 사용하면 Word 문서에서 특정 보호 유형을 선택적으로 제거할 수 있습니다. 전화로`Unprotect` 의 방법`Document` 개체의 경우 읽기 전용 보호, 양식 보호 등 원하는 보호 유형을 제거하고 다른 보호 유형은 그대로 유지할 수 있습니다.