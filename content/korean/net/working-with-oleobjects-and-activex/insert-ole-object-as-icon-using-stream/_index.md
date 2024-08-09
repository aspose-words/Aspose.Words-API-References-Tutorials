---
title: 스트림을 사용하여 Ole 객체를 아이콘으로 삽입
linktitle: 스트림을 사용하여 Ole 객체를 아이콘으로 삽입
second_title: Aspose.Words 문서 처리 API
description: 이 상세한 단계별 튜토리얼에서 .NET용 Aspose.Words가 포함된 스트림을 사용하여 OLE 개체를 아이콘으로 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---
## 소개

이 튜토리얼에서는 .NET용 Aspose.Words의 매우 멋진 기능인 스트림을 사용하여 OLE(Object Linking and Embedding) 개체를 아이콘으로 삽입하는 기능을 살펴보겠습니다. PowerPoint 프리젠테이션, Excel 스프레드시트 또는 기타 유형의 파일을 포함하는 경우 이 가이드에서는 해당 작업을 수행하는 방법을 정확하게 보여줍니다. 시작할 준비가 되셨나요? 갑시다!

## 전제 조건

코드를 시작하기 전에 필요한 몇 가지 사항이 있습니다.

-  .NET용 Aspose.Words: 아직 하지 않으셨다면,[다운로드](https://releases.aspose.com/words/net/) .NET용 Aspose.Words를 설치하세요.
- 개발 환경: Visual Studio 또는 기타 C# 개발 환경.
- 입력 파일: 삽입하려는 파일(예: PowerPoint 프레젠테이션) 및 아이콘 이미지입니다.

## 네임스페이스 가져오기

시작하려면 프로젝트에 필요한 네임스페이스를 가져왔는지 확인하세요.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

따라하기 쉽도록 과정을 단계별로 나누어 보겠습니다.

## 1단계: 새 문서 만들기

먼저 새 문서와 해당 문서로 작업할 문서 작성기를 만듭니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 생각하다`Document` 당신의 빈 캔버스로서`DocumentBuilder` 당신의 붓으로. 우리는 걸작을 만들기 위한 도구를 설정하고 있습니다.

## 2단계: 스트림 준비

다음으로, 삽입하려는 파일이 포함된 메모리 스트림을 준비해야 합니다. 이 예에서는 PowerPoint 프레젠테이션을 포함하겠습니다.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes("Path_to_your_directory/Presentation.pptx")))
{
```

이 단계는 페인트를 브러시에 넣는 것과 같습니다. 파일을 삽입할 준비를 하고 있습니다.

## 3단계: OLE 개체를 아이콘으로 삽입

이제 문서 작성기를 사용하여 OLE 개체를 문서에 삽입하겠습니다. 파일 스트림, 파일 유형(이 경우 "패키지")에 대한 ProgID, 아이콘 이미지 경로 및 포함된 파일에 대한 레이블을 지정합니다.

```csharp
builder.InsertOleObjectAsIcon(stream, "Package", "Path_to_your_directory/Logo icon.ico", "My embedded file");
}
```

이곳이 바로 마법이 일어나는 곳입니다! 파일을 삽입하고 문서 내에 아이콘으로 표시합니다.

## 4단계: 문서 저장

마지막으로 문서를 지정된 경로에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

이 단계는 완성된 그림을 액자에 넣어 벽에 걸어 두는 것과 같습니다. 이제 문서를 사용할 준비가 되었습니다!

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서에 OLE 개체를 아이콘으로 성공적으로 포함했습니다. 이 강력한 기능을 사용하면 동적이고 대화형인 문서를 쉽게 만들 수 있습니다. 프리젠테이션, 스프레드시트 또는 기타 파일을 삽입하든 Aspose.Words를 사용하면 매우 쉽습니다. 그러니 직접 사용해 보시고 문서에 어떤 변화가 생기는지 확인해 보세요!

## FAQ

### 이 방법을 사용하여 다양한 유형의 파일을 포함할 수 있습니까?
예, Word, Excel, PowerPoint 등을 포함하여 OLE에서 지원하는 모든 파일 형식을 포함할 수 있습니다.

### .NET용 Aspose.Words를 사용하려면 특별한 라이센스가 필요합니까?
 예, .NET용 Aspose.Words에는 라이선스가 필요합니다. 당신은 얻을 수 있습니다[무료 평가판](https://releases.aspose.com/) 또는 구매[임시 면허증](https://purchase.aspose.com/temporary-license/) 테스트용.

### OLE 개체에 사용되는 아이콘을 사용자 정의할 수 있나요?
 전적으로! 경로를 지정하여 아이콘에 대한 이미지 파일을 사용할 수 있습니다.`InsertOleObjectAsIcon` 방법.

### 파일이나 아이콘 경로가 올바르지 않으면 어떻게 되나요?
메서드에서 예외가 발생합니다. 오류를 방지하려면 파일 경로가 올바른지 확인하세요.

### 포함된 개체를 포함하는 대신 연결하는 것이 가능합니까?
예, Aspose.Words를 사용하면 내용을 포함하지 않고 파일을 참조하는 연결된 OLE 개체를 삽입할 수 있습니다.