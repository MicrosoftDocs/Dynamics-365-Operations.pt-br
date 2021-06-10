---
title: Você não pode filtrar itens de planejamento mestre por seus valores de grupo de cobertura relacionados
description: Você não pode filtrar itens de planejamento mestre por seus valores de grupo de cobertura relacionados.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049453"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a><span data-ttu-id="3219f-103">Você não pode filtrar itens de planejamento mestre por seus valores de grupo de cobertura relacionados</span><span class="sxs-lookup"><span data-stu-id="3219f-103">You can't filter master planning items by their related coverage group values</span></span>

<span data-ttu-id="3219f-104">Número da base de dados de conhecimento: 4612572</span><span class="sxs-lookup"><span data-stu-id="3219f-104">KB number: 4612572</span></span>

## <a name="symptoms"></a><span data-ttu-id="3219f-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="3219f-105">Symptoms</span></span>

<span data-ttu-id="3219f-106">Você deseja filtrar os itens que serão incluídos em um trabalho em lote de planejamento mestre, com base nos valores dos registros relacionados da tabela de cobertura do item.</span><span class="sxs-lookup"><span data-stu-id="3219f-106">You want to filter the items that will be included in a master planning batch job, based on the values of related records from the item coverage table.</span></span> <span data-ttu-id="3219f-107">(Por exemplo, você deseja filtrar itens por seu valor **Fornecedor** e/ou **Grupo de cobertura**).</span><span class="sxs-lookup"><span data-stu-id="3219f-107">(For example, you want to filter items by their **Vendor** and/or **Coverage group** value).</span></span> <span data-ttu-id="3219f-108">A configuração do filtro para o trabalho em lote permite criar uma junção da tabela **Itens** à tabela **Cobertura de item** e, em seguida, especificar valores de campo da tabela de cobertura de item em sua consulta.</span><span class="sxs-lookup"><span data-stu-id="3219f-108">The filter setup for the batch job lets you create a join from the **Items** table to the **Item coverage** table, and then specify field values from the item coverage table in your query.</span></span> <span data-ttu-id="3219f-109">Contudo, depois de concluir essa configuração, o sistema ainda cria ordens planejadas para toda a cobertura do item, não apenas para os itens que correspondem aos valores de campo especificados da tabela de cobertura do item.</span><span class="sxs-lookup"><span data-stu-id="3219f-109">However, after you complete this setup, the system still creates planned orders for the whole item coverage, not just for the items that match the specified field values from the item coverage table.</span></span>

## <a name="resolution"></a><span data-ttu-id="3219f-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="3219f-110">Resolution</span></span>

<span data-ttu-id="3219f-111">O filtro de trabalho em lote pode filtrar somente em itens.</span><span class="sxs-lookup"><span data-stu-id="3219f-111">The batch job filter can filter only on items.</span></span> <span data-ttu-id="3219f-112">Embora você possa adicionar uma junção à tabela **Cobertura de item**, as configurações de filtro feitas nessa tabela não afetarão a saída da consulta.</span><span class="sxs-lookup"><span data-stu-id="3219f-112">Although you can add a join to the **Item coverage** table, filter settings that you make against that table won't affect the query output.</span></span> <span data-ttu-id="3219f-113">Em tempo de execução, o sistema executa o planejamento para todos os grupos de cobertura e todas as variações que os itens filtrados possuem.</span><span class="sxs-lookup"><span data-stu-id="3219f-113">At runtime, the system runs planning for all the coverage groups and all the variations that the filtered items have.</span></span> <span data-ttu-id="3219f-114">Depois que um item já está incluído na execução, qualquer grupo de cobertura incluído no filtro de item não afetarão a saída de planejamento.</span><span class="sxs-lookup"><span data-stu-id="3219f-114">After an item is already included in the run, any coverage groups that are included in the item filter a won't affect the planning output.</span></span>
