---
title: Habilitar o cálculo de impostos atrasados nos diários
description: Este tópico explica como ativar o recurso Cálculo de impostos atrasados para ajudar a melhorar o desempenho dos cálculos de impostos quando o número de linhas do diário é muito grande.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d4ce0343ac766b30d532be0866a381dc520fd462
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977134"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a><span data-ttu-id="44aa8-103">Habilitar o cálculo de impostos atrasados nos diários</span><span class="sxs-lookup"><span data-stu-id="44aa8-103">Enable delayed tax calculation on journals</span></span>
[!include [banner](../includes/banner.md)]


<span data-ttu-id="44aa8-104">Este tópico explica como você pode adiar o cálculo do imposto sobre vendas nos diários.</span><span class="sxs-lookup"><span data-stu-id="44aa8-104">This topic explains how you can delay sales tax calculation on journals.</span></span> <span data-ttu-id="44aa8-105">Esse recurso ajuda a melhorar o desempenho dos cálculos de impostos quando existem muitas linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="44aa8-105">This capability helps improve the performance of tax calculations when there are many journal lines.</span></span>

<span data-ttu-id="44aa8-106">Por padrão, os valores do imposto sobre vendas nas linhas do diário são calculados sempre que os campos relacionados ao imposto são atualizados.</span><span class="sxs-lookup"><span data-stu-id="44aa8-106">By default, sales tax amounts on journal lines are calculated whenever tax-related fields are updated.</span></span> <span data-ttu-id="44aa8-107">Esses campos incluem os campos para grupos de impostos e grupos de impostos sobre itens.</span><span class="sxs-lookup"><span data-stu-id="44aa8-107">These fields include the fields for sales tax groups and item sales tax groups.</span></span> <span data-ttu-id="44aa8-108">Qualquer atualização em uma linha do diário faz com que os valores dos impostos sejam recalculados para todas as linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="44aa8-108">Any update to a journal line causes tax amounts to be recalculated for all journal lines.</span></span> <span data-ttu-id="44aa8-109">Embora esse comportamento ajude o usuário a ver os valores dos impostos calculados em tempo real, também poderá afetar o desempenho se o número de linhas do diário for muito grande.</span><span class="sxs-lookup"><span data-stu-id="44aa8-109">Although this behavior helps user see tax amounts calculated in real time, it can also affect performance if the number of journal lines is very large.</span></span>

<span data-ttu-id="44aa8-110">O recurso Cálculo de impostos atrasados permite adiar o cálculo de impostos em diários e, portanto, ajuda a corrigir problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="44aa8-110">The Delayed tax calculation feature lets you delay tax calculation on journals and therefore helps fix performance issues.</span></span> <span data-ttu-id="44aa8-111">Quando esse recurso é ativado, os valores do imposto são calculados apenas quando um usuário seleciona **Imposto** ou lança o diário.</span><span class="sxs-lookup"><span data-stu-id="44aa8-111">When this feature is turned on, tax amounts are calculated only when a user selects **Sales Tax** or posts the journal.</span></span>

<span data-ttu-id="44aa8-112">Você pode adiar o cálculo dos impostos em três níveis:</span><span class="sxs-lookup"><span data-stu-id="44aa8-112">You can delay the calculation of sales taxes at three levels:</span></span>

- <span data-ttu-id="44aa8-113">Pessoa jurídica em geral</span><span class="sxs-lookup"><span data-stu-id="44aa8-113">Legal entity</span></span>
- <span data-ttu-id="44aa8-114">Nome do diário</span><span class="sxs-lookup"><span data-stu-id="44aa8-114">Journal name</span></span>
- <span data-ttu-id="44aa8-115">Cabeçalho do diário</span><span class="sxs-lookup"><span data-stu-id="44aa8-115">Journal header</span></span>

<span data-ttu-id="44aa8-116">O sistema prioriza a configuração do cabeçalho do diário.</span><span class="sxs-lookup"><span data-stu-id="44aa8-116">The system gives priority to the setting for the journal header.</span></span> <span data-ttu-id="44aa8-117">Por padrão, essa configuração é obtida do nome do diário.</span><span class="sxs-lookup"><span data-stu-id="44aa8-117">By default, this setting is taken from the journal name.</span></span> <span data-ttu-id="44aa8-118">Por padrão, a configuração para o nome do diário é obtida na página **Parâmetros da contabilidade** quando o nome do diário é criado.</span><span class="sxs-lookup"><span data-stu-id="44aa8-118">By default, the setting for the journal name is taken from the setting on the **General ledger parameters** page when the journal name is created.</span></span> <span data-ttu-id="44aa8-119">As seções a seguir explicam como ativar o cálculo de impostos atrasados para entidades legais, nomes de diários e cabeçalhos de diários.</span><span class="sxs-lookup"><span data-stu-id="44aa8-119">The following sections explain how to turn on delayed tax calculation for legal entities, journal names, and journal headers.</span></span>

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a><span data-ttu-id="44aa8-120">Ativar cálculo de impostos atrasados no nível da entidade legal</span><span class="sxs-lookup"><span data-stu-id="44aa8-120">Turn on delayed tax calculation at the legal entity level</span></span>

1. <span data-ttu-id="44aa8-121">Vá para **Contabilidade \> Configuração do razão \> Parâmetros da contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="44aa8-121">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="44aa8-122">Na guia **Imposto**, na Guia Rápida **Geral**, defina a opção **Cálculo de impostos atrasados** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="44aa8-122">On the **Sales tax** tab, on the **General** FastTab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Imagem dos parâmetros da contabilidade](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a><span data-ttu-id="44aa8-124">Ativar cálculo de impostos atrasados no nível do nome do diário</span><span class="sxs-lookup"><span data-stu-id="44aa8-124">Turn on delayed tax calculation at the journal name level</span></span>

1. <span data-ttu-id="44aa8-125">Vá para **Contabilidade \> Configuração do diário \> Nomes de diário**.</span><span class="sxs-lookup"><span data-stu-id="44aa8-125">Go to **General ledger \> Journal setup \> Journal names**.</span></span>
2. <span data-ttu-id="44aa8-126">Na Guia Rápida **Geral**, na seção **Imposto**, defina a opção **Cálculo de impostos atrasados** como **Yes**.</span><span class="sxs-lookup"><span data-stu-id="44aa8-126">On the **General** FastTab, in the **Sales tax** section, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Imagem dos nomes de diário](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a><span data-ttu-id="44aa8-128">Ativar cálculo de impostos atrasados no nível do cabeçalho do diário</span><span class="sxs-lookup"><span data-stu-id="44aa8-128">Turn on delayed tax calculation at the journal header level</span></span>

1. <span data-ttu-id="44aa8-129">Ir para **Contabilidade \> Entradas de diários \> Diários gerais**.</span><span class="sxs-lookup"><span data-stu-id="44aa8-129">Go to **General ledger \> Journal entries \> General journals**.</span></span>
2. <span data-ttu-id="44aa8-130">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="44aa8-130">Select **New**.</span></span>
3. <span data-ttu-id="44aa8-131">Selecione um nome de diário.</span><span class="sxs-lookup"><span data-stu-id="44aa8-131">Select a journal name.</span></span>
4. <span data-ttu-id="44aa8-132">Na guia **Setup**, defina a opção **Cálculo de impostos atrasados** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="44aa8-132">On the **Setup** tab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Imagem da página Diário geral](media/delayed-tax-calculation-journal-header.png)
