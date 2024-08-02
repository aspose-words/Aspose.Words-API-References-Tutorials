---
title: 마지막으로 저장된 시간 속성 업데이트
linktitle: 마지막으로 저장된 시간 속성 업데이트
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 마지막으로 저장된 시간 속성을 업데이트하는 방법을 알아보세요. 자세한 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
## 소개

프로그래밍 방식으로 Word 문서에서 마지막으로 저장된 시간 속성을 추적하는 방법이 궁금하신가요? 여러 문서를 다루고 메타데이터를 유지해야 하는 경우 마지막으로 저장된 시간 속성을 업데이트하는 것이 매우 편리할 수 있습니다. 오늘은 Aspose.Words for .NET을 사용하여 이 과정을 안내하겠습니다. 그러니 버클을 채우고 뛰어들어 보세요!

## 전제 조건

단계별 가이드를 시작하기 전에 필요한 몇 가지 사항이 있습니다.

1.  .NET용 Aspose.Words: .NET용 Aspose.Words가 설치되어 있는지 확인하세요. 아직 안 해보셨다면 할 수 있습니다[여기에서 다운로드하십시오](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio와 같은 개발 환경입니다.
3. C# 기본 지식: C# 프로그래밍의 기본을 이해하면 도움이 됩니다.

## 네임스페이스 가져오기

우선, 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이를 통해 Word 문서를 조작하는 데 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

이제 프로세스를 간단한 단계로 나누어 보겠습니다. 각 단계는 Word 문서에서 마지막으로 저장된 시간 속성을 업데이트하는 과정을 안내합니다.

## 1단계: 문서 디렉토리 설정

먼저 문서 디렉터리의 경로를 지정해야 합니다. 여기에는 기존 문서가 저장되고 업데이트된 문서가 저장됩니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 디렉터리의 실제 경로를 사용합니다.

## 2단계: Word 문서 로드

 그런 다음 업데이트하려는 Word 문서를 로드합니다. 이 작업은 인스턴스를 생성하여 수행할 수 있습니다.`Document` 클래스를 작성하고 문서 경로를 전달합니다.

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

 이름이 지정된 문서인지 확인하세요.`Document.docx` 지정된 디렉터리에 있습니다.

## 3단계: 저장 옵션 구성

 이제`OoxmlSaveOptions` 수업. 이 클래스를 사용하면 문서를 OOXML(Office Open XML) 형식으로 저장하기 위한 옵션을 지정할 수 있습니다. 여기서는`UpdateLastSavedTimeProperty` 에게`true`.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions
{
    UpdateLastSavedTimeProperty = true
};
```

이는 Aspose.Words에게 문서의 마지막 저장된 시간 속성을 업데이트하도록 지시합니다.

## 4단계: 업데이트된 문서 저장

 마지막으로 다음을 사용하여 문서를 저장합니다.`Save` 의 방법`Document` 클래스에 업데이트된 문서를 저장할 경로와 저장 옵션을 전달합니다.

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

그러면 업데이트된 마지막 저장 시간 속성으로 문서가 저장됩니다.

## 결론

그리고 거기에 있습니다! 다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 Word 문서의 마지막 저장 시간 속성을 쉽게 업데이트할 수 있습니다. 이는 문서 관리 시스템 및 기타 다양한 애플리케이션에 매우 중요한 문서의 정확한 메타데이터를 유지하는 데 특히 유용합니다.

## FAQ

### .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 .NET 애플리케이션에서 Word 문서를 생성, 편집, 변환하기 위한 강력한 라이브러리입니다.

### 마지막으로 저장된 시간 속성을 업데이트해야 하는 이유는 무엇입니까?
마지막으로 저장된 시간 속성을 업데이트하면 문서 추적 및 관리에 필수적인 정확한 메타데이터를 유지하는 데 도움이 됩니다.

### .NET용 Aspose.Words를 사용하여 다른 속성을 업데이트할 수 있나요?
예, .NET용 Aspose.Words를 사용하면 제목, 작성자, 제목과 같은 다양한 문서 속성을 업데이트할 수 있습니다.

### .NET용 Aspose.Words는 무료인가요?
 Aspose.Words for .NET은 무료 평가판을 제공하지만 전체 기능을 사용하려면 라이선스가 필요합니다. 라이센스를 취득하실 수 있습니다[여기](https://purchase.aspose.com/buy).

### .NET용 Aspose.Words에 대한 추가 튜토리얼은 어디서 찾을 수 있나요?
더 많은 튜토리얼과 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/words/net/).
