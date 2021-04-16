---
title: Sincronizar data e hora em trabalhos de importação
description: Use fusos horários UTC em trabalhos de importação para evitar problemas com conversões de fuso horário.
author: Sunil-Garg
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c0ec805a20a525989e0133e5dffb29ce3fed39
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748660"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a><span data-ttu-id="53225-103">Sincronizar data e hora em trabalhos de importação</span><span class="sxs-lookup"><span data-stu-id="53225-103">Synchronize date and time in import jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="53225-104">É importante definir o fuso horário do trabalho de importação como o tempo universal coordenado (UTC).</span><span class="sxs-lookup"><span data-stu-id="53225-104">It's important to set the time zone for your import job to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="53225-105">Você poderá ver datas e horas inesperadas nos dados importados se usar uma configuração diferente.</span><span class="sxs-lookup"><span data-stu-id="53225-105">You might see unexpected dates and times in your imported data if you use a different setting.</span></span> <span data-ttu-id="53225-106">Sem a configuração correta, o processo de importação converte a data UTC no formato local e, em seguida, converte-a novamente.</span><span class="sxs-lookup"><span data-stu-id="53225-106">Without the correct setting, the import process converts the UTC date to the local format, and then system settings converts it again.</span></span>

<span data-ttu-id="53225-107">Essa conversão dupla causa a alteração de datas entre os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="53225-107">This dual conversion causes dates to change between applications.</span></span> <span data-ttu-id="53225-108">Por exemplo, a conversão dupla pode fazer com que a data inicial de um funcionário seja diferente entre o Dynamics 365 Human Resources e Dynamics 365 Finance devido a diferenças nos fusos horários locais.</span><span class="sxs-lookup"><span data-stu-id="53225-108">For example, the dual conversion could cause an employee's start date to be different between Dynamics 365 Human Resources and Dynamics 365 Finance due to differences in local time zones.</span></span> <span data-ttu-id="53225-109">A definição do trabalho de importação para o UTC resolve esse problema.</span><span class="sxs-lookup"><span data-stu-id="53225-109">Setting the import job to UTC resolves this problem.</span></span>

1. <span data-ttu-id="53225-110">No Dynamics 365 Finance and Operations, selecione **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="53225-110">In Dynamics 365 Finance and Operations, select **Data management**.</span></span>

2. <span data-ttu-id="53225-111">Selecione **Importar projetos** e então selecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="53225-111">Select **Import projects**, and then select the project.</span></span>

3. <span data-ttu-id="53225-112">Em **Formato da data de origem**, selecione **CSV-Unicode**.</span><span class="sxs-lookup"><span data-stu-id="53225-112">Under **Source date format**, select **CSV-Unicode**.</span></span>

   <span data-ttu-id="53225-113">[![Alterar o formato da data de origem para UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span><span class="sxs-lookup"><span data-stu-id="53225-113">[![Change source date format to UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span></span>

4. <span data-ttu-id="53225-114">Altere o **Fuso horário** para o **Tempo Universal Coordenado** e altere o **Idioma** para **En-US**.</span><span class="sxs-lookup"><span data-stu-id="53225-114">Change **Timezone** to **Coordinated Universal Timezone**, and change **Language** to **En-US**.</span></span>




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]