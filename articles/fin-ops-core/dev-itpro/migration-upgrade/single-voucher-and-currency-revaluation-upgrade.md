---
title: Atualizar diários de comprovante único e reavaliações de moeda
description: Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar. Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5fa955f4548acc48208d8b151d1eee1fa5e59225
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249040"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="9a91d-104">​Atualizar diários de comprovante único e reavaliações de moeda</span><span class="sxs-lookup"><span data-stu-id="9a91d-104">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a91d-105">Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar.</span><span class="sxs-lookup"><span data-stu-id="9a91d-105">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="9a91d-106">Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611.</span><span class="sxs-lookup"><span data-stu-id="9a91d-106">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="9a91d-107">Siga estas etapas quando fizer o upgrade para o Microsoft Dynamics 365 for Operations versão 1611.</span><span class="sxs-lookup"><span data-stu-id="9a91d-107">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="9a91d-108">Antes de atualizar para o Finance and Operations, execute os processos de reavaliação de moeda estrangeira para Contas a receber e Contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="9a91d-108">Before you upgrade to Finance and Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="9a91d-109">Defina o campo **Método** para **Data da fatura**.</span><span class="sxs-lookup"><span data-stu-id="9a91d-109">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="9a91d-110">É criada uma transação de reavaliação que reverte a última reavaliação de moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="9a91d-110">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="9a91d-111">Portanto, as transações em aberto são avaliadas em sua moeda de contabilização original.</span><span class="sxs-lookup"><span data-stu-id="9a91d-111">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="9a91d-112">Atualize para a versão 1611.</span><span class="sxs-lookup"><span data-stu-id="9a91d-112">Upgrade to version 1611.</span></span>
3.  <span data-ttu-id="9a91d-113">Execute novamente os processos de reavaliação de contas a receber e contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="9a91d-113">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="9a91d-114">Agora, defina o campo **Método** para **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="9a91d-114">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="9a91d-115">É criada uma nova transação de reavaliação baseada nas taxas de câmbio atuais.</span><span class="sxs-lookup"><span data-stu-id="9a91d-115">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="9a91d-116">Essa transação registra o ganho/perda não realizado e a conta de razão contábil correta.</span><span class="sxs-lookup"><span data-stu-id="9a91d-116">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>