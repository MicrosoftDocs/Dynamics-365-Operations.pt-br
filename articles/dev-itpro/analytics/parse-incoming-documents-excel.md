---
title: Analisar documentos de entrada no Microsoft Excel
description: "Este tópico fornece informações sobre como criar formatos de relatórios eletrônicos (ER) para analisar o conteúdo contido em arquivos de entrada do Microsoft Excel."
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: 001e287590b9f43ed38de803bcace3a25a6f6637
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2018

---

# <a name="parse-incoming-microsoft-excel-files"></a><span data-ttu-id="81591-103">Analise arquivos de entrada no Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="81591-103">Parse incoming Microsoft Excel files</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="81591-104">Você pode criar formatos de relatórios eletrônicos (ER) para analisar arquivos de entrada do Microsoft Excel que representam dados nas pastas de trabalho do Microsoft Excel (arquivos no formato XLSX).</span><span class="sxs-lookup"><span data-stu-id="81591-104">You can design Electronic reporting (ER) formats to parse incoming Microsoft Excel files that represent data in Microsoft Excel workbooks (files in XLSX format).</span></span> <span data-ttu-id="81591-105">Você pode usar o conteúdo desses arquivos para atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="81591-105">You can then use the content from these files to update application data.</span></span> <span data-ttu-id="81591-106">Isso será útil se você:</span><span class="sxs-lookup"><span data-stu-id="81591-106">This is useful if you:</span></span>

-   <span data-ttu-id="81591-107">Criar um novo modelo e formato e testá-los em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="81591-107">Design a new model and format and want to test them at run-time.</span></span> <span data-ttu-id="81591-108">Nesse caso, o Excel simulará os dados reais do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="81591-108">In this case, Excel will simulate the actual application data.</span></span>
-   <span data-ttu-id="81591-109">Gerenciar dados além do aplicativo no Excel e desejar importar esses dados para enviar um relatório específico.</span><span class="sxs-lookup"><span data-stu-id="81591-109">Manage data beyond your application in Excel and want to import this data to submit a specific report.</span></span>

<span data-ttu-id="81591-110">Para saber mais sobre esse recurso, execute as guias de tarefa **Dados de ER de um arquivo do Microsoft Excel (Parte 1: Criar formato)** e **Importar dados de ER de um arquivo do Microsoft Excel (Parte 2: Importar dados)** (partes do processo comercial 7.5.4.3 Adquirir/desenvolver serviço de TI/componentes de solução (10677)).</span><span class="sxs-lookup"><span data-stu-id="81591-110">To learn more about this feature, play the task guides **ER Import data from a Microsoft Excel file (Part 1: Design format)** and **ER Import data from a Microsoft Excel file (Part 2: Import data)** (parts of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span> <span data-ttu-id="81591-111">Essas guias de tarefas mostram como o arquivo de entrada do Excel pode ser analisado usando o formato de ER para importar informações de documentos de entrada e atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="81591-111">These task guides walk through how the incoming Excel file can be parsed by using the ER format to import information from incoming documents and update application data.</span></span> <span data-ttu-id="81591-112">É possível baixar os arquivos da guia de tarefas no [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="81591-112">You can download the task guide files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

<span data-ttu-id="81591-113">Baixe os arquivos a seguir para concluir as guias de tarefas mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="81591-113">Download the following files to complete the task guides mentioned above.</span></span>

| <span data-ttu-id="81591-114">Descrição do conteúdo</span><span class="sxs-lookup"><span data-stu-id="81591-114">Content description</span></span>                        | <span data-ttu-id="81591-115">Arquivo</span><span class="sxs-lookup"><span data-stu-id="81591-115">File</span></span>                                                                       |
---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="81591-116">Arquivo de entrada no formato .XLSX - modelo</span><span class="sxs-lookup"><span data-stu-id="81591-116">Incoming file in .XLSX format - template</span></span>   | [<span data-ttu-id="81591-117">1099import-template.xlsx</span><span class="sxs-lookup"><span data-stu-id="81591-117">1099import-template.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)  |
| <span data-ttu-id="81591-118">Arquivo de entrada no formato .XLSX - dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="81591-118">Incoming file in .XLSX format - sample data</span></span>| [<span data-ttu-id="81591-119">1099import-data.xlsx</span><span class="sxs-lookup"><span data-stu-id="81591-119">1099import-data.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)     |

<span data-ttu-id="81591-120">Se você ainda não tiver executado esta guia de tarefas, [ER Criar configurações necessárias para importar dados de um arquivo externo](./tasks/er-required-configurations-import-data.md) no aplicativo atual Dynamics 365 for Finance and Operation, baixe o arquivo a seguir.</span><span class="sxs-lookup"><span data-stu-id="81591-120">If you have not yet played the following task guide, [ER Create required configurations to import data from an external file](./tasks/er-required-configurations-import-data.md) in the current Dynamics 365 for Finance and Operation application, download the following file.</span></span>

| <span data-ttu-id="81591-121">Descrição do conteúdo</span><span class="sxs-lookup"><span data-stu-id="81591-121">Content description</span></span>                        | <span data-ttu-id="81591-122">Arquivo</span><span class="sxs-lookup"><span data-stu-id="81591-122">File</span></span>                                                                       |
---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="81591-123">Configuração de modelo ER</span><span class="sxs-lookup"><span data-stu-id="81591-123">ER model configuration</span></span>                     | [<span data-ttu-id="81591-124">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="81591-124">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)            |


