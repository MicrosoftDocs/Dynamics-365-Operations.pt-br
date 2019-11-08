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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: f65118b6a7393ced9d80c30fad7540a7b27da6c7
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569075"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a><span data-ttu-id="32f69-103">Especificar um local de armazenamento personalizado para os documentos gerados</span><span class="sxs-lookup"><span data-stu-id="32f69-103">Specify a custom storage location for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="32f69-104">A interface de programação de aplicativos (API) da estrutura de relatórios eletrônicos (ER) permite estender a lista de locais de armazenamento para documentos gerados pelos formatos ER.</span><span class="sxs-lookup"><span data-stu-id="32f69-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="32f69-105">Este tópico inclui uma visão geral das tarefas principais que você deve concluir para adicionar um local de armazenamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="32f69-105">This topic includes an overview of the main tasks that you must complete to add a custom storage location.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32f69-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="32f69-106">Prerequisites</span></span>

<span data-ttu-id="32f69-107">Você deve implantar uma topologia que dê suporte à compilação contínua.</span><span class="sxs-lookup"><span data-stu-id="32f69-107">You must deploy a topology that supports continuous build.</span></span> <span data-ttu-id="32f69-108">(Para obter mais informações, consulte [Implantar topologias com suporte à contínua automação de compilações e testes](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) Você deve ter acesso a essa topologia para uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="32f69-108">(For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="32f69-109">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="32f69-109">Electronic reporting developer</span></span>
- <span data-ttu-id="32f69-110">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="32f69-110">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="32f69-111">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="32f69-111">System administrator</span></span>

<span data-ttu-id="32f69-112">Você também deve ter acesso ao ambiente de desenvolvimento para essa topologia.</span><span class="sxs-lookup"><span data-stu-id="32f69-112">You must also have access to the development environment for this topology.</span></span>

## <a name="create-or-import-an-er-format-configuration"></a><span data-ttu-id="32f69-113">Criar ou importar uma configuração de formato ER</span><span class="sxs-lookup"><span data-stu-id="32f69-113">Create or import an ER format configuration</span></span>

<span data-ttu-id="32f69-114">Na topologia atual, [crie um novo formato de ER](tasks/er-format-configuration-2016-11.md) para gerar documentos aos quais você planeja adicionar um local de armazenamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="32f69-114">In the current topology, [create a new ER format](tasks/er-format-configuration-2016-11.md) to generate documents that you plan to add a custom storage location for.</span></span> <span data-ttu-id="32f69-115">Como alternativa, [importe um formato ER existente para essa topologia](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="32f69-115">Alternatively, [import an existing ER format into this topology](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Página do designer de formatos](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> <span data-ttu-id="32f69-117">O formato ER que você cria ou importa deve conter pelo menos um dos seguintes elementos de formato:</span><span class="sxs-lookup"><span data-stu-id="32f69-117">The ER format that you create or import must contain at least one of the following format elements:</span></span>
>
> - <span data-ttu-id="32f69-118">Arquivo</span><span class="sxs-lookup"><span data-stu-id="32f69-118">File</span></span>
> - <span data-ttu-id="32f69-119">Pasta</span><span class="sxs-lookup"><span data-stu-id="32f69-119">Folder</span></span>
> - <span data-ttu-id="32f69-120">Fusão</span><span class="sxs-lookup"><span data-stu-id="32f69-120">Merger</span></span>
> - <span data-ttu-id="32f69-121">Anexo</span><span class="sxs-lookup"><span data-stu-id="32f69-121">Attachment</span></span>

## <a name="create-a-new-document-type"></a><span data-ttu-id="32f69-122">Criar um novo tipo de documento</span><span class="sxs-lookup"><span data-stu-id="32f69-122">Create a new document type</span></span>

<span data-ttu-id="32f69-123">Para especificar como os documentos gerados por um formato ER são roteados, você deve configurar [destinos de ER](electronic-reporting-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="32f69-123">To specify how documents that an ER format generates are routed, you must configure [ER destinations](electronic-reporting-destinations.md).</span></span> <span data-ttu-id="32f69-124">Em cada destino de ER configurado para armazenar documentos gerados como arquivos, você deve especificar um tipo de documento da estrutura de gerenciamento de documentos.</span><span class="sxs-lookup"><span data-stu-id="32f69-124">In each ER destination that is configured to store generated documents as files, you must specify a document type of the Document management framework.</span></span> <span data-ttu-id="32f69-125">Diferentes tipos de documentos podem ser usados para rotear documentos gerados por diferentes formatos ER.</span><span class="sxs-lookup"><span data-stu-id="32f69-125">Different document types can be used to route documents that different ER formats generate.</span></span>

1. <span data-ttu-id="32f69-126">Adicionar um novo [tipo de documento](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) para o formato ER que você criou ou importou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="32f69-126">Add a new [document type](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) for the ER format that you created or imported earlier.</span></span> <span data-ttu-id="32f69-127">Na ilustração a seguir, o tipo de documento é **FileX**.</span><span class="sxs-lookup"><span data-stu-id="32f69-127">In the illustration that follows, the document type is **FileX**.</span></span>
2. <span data-ttu-id="32f69-128">Para diferenciar esse tipo de documento de outros tipos de documentos, inclua uma palavra-chave específica em seu nome.</span><span class="sxs-lookup"><span data-stu-id="32f69-128">To differentiate this document type from other document types, include a specific keyword in its name.</span></span> <span data-ttu-id="32f69-129">Por exemplo, na ilustração a seguir, o nome é **Pasta (LOCAL)**.</span><span class="sxs-lookup"><span data-stu-id="32f69-129">For example, in the illustration that follows, the name is **(LOCAL) folder**.</span></span>
3. <span data-ttu-id="32f69-130">No campo **Classe**, especifique **Anexar arquivo**.</span><span class="sxs-lookup"><span data-stu-id="32f69-130">In the **Class** field, specify **Attach file**.</span></span>
4. <span data-ttu-id="32f69-131">No campo **Grupo**, especifique **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="32f69-131">In the **Group** field, specify **File**.</span></span>

![Página Tipos de documento](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> <span data-ttu-id="32f69-133">Tipos de documentos são específicos da empresa.</span><span class="sxs-lookup"><span data-stu-id="32f69-133">Document types are company-specific.</span></span> <span data-ttu-id="32f69-134">Para usar um formato ER com um destino configurado em várias empresas, você deve configurar um tipo de documento separado em cada empresa.</span><span class="sxs-lookup"><span data-stu-id="32f69-134">To use an ER format with a configured destination in multiple companies, you must configure a separate document type in each company.</span></span>

## <a name="review-source-code"></a><span data-ttu-id="32f69-135">Revisar código-fonte</span><span class="sxs-lookup"><span data-stu-id="32f69-135">Review source code</span></span>

<span data-ttu-id="32f69-136">Revise o código do método **insertFile()** da classe **ERDocuManagement**.</span><span class="sxs-lookup"><span data-stu-id="32f69-136">Review the code of the **insertFile()** method of the **ERDocuManagement** class.</span></span> <span data-ttu-id="32f69-137">Observe que o evento **AttachingFile()** é gerado enquanto o arquivo gerado é anexado a um registro.</span><span class="sxs-lookup"><span data-stu-id="32f69-137">Notice that the **AttachingFile()** event is raised while the generated file is attached to a record.</span></span>

```
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

<span data-ttu-id="32f69-138">O evento **AttachingFile()** é gerado quando os seguintes destinos de ER são processados:</span><span class="sxs-lookup"><span data-stu-id="32f69-138">The **AttachingFile()** event is raised when the following ER destinations are processed:</span></span>

- <span data-ttu-id="32f69-139">**Arquivar** – Quando este destino é usado, um novo registro para o formato ER executado é criado na tabela ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="32f69-139">**Archive** – When this destination is used, a new record for the ER format that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="32f69-140">O campo **Arquivado** neste registro é definido como **Falso**.</span><span class="sxs-lookup"><span data-stu-id="32f69-140">The **Archived** field in this record is set to **False**.</span></span> <span data-ttu-id="32f69-141">Se o formato ER for executado com êxito, o documento gerado será anexado a esse registro e o evento **AttachingFile()** será gerado.</span><span class="sxs-lookup"><span data-stu-id="32f69-141">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="32f69-142">O tipo de documento selecionado nesse destino de ER determina o local de armazenamento do arquivo anexado (Armazenamento do Microsoft Azure ou uma pasta do Microsoft SharePoint).</span><span class="sxs-lookup"><span data-stu-id="32f69-142">The document type that is selected in this ER destination determines the storage location for the attached file (Microsoft Azure Storage or a Microsoft SharePoint folder).</span></span>
- <span data-ttu-id="32f69-143">**Arquivo de trabalho** – Quando este destino é usado, um novo registro para o formato ER executado é criado na tabela ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="32f69-143">**Job archive** – When this destination is used, a new record for the ER form that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="32f69-144">O campo **Arquivado** neste registro é definido como **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="32f69-144">The **Archived** field in this record is set to **True**.</span></span> <span data-ttu-id="32f69-145">Se o formato ER for executado com êxito, o documento gerado será anexado a esse registro e o evento **AttachingFile()** será gerado.</span><span class="sxs-lookup"><span data-stu-id="32f69-145">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="32f69-146">O tipo de documento configurado nos parâmetros ER determina o local de armazenamento do arquivo anexado (Armazenamento do Azure ou uma pasta do SharePoint).</span><span class="sxs-lookup"><span data-stu-id="32f69-146">The document type that is configured in the ER parameters determines the storage location for the attached file (Azure Storage or a SharePoint folder).</span></span>

![Página de parâmetros de relatórios eletrônicos](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a><span data-ttu-id="32f69-148">Configurar um destino de ER</span><span class="sxs-lookup"><span data-stu-id="32f69-148">Configure an ER destination</span></span>

1. <span data-ttu-id="32f69-149">Configure o destino arquivado para um dos elementos mencionados anteriormente (arquivo, pasta, fusão ou anexo) do formato ER que você criou ou importou.</span><span class="sxs-lookup"><span data-stu-id="32f69-149">Configure the archived destination for one of the previously mentioned elements (file, folder, merger, or attachment) of the ER format that you created or imported.</span></span> <span data-ttu-id="32f69-150">Para obter orientação, consulte [Configurar destinos ER](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span><span class="sxs-lookup"><span data-stu-id="32f69-150">For guidance, see [ER Configure destinations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span></span>
2. <span data-ttu-id="32f69-151">Use o tipo de documento que você adicionou anteriormente para o destino configurado.</span><span class="sxs-lookup"><span data-stu-id="32f69-151">Use the document type that you added earlier for the configured destination.</span></span> <span data-ttu-id="32f69-152">(Para o exemplo neste tópico, o tipo de documento é **FileX**.)</span><span class="sxs-lookup"><span data-stu-id="32f69-152">(For the example in this topic, the document type is **FileX**.)</span></span>

![Caixa de diálogo de configurações de destino](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a><span data-ttu-id="32f69-154">Modificar o código-fonte</span><span class="sxs-lookup"><span data-stu-id="32f69-154">Modify source code</span></span>

1. <span data-ttu-id="32f69-155">Adicione uma nova classe ao projeto do Microsoft Visual Studio e escreva código para se inscrever ao evento **AttachingFile()** que foi mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="32f69-155">Add a new class to your Microsoft Visual Studio project, and write code to subscribe to the **AttachingFile()** event that was mentioned earlier.</span></span> <span data-ttu-id="32f69-156">(Para obter mais informações sobre o padrão de extensibilidade usado, consulte [Responder usando EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Por exemplo, na nova classe, escreva o código que executa as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="32f69-156">(For more information about the extensibility pattern that is used, see [Respond by using EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) For example, in the new class, write code that performs the following actions:</span></span>

    1. <span data-ttu-id="32f69-157">Armazene arquivos gerados em uma pasta do sistema de arquivos local do servidor que executa o serviço Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="32f69-157">Store generated files in a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    2. <span data-ttu-id="32f69-158">Armazene esses arquivos gerados somente quando o novo tipo de documento (por exemplo, o tipo **FileX** que possui a palavra-chave "(LOCAL)" em seu nome) for usado enquanto um arquivo estiver anexado ao registro no trabalho de execução de ER.</span><span class="sxs-lookup"><span data-stu-id="32f69-158">Store these generated files only when the new document type (for example, the **FileX** type that has the "(LOCAL)" keyword in its name) is used while a file is attached to the record in the ER execution job log.</span></span>

    ```
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

2. <span data-ttu-id="32f69-159">Reconstrua seu projeto.</span><span class="sxs-lookup"><span data-stu-id="32f69-159">Rebuild your project.</span></span>

## <a name="run-the-er-format-that-you-created-or-imported"></a><span data-ttu-id="32f69-160">Executar o formato ER que você criou ou importou</span><span class="sxs-lookup"><span data-stu-id="32f69-160">Run the ER format that you created or imported</span></span>

1. <span data-ttu-id="32f69-161">Execute o formato ER que você criou ou importou.</span><span class="sxs-lookup"><span data-stu-id="32f69-161">Execute the ER format that you created or imported.</span></span>
2. <span data-ttu-id="32f69-162">Vá para **Administração da organização \> Relatório eletrônico \> Trabalhos de relatórios eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="32f69-162">Go to **Organization administration \> Electronic reporting \> Electronic reporting jobs**.</span></span> <span data-ttu-id="32f69-163">Localize o registro que foi criado para esse trabalho de execução e que tenha o arquivo gerado anexado a ele.</span><span class="sxs-lookup"><span data-stu-id="32f69-163">Find the record that was created for this execution job, and that has the generated file attached to it.</span></span>
3. <span data-ttu-id="32f69-164">Explore a pasta local **C:\\0** para encontrar o mesmo arquivo gerado.</span><span class="sxs-lookup"><span data-stu-id="32f69-164">Explore the local **C:\\0** folder to find same generated file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="32f69-165">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="32f69-165">Additional resources</span></span>

- [<span data-ttu-id="32f69-166">Destinos de Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="32f69-166">Electronic reporting destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="32f69-167">Home page da extensibilidade</span><span class="sxs-lookup"><span data-stu-id="32f69-167">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
