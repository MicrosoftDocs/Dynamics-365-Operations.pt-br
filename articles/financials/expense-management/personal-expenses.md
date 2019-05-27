---
title: Despesas pessoais em um relatório de despesas
description: Este tópico explica os dois métodos para lidar com as despesas pessoais de um trabalhador no Microsoft Dynamics 365 for Finance and Operations.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a6b6c505e7dc5e6544658b00d9f59e6062353608
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564730"
---
# <a name="personal-expenses-on-an-expense-report"></a><span data-ttu-id="eacd6-103">Despesas pessoais em um relatório de despesas</span><span class="sxs-lookup"><span data-stu-id="eacd6-103">Personal expenses on an expense report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eacd6-104">Durante viagens de trabalho, os trabalhadores às vezes podem colocar despesas pessoais em seus cartões de crédito corporativos.</span><span class="sxs-lookup"><span data-stu-id="eacd6-104">During business travel, workers might sometimes charge personal expenses to their corporate credit cards.</span></span> <span data-ttu-id="eacd6-105">Se você não definir um processo para lidar com despesas pessoais, o processo de aprovação de relatórios de despesas poderá ser interrompido quando os trabalhadores enviarem seus relatórios de despesas discriminadas.</span><span class="sxs-lookup"><span data-stu-id="eacd6-105">If you don't define a process for handling personal expenses, the approval process for expense reports might be disrupted when workers submit their itemized expense reports.</span></span> 

<span data-ttu-id="eacd6-106">No Microsoft Dynamics 365 for Finance and Operations, há dois métodos para lidar com as despesas pessoais de um trabalhador:</span><span class="sxs-lookup"><span data-stu-id="eacd6-106">In Microsoft Dynamics 365 for Finance and Operations, there are two methods for handling a worker's personal expenses:</span></span>

- <span data-ttu-id="eacd6-107">**Pagas pelo funcionário** – sua organização não paga as despesas pessoais que aparecem na fatura do cartão de crédito corporativo.</span><span class="sxs-lookup"><span data-stu-id="eacd6-107">**Paid by employee** – Your organization doesn't pay personal expenses that appear on the bill for the corporate credit card.</span></span> <span data-ttu-id="eacd6-108">Em vez disso, um relatório é criado, mostrando as despesas pessoais juntamente com as despesas corporativas que foram cobradas no cartão de crédito corporativo.</span><span class="sxs-lookup"><span data-stu-id="eacd6-108">Instead, it creates a report that shows personal expenses together with the corporate expenses that were charged to the corporate credit card.</span></span>
- <span data-ttu-id="eacd6-109">**Pagas pela empresa** – sua organização paga toda a fatura do cartão de crédito corporativo e depois debita as despesas pessoais da conta do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="eacd6-109">**Paid by company** – Your organization pays the whole bill for the corporate credit card and then debits the worker's account for the personal expenses.</span></span>

<span data-ttu-id="eacd6-110">Você pode selecionar o método que sua organização usa na página **Parâmetros de gerenciamento de despesas**.</span><span class="sxs-lookup"><span data-stu-id="eacd6-110">You can select the method that your organization uses on the **Expense management parameters** page.</span></span>
