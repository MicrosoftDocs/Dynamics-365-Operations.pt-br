---
title: Habilitar o cálculo de impostos atrasados no diário
description: Este tópico explica como usar o recurso **Habilitar o cálculo de impostos atrasados no diário** para melhorar o desempenho de cálculo de impostos quando o volume de linhas do diário é enorme.
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
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176375"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a><span data-ttu-id="b8b79-103">Habilitar o cálculo de impostos atrasados no diário</span><span class="sxs-lookup"><span data-stu-id="b8b79-103">Enable delayed tax calculation on journal</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="b8b79-104">Este tópico explica como usar o recurso **Habilitar o cálculo de impostos atrasados no diário** para melhorar o desempenho de cálculo de impostos quando o volume de linhas do diário é enorme.</span><span class="sxs-lookup"><span data-stu-id="b8b79-104">This topic explains how to use the **Enable delayed tax calculation on journal** feature to improve tax calculation performance when the volume of journal lines is huge.</span></span>

<span data-ttu-id="b8b79-105">O comportamento atual de cálculo de impostos no diário é acionado em tempo real quando o usuário atualiza campos relacionadas a impostos, por exemplo, o grupo de impostos sobre vendas/grupo de impostos do item.</span><span class="sxs-lookup"><span data-stu-id="b8b79-105">Current sales tax calculation behavior on journal is real-time triggered when user updates tax related fields, e.g. sales tax group/item sales tax group.</span></span> <span data-ttu-id="b8b79-106">Qualquer atualização em nível de linha do diário recalculará o valor do imposto em todas as linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="b8b79-106">Any update at journal line level will re-calculate tax amount on all journal lines.</span></span> <span data-ttu-id="b8b79-107">Isso ajuda a usuário a ver o valor do imposto calculado em tempo real, mas também poderá causar problemas de desempenho, se o volume de linhas do diário for muito grande.</span><span class="sxs-lookup"><span data-stu-id="b8b79-107">It helps user to see real-time calculated tax amount but it could also bring performance issue if  the volume of journal lines is huge.</span></span>

<span data-ttu-id="b8b79-108">Este recurso fornece uma opção para atrasar o cálculo do imposto para resolver o problema de desempenho.</span><span class="sxs-lookup"><span data-stu-id="b8b79-108">This feature provides an option to delay tax calculation to solve performance issue.</span></span> <span data-ttu-id="b8b79-109">Se o recurso estiver ativado, o valor do imposto será calculado somente quando o usuário clicar no comando “Imposto” ou lançar o diário.</span><span class="sxs-lookup"><span data-stu-id="b8b79-109">If this feature is turned on, tax amount will only be calculated when user clicks "Sales Tax" command or posts the journal.</span></span>

<span data-ttu-id="b8b79-110">O usuário pode ativar/desativar o parâmetro em três níveis:</span><span class="sxs-lookup"><span data-stu-id="b8b79-110">User can turn on/off the parameter at three levels:</span></span>
- <span data-ttu-id="b8b79-111">Por entidade legal</span><span class="sxs-lookup"><span data-stu-id="b8b79-111">By legal entity</span></span>
- <span data-ttu-id="b8b79-112">Por nome do diário</span><span class="sxs-lookup"><span data-stu-id="b8b79-112">By journal name</span></span>
- <span data-ttu-id="b8b79-113">Por cabeçalho do diário</span><span class="sxs-lookup"><span data-stu-id="b8b79-113">By journal header</span></span>

<span data-ttu-id="b8b79-114">O sistema assumirá o valor do parâmetro no cabeçalho do diário como o final.</span><span class="sxs-lookup"><span data-stu-id="b8b79-114">System will take the parameter value on journal header as final.</span></span> <span data-ttu-id="b8b79-115">O valor do parâmetro no cabeçalho do diário usará como padrão o nome do diário.</span><span class="sxs-lookup"><span data-stu-id="b8b79-115">Parameter value on journal header will be defaulted from journal name.</span></span> <span data-ttu-id="b8b79-116">O valor do parâmetro no nome de diário usará como padrão o parâmetro de contabilidade quando o nome do diário for criado.</span><span class="sxs-lookup"><span data-stu-id="b8b79-116">Parameter value on journal name will be defaulted from general ledger parameter when the journal name is created.</span></span>

<span data-ttu-id="b8b79-117">Os campos "Valor real do imposto" e "Valor do imposto calculado" no diário ficarão ocultos se esse parâmetro estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="b8b79-117">"Actual sales tax amount" and "Calculated sales tax amount" fields on journal will be hided if this parameter is turned on.</span></span> <span data-ttu-id="b8b79-118">O objetivo disso é não confundir o usuário porque o valor desses dois campos sempre mostrará 0, até que o usuário dispare o cálculo do imposto.</span><span class="sxs-lookup"><span data-stu-id="b8b79-118">The purpose is not to confuse user because the value of these two fields will always show 0 before user trigger the tax calculation.</span></span>

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a><span data-ttu-id="b8b79-119">Habilitar o cálculo de impostos atrasados por entidade legal</span><span class="sxs-lookup"><span data-stu-id="b8b79-119">Enable delayed tax calculation by legal entity</span></span>

1. <span data-ttu-id="b8b79-120">Vá para **Contabilidade > Configuração do razão > Parâmetros da contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="b8b79-120">Go to **General ledger > Ledger setup > General ledger parameters**</span></span>
2. <span data-ttu-id="b8b79-121">Clique na guia **Imposto**</span><span class="sxs-lookup"><span data-stu-id="b8b79-121">Click **Sales tax** tab</span></span>
3. <span data-ttu-id="b8b79-122">Na Guia Rápida **Geral**, localize o parâmetro **Cálculo de impostos atrasados**, ative-o ou desative-o</span><span class="sxs-lookup"><span data-stu-id="b8b79-122">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a><span data-ttu-id="b8b79-123">Habilitar o cálculo de impostos atrasados por nome do diário</span><span class="sxs-lookup"><span data-stu-id="b8b79-123">Enable delayed tax calculation by journal name</span></span>

1. <span data-ttu-id="b8b79-124">Vá para **Contabilidade > Configuração do diário > Nomes de diário**.</span><span class="sxs-lookup"><span data-stu-id="b8b79-124">Go to **General ledger > Journal setup > Journal names**</span></span>
2. <span data-ttu-id="b8b79-125">Na Guia Rápida **Geral**, localize o parâmetro **Cálculo de impostos atrasados**, ative-o ou desative-o</span><span class="sxs-lookup"><span data-stu-id="b8b79-125">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a><span data-ttu-id="b8b79-126">Habilitar o cálculo de impostos atrasados por diário</span><span class="sxs-lookup"><span data-stu-id="b8b79-126">Enable delayed tax calculation by journal</span></span>

1. <span data-ttu-id="b8b79-127">Vá para **Contabilidade > Entradas de diário > Diários gerais**.</span><span class="sxs-lookup"><span data-stu-id="b8b79-127">Go to **General ledger > Journal entries > General journals**</span></span>
2. <span data-ttu-id="b8b79-128">Clique em **Novo**</span><span class="sxs-lookup"><span data-stu-id="b8b79-128">Click **New**</span></span>
3. <span data-ttu-id="b8b79-129">Selecione um nome de diário</span><span class="sxs-lookup"><span data-stu-id="b8b79-129">Select a journal name</span></span>
4. <span data-ttu-id="b8b79-130">Clique em **Configuração**</span><span class="sxs-lookup"><span data-stu-id="b8b79-130">Click **Setup**</span></span>
5. <span data-ttu-id="b8b79-131">Localize o parâmetro **Cálculo de impostos atrasados**, ative-o ou desative-o</span><span class="sxs-lookup"><span data-stu-id="b8b79-131">Find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-header.png)
