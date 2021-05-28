---
title: Configurações do princípio de liberação em linhas de BOM não são respeitadas
description: Configurações do princípio de liberação em linhas de lista de materiais (BOM) não são respeitadas.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026271"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a><span data-ttu-id="c8606-103">Configurações do princípio de liberação em linhas de BOM não são respeitadas</span><span class="sxs-lookup"><span data-stu-id="c8606-103">Flushing principle settings on BOM lines aren't respected</span></span>

<span data-ttu-id="c8606-104">Número da base de dados de conhecimento: 4612725</span><span class="sxs-lookup"><span data-stu-id="c8606-104">KB number: 4612725</span></span>

## <a name="symptoms"></a><span data-ttu-id="c8606-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="c8606-105">Symptoms</span></span>

<span data-ttu-id="c8606-106">Este problema ocorre quando o campo **Consumo automático da BOM** na guia **Atualização automática** da página **Parâmetros de controle de produção** estiver definido como *Princípio de liberação*.</span><span class="sxs-lookup"><span data-stu-id="c8606-106">This issue occurs when the **Automatic BOM consumption** field on the **Automatic update** tab of the **Production control parameters** page is set to *Flushing principle*.</span></span> <span data-ttu-id="c8606-107">Esta configuração indica que todas as linhas de BOM (lista de materiais) devem ser consumidas automaticamente quando um pedido de compra é recebido.</span><span class="sxs-lookup"><span data-stu-id="c8606-107">This setting indicates that all bill of materials (BOM) lines should automatically be consumed when a purchase order is received.</span></span> <span data-ttu-id="c8606-108">Se o campo **Princípio de liberação** nas linhas da BOM estiver definido explicitamente como *Manual*, você pode esperar que as linhas da BOM não sejam consumidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c8606-108">If the **Flushing principle** field on BOM lines is explicitly set to *Manual*, you might expect that the BOM lines won't automatically be consumed.</span></span> <span data-ttu-id="c8606-109">No entanto, quando esse problema ocorre, as linhas da BOM em que o campo **Princípio de liberação** estiver definido explicitamente como *Manual*, as linhas da BOM são consumidas automaticamente mesmo assim.</span><span class="sxs-lookup"><span data-stu-id="c8606-109">However, when this issue occurs, BOM lines where the **Flushing principle** field is set to *Manual* are automatically consumed anyway.</span></span>

## <a name="resolution"></a><span data-ttu-id="c8606-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="c8606-110">Resolution</span></span>

<span data-ttu-id="c8606-111">Se esse problema ocorrer, seus parâmetros de controle de produção podem estar configurados para substituir a configuração **Princípio de liberação** nas linhas da BOM.</span><span class="sxs-lookup"><span data-stu-id="c8606-111">If you're experiencing this issue, your production control parameters might be set up to override the **Flushing principle** setting on BOM lines.</span></span> <span data-ttu-id="c8606-112">Na página **Parâmetros de controle de produção**, na guia **Atualização automática**, verifique o valor do campo **Consumo automático da BOM**.</span><span class="sxs-lookup"><span data-stu-id="c8606-112">On the **Production control parameters** page, on the **Automatic update** tab, check the value of the **Automatic BOM consumption** field.</span></span> <span data-ttu-id="c8606-113">Se ele estiver definido como *Sempre*, o sistema ignorará a configuração **Princípio de liberação** em todas as linhas da BOM e sempre liberará as linhas.</span><span class="sxs-lookup"><span data-stu-id="c8606-113">If it's set to *Always*, the system will disregard the **Flushing principle** setting on all BOM lines and will always flush the lines.</span></span> <span data-ttu-id="c8606-114">Para fazer o sistema respeitar a configuração **Princípio de liberação** nas linhas da BOM, mude o valor do campo **Consumo automático da BOM** para *Princípio de liberação*.</span><span class="sxs-lookup"><span data-stu-id="c8606-114">To make the system respect the **Flushing principle** setting on BOM lines, change the value of the **Automatic BOM consumption** field to *Flushing principle*.</span></span>
