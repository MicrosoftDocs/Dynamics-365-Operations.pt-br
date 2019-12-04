---
title: Analise documentos de entrada no formato Excel
description: Este tópico fornece informações sobre como criar formatos de Relatórios eletrônicos (ER) para analisar o conteúdo contido em arquivos de entrada do Microsoft Excel.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 3f83271327df186d407516ff1a197800ffc8c78c
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249347"
---
# <a name="parse-incoming-documents-in-excel-format"></a><span data-ttu-id="b401c-103">Analisar documentos de entrada no formato Excel</span><span class="sxs-lookup"><span data-stu-id="b401c-103">Parse incoming documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b401c-104">Você pode criar formatos de relatórios eletrônicos (ER) para analisar arquivos de entrada do Microsoft Excel que representam dados nas pastas de trabalho do Microsoft Excel (arquivos no formato XLSX).</span><span class="sxs-lookup"><span data-stu-id="b401c-104">You can design Electronic reporting (ER) formats to parse incoming Microsoft Excel files that represent data in Microsoft Excel workbooks (files in XLSX format).</span></span> <span data-ttu-id="b401c-105">Você pode usar o conteúdo desses arquivos para atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b401c-105">You can then use the content from these files to update application data.</span></span> <span data-ttu-id="b401c-106">Isso será útil se você:</span><span class="sxs-lookup"><span data-stu-id="b401c-106">This is useful if you:</span></span>

- <span data-ttu-id="b401c-107">Criar um novo modelo e formato e testá-los em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b401c-107">Design a new model and format and want to test them at run-time.</span></span> <span data-ttu-id="b401c-108">Nesse caso, o Excel simulará os dados reais do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b401c-108">In this case, Excel will simulate the actual application data.</span></span>
- <span data-ttu-id="b401c-109">Gerenciar dados além do aplicativo no Excel e desejar importar esses dados para enviar um relatório específico.</span><span class="sxs-lookup"><span data-stu-id="b401c-109">Manage data beyond your application in Excel and want to import this data to submit a specific report.</span></span>

<span data-ttu-id="b401c-110">Para saber mais sobre esse recurso, execute as guias de tarefa **ER Importar dados de um arquivo do Microsoft Excel (Parte 1: Criar formato)** e **Importar dados de ER de um arquivo do Microsoft Excel (Parte 2: Importar dados)** (partes do processo comercial 7.5.4.3 Adquirir/desenvolver serviço de TI/componentes de solução (10677)).</span><span class="sxs-lookup"><span data-stu-id="b401c-110">To learn more about this feature, play the task guides **ER Import data from a Microsoft Excel file (Part 1: Design format)** and **ER Import data from a Microsoft Excel file (Part 2: Import data)** (parts of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span> <span data-ttu-id="b401c-111">Essas guias de tarefas mostram como o arquivo de entrada do Excel pode ser analisado usando o formato de ER para importar informações de documentos de entrada e atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b401c-111">These task guides walk through how the incoming Excel file can be parsed by using the ER format to import information from incoming documents and update application data.</span></span> <span data-ttu-id="b401c-112">É possível baixar os arquivos da guia de tarefas no [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="b401c-112">You can download the task guide files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

<span data-ttu-id="b401c-113">Baixe os arquivos a seguir para concluir as guias de tarefas mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b401c-113">Download the following files to complete the task guides mentioned above.</span></span>

| <span data-ttu-id="b401c-114">Descrição do conteúdo</span><span class="sxs-lookup"><span data-stu-id="b401c-114">Content description</span></span>                         | <span data-ttu-id="b401c-115">Arquivo</span><span class="sxs-lookup"><span data-stu-id="b401c-115">File</span></span>                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="b401c-116">Arquivo de entrada no formato .XLSX - modelo</span><span class="sxs-lookup"><span data-stu-id="b401c-116">Incoming file in .XLSX format - template</span></span>    | [<span data-ttu-id="b401c-117">1099import-template.xlsx</span><span class="sxs-lookup"><span data-stu-id="b401c-117">1099import-template.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
| <span data-ttu-id="b401c-118">Arquivo de entrada no formato .XLSX - dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="b401c-118">Incoming file in .XLSX format - sample data</span></span> | [<span data-ttu-id="b401c-119">1099import-data.xlsx</span><span class="sxs-lookup"><span data-stu-id="b401c-119">1099import-data.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)     |

<span data-ttu-id="b401c-120">Se você ainda não tiver executado este guia de tarefas, [ER Criar configurações necessárias para importar dados de um arquivo externo](./tasks/er-required-configurations-import-data.md) no aplicativo atual do Finance and Operations, baixe o arquivo a seguir.</span><span class="sxs-lookup"><span data-stu-id="b401c-120">If you have not yet played the following task guide, [ER Create required configurations to import data from an external file](./tasks/er-required-configurations-import-data.md) in the current Finance and Operations application, download the following file.</span></span>

| <span data-ttu-id="b401c-121">Descrição do conteúdo</span><span class="sxs-lookup"><span data-stu-id="b401c-121">Content description</span></span>    | <span data-ttu-id="b401c-122">Arquivo</span><span class="sxs-lookup"><span data-stu-id="b401c-122">File</span></span>                                                            |
|------------------------|-----------------------------------------------------------------|
| <span data-ttu-id="b401c-123">Configuração de modelo ER</span><span class="sxs-lookup"><span data-stu-id="b401c-123">ER model configuration</span></span> | [<span data-ttu-id="b401c-124">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="b401c-124">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |