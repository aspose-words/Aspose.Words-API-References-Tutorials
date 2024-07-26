---
title: 문서 파일 형식 감지
linktitle: 문서 파일 형식 감지
second_title: Aspose.Words 문서 처리 API
description: 이 포괄적인 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 문서 파일 형식을 감지하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-fileformat/detect-file-format/
---
## 소개

오늘날의 디지털 세계에서는 다양한 문서 형식을 효율적으로 관리하는 것이 중요합니다. Word, PDF, HTML 또는 기타 형식을 처리하는 경우 이러한 파일을 올바르게 감지하고 처리할 수 있으면 많은 시간과 노력을 절약할 수 있습니다. 이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서 파일 형식을 감지하는 방법을 살펴보겠습니다. 이 가이드는 전제 조건부터 자세한 단계별 가이드까지 알아야 할 모든 것을 안내합니다.

## 전제조건

코드를 살펴보기 전에 필요한 모든 것이 갖추어져 있는지 확인하겠습니다.

-  .NET용 Aspose.Words: 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/) . 유효한 라이센스가 있는지 확인하십시오. 그렇지 않은 경우[임시면허](https://purchase.aspose.com/temporary-license/).
- Visual Studio: 모든 최신 버전이 정상적으로 작동합니다.
- .NET Framework: 올바른 버전이 설치되어 있는지 확인하세요.

## 네임스페이스 가져오기

시작하려면 프로젝트에서 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

더 쉽게 따라할 수 있도록 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 디렉터리 설정

먼저, 파일이 형식에 따라 정렬될 디렉터리를 설정해야 합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// 디렉토리가 아직 존재하지 않는 경우 디렉토리를 작성하십시오.
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## 2단계: 파일 목록 가져오기

다음으로 손상된 문서를 제외하고 디렉터리에서 파일 목록을 가져옵니다.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## 3단계: 파일 형식 감지

이제 Aspose.Words를 사용하여 각 파일을 반복하고 해당 형식을 감지합니다.

```csharp
foreach (string fileName in fileList)
{
    string nameOnly = Path.GetFileName(fileName);

    Console.Write(nameOnly);

    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

    // 문서 유형 표시
    switch (info.LoadFormat)
    {
        case LoadFormat.Doc:
            Console.WriteLine("\tMicrosoft Word 97-2003 document.");
            break;
        case LoadFormat.Dot:
            Console.WriteLine("\tMicrosoft Word 97-2003 template.");
            break;
        case LoadFormat.Docx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
            break;
        case LoadFormat.Docm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
            break;
        case LoadFormat.Dotx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
            break;
        case LoadFormat.Dotm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
            break;
        case LoadFormat.FlatOpc:
            Console.WriteLine("\tFlat OPC document.");
            break;
        case LoadFormat.Rtf:
            Console.WriteLine("\tRTF format.");
            break;
        case LoadFormat.WordML:
            Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
            break;
        case LoadFormat.Html:
            Console.WriteLine("\tHTML format.");
            break;
        case LoadFormat.Mhtml:
            Console.WriteLine("\tMHTML (Web archive) format.");
            break;
        case LoadFormat.Odt:
            Console.WriteLine("\tOpenDocument Text.");
            break;
        case LoadFormat.Ott:
            Console.WriteLine("\tOpenDocument Text Template.");
            break;
        case LoadFormat.DocPreWord60:
            Console.WriteLine("\tMS Word 6 or Word 95 format.");
            break;
        case LoadFormat.Unknown:
            Console.WriteLine("\tUnknown format.");
            break;
    }

    if (info.IsEncrypted)
    {
        Console.WriteLine("\tAn encrypted document.");
        File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
    }
    else
    {
        switch (info.LoadFormat)
        {
            case LoadFormat.DocPreWord60:
                File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
                break;
            case LoadFormat.Unknown:
                File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
                break;
            default:
                File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
                break;
        }
    }
}
```

## 결론

.NET용 Aspose.Words를 사용하여 문서 파일 형식을 감지하는 과정은 간단합니다. 디렉토리를 설정하고, 파일 목록을 가져오고, Aspose.Words를 활용하여 파일 형식을 감지함으로써 문서를 효율적으로 구성하고 관리할 수 있습니다. 이 접근 방식을 사용하면 시간을 절약할 수 있을 뿐만 아니라 다양한 문서 형식을 올바르게 처리할 수 있습니다.

## FAQ

### .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 Word 문서를 프로그래밍 방식으로 작업하기 위한 강력한 라이브러리입니다. 이를 통해 개발자는 다양한 형식의 문서를 생성, 수정 및 변환할 수 있습니다.

### Aspose.Words는 암호화된 문서를 감지할 수 있나요?
네, Aspose.Words는 문서가 암호화되었는지 감지할 수 있으며 이에 따라 그러한 문서를 처리할 수 있습니다.

### Aspose.Words는 어떤 형식을 감지할 수 있나요?
Aspose.Words는 DOC, DOCX, RTF, HTML, MHTML, ODT 등을 포함한 광범위한 형식을 감지할 수 있습니다.

### Aspose.Words에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 발급받으실 수 있습니다.[구매 제안](https://purchase.aspose.com/temporary-license/) 페이지.

### Aspose.Words에 대한 문서는 어디서 찾을 수 있나요?
 Aspose.Words에 대한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/words/net/).
