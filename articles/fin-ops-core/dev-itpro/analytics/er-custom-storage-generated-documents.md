---
title: Especificar um local de armazenamento personalizado para os documentos gerados
description: Este tópico explica como estender a lista de locais de armazenamento para documentos gerados pelos formatos de relatório eletrônico (ER).
author: NickSelin
manager: AnnBe
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: 5e9afad936a353c8db3c316ad45c4ce28d33b129
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680797"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a>Especificar um local de armazenamento personalizado para os documentos gerados

[!include[banner](../includes/banner.md)]

A interface de programação de aplicativos (API) da estrutura de relatórios eletrônicos (ER) permite estender a lista de locais de armazenamento para documentos gerados pelos formatos ER. Este tópico inclui uma visão geral das tarefas principais que você deve concluir para adicionar um local de armazenamento personalizado.

## <a name="prerequisites"></a>Pré-requisitos

Você deve implantar uma topologia que dê suporte à compilação contínua. (Para obter mais informações, consulte [Implantar topologias com suporte à contínua automação de compilações e testes](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) Você deve ter acesso a essa topologia para uma das seguintes funções:

- Desenvolvedor de relatório eletrônico
- Consultor funcional de relatório eletrônico
- Administrador do sistema

Você também deve ter acesso ao ambiente de desenvolvimento para essa topologia.

## <a name="create-or-import-an-er-format-configuration"></a>Criar ou importar uma configuração de formato ER

Na topologia atual, [crie um novo formato de ER](tasks/er-format-configuration-2016-11.md) para gerar documentos aos quais você planeja adicionar um local de armazenamento personalizado. Como alternativa, [importe um formato ER existente para essa topologia](general-electronic-reporting-manage-configuration-lifecycle.md).

![Página do designer de formatos](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> O formato ER que você cria ou importa deve conter pelo menos um dos seguintes elementos de formato:
>
> - Arquivo
> - Pasta
> - Fusão
> - Anexo

## <a name="create-a-new-document-type"></a>Criar um novo tipo de documento

Para especificar como os documentos gerados por um formato ER são roteados, você deverá configurar [destinos de ER (Relatórios eletrônicos)](electronic-reporting-destinations.md). Em cada destino de ER configurado para armazenar documentos gerados como arquivos, você deve especificar um tipo de documento da estrutura de gerenciamento de documentos. Diferentes tipos de documentos podem ser usados para rotear documentos gerados por diferentes formatos ER.

1. Adicionar um novo [tipo de documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) para o formato ER que você criou ou importou anteriormente. Na ilustração a seguir, o tipo de documento é **FileX**.
2. Para diferenciar esse tipo de documento de outros tipos de documentos, inclua uma palavra-chave específica em seu nome. Por exemplo, na ilustração a seguir, o nome é **Pasta (LOCAL)**.
3. No campo **Classe**, especifique **Anexar arquivo**.
4. No campo **Grupo**, especifique **Arquivo**.

![Página Tipos de documento](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> Tipos de documentos são específicos da empresa. Para usar um formato ER com um destino configurado em várias empresas, você deve configurar um tipo de documento separado em cada empresa.

## <a name="review-source-code"></a>Revisar código-fonte

Revise o código do método **insertFile()** da classe **ERDocuManagement**. Observe que o evento **AttachingFile()** é gerado enquanto o arquivo gerado é anexado a um registro.


```xpp
/// <summary>
/// Inserts file as attachment in Document Management.
/// </summary>
/// <param name = "_owner">A record as the attachment owner.</param>
/// <param name = "_stream">The file stream.</param>
/// <param name = "_filePath">The file path with name.</param>
/// <param name = "_attachmentName">The name of file attachment.</param>
/// <returns>The reference to inserted file.</returns>
[Hookable(false)]
public DocuRef insertFile(
    Common _owner, 
    System.IO.Stream _stream, 
    str _filePath, 
    str _attachmentName, 
    DocuTypeId _docuTypeId)
{
    DocuRef docuRef;
    if (_stream)
    {
        DocuType::createDefaults();
        if (!this.isDocuTypeValid(_docuTypeId))
        {
            throw error(strFmt("@ElectronicReporting:DocuTypeIsNotValid", _docuTypeId));
        }
        var args = ERDocuManagementAttachingFileEventArgs::construct(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        ERDocuManagementEvents::onAttachingFile(args);
        if (args.isHandled())
        {
            docuRef = args.getDocuRef();
        }
        else
        {
            docuRef = this.attachFile(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        }
    }
    return docuRef;
}
```

O evento **AttachingFile()** é gerado quando os seguintes destinos de ER são processados:

- **Arquivar** – Quando este destino é usado, um novo registro para o formato ER executado é criado na tabela ERFormatMappingRunJobTable. O campo **Arquivado** neste registro é definido como **Falso**. Se o formato ER for executado com êxito, o documento gerado será anexado a esse registro e o evento **AttachingFile()** será gerado. O tipo de documento selecionado nesse destino de ER determina o local de armazenamento do arquivo anexado (Armazenamento do Microsoft Azure ou uma pasta do Microsoft SharePoint).
- **Arquivo de trabalho** – Quando este destino é usado, um novo registro para o formato ER executado é criado na tabela ERFormatMappingRunJobTable. O campo **Arquivado** neste registro é definido como **Verdadeiro**. Se o formato ER for executado com êxito, o documento gerado será anexado a esse registro e o evento **AttachingFile()** será gerado. O tipo de documento configurado nos parâmetros ER determina o local de armazenamento do arquivo anexado (Armazenamento do Azure ou uma pasta do SharePoint).

![Página de parâmetros de relatórios eletrônicos](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a>Configurar um destino de ER

1. Configure o destino arquivado para um dos elementos mencionados anteriormente (arquivo, pasta, fusão ou anexo) do formato ER que você criou ou importou. Para obter orientação, consulte [Configurar destinos ER](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).
2. Use o tipo de documento que você adicionou anteriormente para o destino configurado. (Para o exemplo neste tópico, o tipo de documento é **FileX**.)

![Caixa de diálogo de configurações de destino](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a>Modificar o código-fonte

1. Adicione uma nova classe ao projeto do Microsoft Visual Studio e escreva código para se inscrever ao evento **AttachingFile()** que foi mencionado anteriormente. (Para obter mais informações sobre o padrão de extensibilidade usado, consulte [Responder usando EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Por exemplo, na nova classe, escreva o código que executa as seguintes ações:

    1. Armazene arquivos gerados em uma pasta do sistema de arquivos local do servidor que executa o serviço Application Object Server (AOS).
    2. Armazene esses arquivos gerados somente quando o novo tipo de documento (por exemplo, o tipo **FileX** que possui a palavra-chave "(LOCAL)" em seu nome) for usado enquanto um arquivo estiver anexado ao registro no trabalho de execução de ER.

    ```xpp
    class ERDocuSubscriptionSample
    {
        void new()
        {
        }
        [SubscribesTo(classStr(ERDocuManagementEvents), 
        staticDelegateStr(ERDocuManagementEvents, 
        attachingFile))]
        public static void ERDocuManagementEvents_attachingFile(ERDocuManagementAttachingFileEventArgs _args)
        {
            if (!_args.isHandled())
            {
                DocuType docuType = DocuType::find(_args.getDocuTypeId());
                if (strContains(docuType.Name, '(LOCAL)'))
                {
                    _args.markAsHandled();
                    var stream = _args.getStream();
                    if (stream.CanSeek)
                    {
                        stream.Seek(0, System.IO.SeekOrigin::Begin);
                    }
                    using (var localStream = System.IO.File::OpenWrite(@'c:\0\' + _args.getAttachmentName()))
                    {
                        stream.CopyTo(localStream);
                    }
                }
            }
        }
    }
    ```

2. Reconstrua seu projeto.

## <a name="run-the-er-format-that-you-created-or-imported"></a>Executar o formato ER que você criou ou importou

1. Execute o formato ER que você criou ou importou.
2. Vá para **Administração da organização \> Relatório eletrônico \> Trabalhos de relatórios eletrônicos**. Localize o registro que foi criado para esse trabalho de execução e que tenha o arquivo gerado anexado a ele.
3. Explore a pasta local **C:\\0** para encontrar o mesmo arquivo gerado.

## <a name="additional-resources"></a>Recursos adicionais

- [Destinos de relatório eletrônico (ER)](electronic-reporting-destinations.md)
- [Home page da extensibilidade](../extensibility/extensibility-home-page.md)
