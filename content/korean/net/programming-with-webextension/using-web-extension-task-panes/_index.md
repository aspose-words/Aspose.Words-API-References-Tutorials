---
title: 웹 확장 작업창 사용
linktitle: 웹 확장 작업창 사용
second_title: Aspose.Words 문서 처리 API
description: 이 상세한 단계별 튜토리얼에서 .NET용 Aspose.Words를 사용하여 Word 문서에 웹 확장 작업창을 추가하고 구성하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-webextension/using-web-extension-task-panes/
---
## 소개

.NET용 Aspose.Words를 사용하여 Word 문서에서 웹 확장 작업창을 사용하는 방법에 대한 심층적인 튜토리얼에 오신 것을 환영합니다. 대화형 작업창을 사용하여 Word 문서를 향상시키고 싶다면 올바른 위치에 오셨습니다. 이 가이드는 이를 원활하게 달성하기 위한 모든 단계를 안내합니다.

## 전제 조건

자세히 알아보기 전에 필요한 모든 것이 갖추어져 있는지 확인하겠습니다.

-  .NET용 Aspose.Words: 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
- .NET 개발 환경: Visual Studio 또는 선호하는 기타 IDE.
- C#에 대한 기본 지식: 코드 예제를 따라가는 데 도움이 됩니다.
-  Aspose.Words 라이선스: 구매 가능[여기](https://purchase.aspose.com/buy) 아니면 임시면허를 취득하세요.[여기](https://purchase.aspose.com/temporary-license/).

## 네임스페이스 가져오기

코딩을 시작하기 전에 프로젝트에 다음 네임스페이스를 가져왔는지 확인하세요.

```csharp
using Aspose.Words;
using Aspose.Words.WebExtensions;
```

## 단계별 가이드

이제 프로세스를 따라하기 쉬운 단계로 나누어 보겠습니다.

### 1단계: 문서 디렉토리 설정

먼저, 문서 디렉터리 경로를 설정해야 합니다. 여기에 Word 문서가 저장됩니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 폴더의 실제 경로와 함께.

### 2단계: 새 문서 만들기

다음으로 Aspose.Words를 사용하여 새 Word 문서를 만듭니다.

```csharp
Document doc = new Document();
```

 이 줄은`Document` Word 문서를 나타내는 클래스입니다.

### 3단계: 작업창 추가

이제 문서에 작업창을 추가하겠습니다. 작업창은 Word 문서 내에서 추가 기능과 도구를 제공하는 데 유용합니다.

```csharp
TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);
```

 여기서는 새 항목을 만듭니다.`TaskPane` 개체를 문서에 추가합니다.`WebExtensionTaskPanes` 수집.

### 4단계: 작업 창 구성

작업창을 표시하고 해당 속성을 설정하려면 다음 코드를 사용합니다.

```csharp
taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

- `DockState` 작업창이 나타날 위치를 설정합니다. 이 경우 오른쪽에 있습니다.
- `IsVisible` 작업창이 표시되는지 확인합니다.
- `Width` 작업창의 너비를 설정합니다.

### 5단계: 웹 확장 참조 설정

다음으로 ID, 버전, 스토어 유형, 스토어가 포함된 웹 확장 참조를 설정합니다.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

- `Id`웹 확장의 고유 식별자입니다.
- `Version` 확장 버전을 지정합니다.
- `StoreType` 매장 유형을 나타냅니다(이 경우 OMEX).
- `Store` 매장의 언어/문화 코드를 지정합니다.

### 6단계: 웹 확장에 속성 추가

웹 확장에 속성을 추가하여 동작이나 콘텐츠를 정의할 수 있습니다.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
```

 여기에 다음과 같은 속성을 추가합니다.`mailchimpCampaign`.

### 7단계: 웹 확장 바인딩

마지막으로 웹 확장에 바인딩을 추가합니다. 바인딩을 사용하면 확장을 문서의 특정 부분에 연결할 수 있습니다.

```csharp
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545", WebExtensionBindingType.Text, "194740422"));
```

- `UnnamedBinding_0_1506535429545` 바인딩의 이름입니다.
- `WebExtensionBindingType.Text` 바인딩이 텍스트 유형임을 나타냅니다.
- `194740422` 확장이 바인딩된 문서 부분의 ID입니다.

### 8단계: 문서 저장

모든 설정을 마친 후 문서를 저장하세요.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

이 줄은 지정된 파일 이름으로 지정된 디렉터리에 문서를 저장합니다.

### 9단계: 작업창 정보 로드 및 표시

작업창 정보를 확인하고 표시하기 위해 문서를 로드하고 작업창을 반복합니다.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");

Console.WriteLine("Task panes sources:\n");

foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
    WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
    Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
}
```

이 코드는 문서를 로드하고 콘솔에 있는 각 작업창의 공급자, 버전 및 카탈로그 식별자를 인쇄합니다.

## 결론

그리고 그게 다야! Aspose.Words for .NET을 사용하여 Word 문서에 웹 확장 작업창을 성공적으로 추가하고 구성했습니다. 이 강력한 기능은 문서 내에서 직접 추가 기능을 제공하여 Word 문서를 크게 향상시킬 수 있습니다. 

## FAQ

### Word의 작업창이란 무엇입니까?
작업창은 Word 문서 내에서 추가 도구와 기능을 제공하여 사용자 상호 작용과 생산성을 향상시키는 인터페이스 요소입니다.

### 작업창의 모양을 사용자 지정할 수 있나요?
 예, 다음과 같은 속성을 설정하여 작업창의 모양을 사용자 정의할 수 있습니다.`DockState`, `IsVisible` , 그리고`Width`.

### 웹 확장 속성이란 무엇입니까?
웹 확장 속성은 웹 확장에 추가하여 해당 동작이나 콘텐츠를 정의할 수 있는 사용자 지정 속성입니다.

### 웹 확장을 문서의 일부에 어떻게 바인딩합니까?
 다음을 사용하여 웹 확장을 문서의 일부에 바인딩할 수 있습니다.`WebExtensionBinding` 클래스, 바인딩 유형 및 대상 ID를 지정합니다.

### .NET용 Aspose.Words에 대한 자세한 정보는 어디서 찾을 수 있나요?
 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/words/net/).