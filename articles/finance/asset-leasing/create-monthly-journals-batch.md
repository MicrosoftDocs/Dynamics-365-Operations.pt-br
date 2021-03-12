---
title: Criar entradas de diário mensal em um lote
description: Este tópico explica como criar entradas de diário em um lote para ajudar a aumentar a eficiência quando despesas mensais de arrendamento são registradas.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7f46f289c58c32c535dd20fb510cf2812625c49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971319"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a><span data-ttu-id="84e1c-103">Criar entradas de diário mensal em um lote</span><span class="sxs-lookup"><span data-stu-id="84e1c-103">Create monthly journal entries in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84e1c-104">Este tópico explica como criar entradas de diário em um lote para ajudar a aumentar a eficiência quando despesas mensais de arrendamento são registradas.</span><span class="sxs-lookup"><span data-stu-id="84e1c-104">This topic explains how to create journal entries in a batch to help increase efficiency when monthly lease expenses are recorded.</span></span> <span data-ttu-id="84e1c-105">O processamento em lotes pode ser usado para criar entradas de diário a partir de vários agendamentos.</span><span class="sxs-lookup"><span data-stu-id="84e1c-105">Batch processing can be used to create journal entries from multiple schedules.</span></span> <span data-ttu-id="84e1c-106">Essas entradas de diário podem incluir pagamentos de arrendamento, amortização de passivos, amortização de ativos de direito de uso (DDU) e despesas de custo de execução.</span><span class="sxs-lookup"><span data-stu-id="84e1c-106">These journal entries can include lease payments, liability amortization, right-of-use (ROU) asset amortization, and executory cost expenses.</span></span> <span data-ttu-id="84e1c-107">Você também pode usar o processamento em lotes para fazer o reconhecimento inicial de vários arrendamentos ao mesmo tempo ou para criar ajustes de transição para vários arrendamentos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="84e1c-107">You can also use batch processing to do the initial recognition of multiple leases at the same time, or to create transition adjustments for multiple leases at the same time.</span></span>

<span data-ttu-id="84e1c-108">Para configurar um trabalho em lotes ou para processar faturas de pagamento, depreciação ou juros para vários arrendamentos, acesse **Arrendamento de ativos \> Periódico \> Criação de jornal em lote**.</span><span class="sxs-lookup"><span data-stu-id="84e1c-108">To set up a batch job, or to process payment invoices, depreciation, or interest for multiple leases, go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span> <span data-ttu-id="84e1c-109">Na caixa de diálogo exibida, é possível selecionar o agendamento a partir do qual as entradas de diário devem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="84e1c-109">In the dialog box that appears, you can select the schedule that the journal entries should be created from.</span></span> <span data-ttu-id="84e1c-110">Você também pode especificar se o processo em lote deve ser executado para entidades, grupos de arrendamentos ou registros de arrendamento específicos.</span><span class="sxs-lookup"><span data-stu-id="84e1c-110">You can also specify whether the batch process should be run for specific entities, lease groups, or lease books.</span></span>

> [!NOTE]
> <span data-ttu-id="84e1c-111">Transações subsequentes, como agendamentos de amortização de passivos, pagamentos, depreciação e despesas, serão lançadas somente depois que o reconhecimento inicial dos arrendamentos correspondentes for lançado.</span><span class="sxs-lookup"><span data-stu-id="84e1c-111">Subsequent transactions, such as liability amortization schedules, payments, depreciation, and expenses, will be posted only after the initial recognition for corresponding leases is posted.</span></span>
>
> <span data-ttu-id="84e1c-112">As entradas de diário são criadas, mas não serão lançadas até que você selecione o comando **Executar**.</span><span class="sxs-lookup"><span data-stu-id="84e1c-112">The journal entries are created, but they won't be posted until you select the **Run** command.</span></span>
