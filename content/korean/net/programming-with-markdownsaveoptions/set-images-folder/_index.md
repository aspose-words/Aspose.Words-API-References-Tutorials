---
title: 이미지 폴더 설정
linktitle: 이미지 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 적절한 테이블 정렬을 통해 Word 문서를 Markdown으로 변환합니다. 완벽한 결과를 얻으려면 자세한 가이드를 따르십시오.
type: docs
weight: 10
url: /ko/net/programming-with-markdownsaveoptions/set-images-folder/
---
## 소개

테이블과 콘텐츠가 완벽하게 정렬되도록 하면서 Word 문서를 Markdown 형식으로 내보내고 싶었던 적이 있습니까? Aspose.Words for .NET은 이 작업에 적합한 솔루션입니다. 이 글에서는 Aspose.Words를 설정하고, 문서를 준비하고, 적절한 표 내용 정렬을 통해 Markdown으로 내보내는 과정을 안내합니다. 우리는 쉽게 따라하고 이해할 수 있도록 각 단계를 세분화하겠습니다. 이제 Word 문서를 아름답게 정렬된 Markdown 파일로 변환해 보겠습니다!

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

-  .NET용 Aspose.Words: 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
-  유효한 라이센스: 무료 평가판 받기[여기](https://releases.aspose.com/) 아니면 임시면허증[여기](https://purchase.aspose.com/temporary-license/).
- Visual Studio: 또는 .NET 개발을 지원하는 다른 IDE.
- C# 기본 지식: C# 프로그래밍 언어에 대한 이해.

## 네임스페이스 가져오기

시작하려면 C# 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스를 사용하면 Aspose.Words 기능에 액세스할 수 있습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System.IO;
```

## 1단계: 프로젝트 설정

가장 먼저 IDE에서 .NET 프로젝트를 설정하세요. 새 콘솔 애플리케이션을 만들고 Aspose.Words for .NET에 대한 참조를 추가합니다.

### 1.1 새 프로젝트 만들기

Visual Studio를 열고 새 콘솔 애플리케이션 프로젝트를 만듭니다. 이름을 "MarkdownExporter" 또는 이와 유사한 것으로 지정합니다.

### 1.2 Aspose.Words 참조 추가

 Aspose.Words를 프로젝트에 추가하려면 다음 중 하나에서 DLL을 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/words/net/) 수동으로 추가하거나 NuGet 패키지 관리자를 사용하세요.

```bash
Install-Package Aspose.Words
```

## 2단계: 마크다운으로 내보내기 위한 코드 작성

이제 Word 문서를 읽고 적절한 표 정렬을 통해 Markdown 파일로 저장하는 코드를 작성해 보겠습니다.

### 2.1 문서 경로 정의

Word 문서의 경로와 이미지를 저장할 폴더를 설정하세요.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
```

### 2.2 문서 올려 놓기

Aspose.Words를 사용하여 Word 문서를 로드하세요.

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

### 2.3 마크다운 저장 옵션 구성

 구성`MarkdownSaveOptions` 이미지를 저장할 위치를 지정합니다.

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    ImagesFolder = dataDir + "Images"
};
```

### 2.4 문서를 마크다운으로 저장

 사용`MemoryStream` 문서를 Markdown 형식으로 저장합니다.

```csharp
using (MemoryStream stream = new MemoryStream())
{
    doc.Save(stream, saveOptions);
}
```

## 결론

다음 단계를 따르면 .NET용 Aspose.Words를 사용하여 표 내용 정렬을 사용하여 Word 문서를 Markdown으로 내보내는 것이 간단합니다. 몇 줄의 코드만으로 변환 프로세스를 자동화하고 콘텐츠의 형식이 올바른지 확인할 수 있습니다. 이제 문서가 보기에도 좋고 구조도 유지되므로 Markdown 형식으로 문서를 쉽게 공유할 수 있습니다.

## FAQ

### 다른 프로그래밍 언어와 함께 .NET용 Aspose.Words를 사용할 수 있나요?

예, Aspose.Words for .NET은 VB.NET, F# 등과 같은 모든 .NET 호환 언어와 함께 사용할 수 있습니다.

### Aspose.Words에 대한 임시 라이선스는 어떻게 얻나요?

 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

### 어떤 유형의 문서를 마크다운으로 변환할 수 있나요?

.doc, .docx, .rtf 등을 포함한 다양한 Word 문서를 변환할 수 있습니다.

### Aspose.Words 평가판에 제한 사항이 있나요?

평가판에는 출력 파일의 워터마크와 같은 몇 가지 제한 사항이 있습니다. 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### Aspose.Words에 대한 추가 예제와 문서는 어디에서 찾을 수 있나요?

 자세한 문서와 예제는 다음에서 찾을 수 있습니다.[Aspose 웹사이트](https://reference.aspose.com/words/net/).
