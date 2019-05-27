---
title: Modificar formatos de relatório eletrônico ao reaplicar modelos do Excel
description: Este tópico fornece informações sobre como modificar o formato de relatório eletrônico (ER) usado para gerar documentos comerciais reaplicando um modelo Excel modificado.
author: NickSelin
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8707f7b184bb66648edd0e48672c5514a0a5caf1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544998"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a><span data-ttu-id="2281f-103">Modificar formatos de relatório eletrônico ao reaplicar modelos do Excel</span><span class="sxs-lookup"><span data-stu-id="2281f-103">Modify Electronic reporting formats by reapplying Excel templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2281f-104">A ferramenta de relatório eletrônico (ER) é usada para gerar documentos comerciais em um formato eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2281f-104">The Electronic reporting (ER) tool is used to generate business documents in an electronic format.</span></span> <span data-ttu-id="2281f-105">Para gerar um documento comercial, crie um formato de ER e use o designer de ER para definir o layout do documento comercial e especificar os dados a serem incluídos nele.</span><span class="sxs-lookup"><span data-stu-id="2281f-105">To generate a business document, you must create an ER format, and then use the ER designer to define the layout of the business document and specify the data that should be included in it.</span></span> <span data-ttu-id="2281f-106">Você pode executar o formato de ER para gerar o documento comercial.</span><span class="sxs-lookup"><span data-stu-id="2281f-106">You can then run the ER format to generate the business document.</span></span>

<span data-ttu-id="2281f-107">A ferramenta de ER pode ser usada para gerar documentos comerciais como arquivos do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="2281f-107">The ER tool can be used to generate business documents as Microsoft Excel files.</span></span> <span data-ttu-id="2281f-108">Você pode usar um documento Excel como um modelo para esses documentos.</span><span class="sxs-lookup"><span data-stu-id="2281f-108">You can use an Excel document as a template for these documents.</span></span> <span data-ttu-id="2281f-109">Para definir o layout do documento no designer de ER, você pode importar o conteúdo do documento em Excel a ser usado como um modelo no formato de ER definido.</span><span class="sxs-lookup"><span data-stu-id="2281f-109">To define the document layout in the ER designer, you can import the contents of the Excel document that you want to use as a template into the defined ER format.</span></span> <span data-ttu-id="2281f-110">Para obter detalhes e praticar este cenário, reproduza a guia de tarefas **Criar uma configuração ER para gerar relatórios no formato OPENXML** (parte do processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)).</span><span class="sxs-lookup"><span data-stu-id="2281f-110">For more details, and to practice this scenario, play the task guide **ER Design a configuration for generating reports in OPENXML format** (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span>

<span data-ttu-id="2281f-111">Se você editar o documento do Excel usado como um modelo para um documento comercial, a nova funcionalidade de ER permitirá reaplicar o modelo atualizado ao formato de ER.</span><span class="sxs-lookup"><span data-stu-id="2281f-111">If you edit the Excel document that is used as a template for a business document, new ER functionality lets you reapply the updated template to the ER format.</span></span> <span data-ttu-id="2281f-112">O formato de ER é atualizado de modo que adote o modelo atualizado.</span><span class="sxs-lookup"><span data-stu-id="2281f-112">The ER format is then updated so that it adheres to the updated template.</span></span> <span data-ttu-id="2281f-113">Para obter mais detalhes sobre essa funcionalidade, reproduza a guia de tarefas **ER Modificar um formato ao reaplicar um modelo do Excel** (parte do processo comercial Adquirir/Desenvolver componentes de solução/serviço de TI (10683)).</span><span class="sxs-lookup"><span data-stu-id="2281f-113">For more details about this functionality, play the task guide **ER Modify a format by reapplying an Excel template** (part of the 7.5.5.3 Acquire/Develop IT service/solution components (10683) business process).</span></span> <span data-ttu-id="2281f-114">Na etapa da guia de tarefas onde você importa um modelo atualizado, use o modelo modificado do arquivo Excel de relatório de pagamento, SampleVendPaymWsReport2, como modelo.</span><span class="sxs-lookup"><span data-stu-id="2281f-114">In the task guide step where you import an updated template, use the modified template of the Payment Report Excel file, SampleVendPaymWsReport2, as a template.</span></span>
