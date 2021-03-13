---
title: ​Atualizar diários de comprovante único e reavaliações de moeda
description: Este tópico descreve como atualizar diários de comprovante único e reavaliações de moeda.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3504c01a4ed1571866fd2a0cd83eef86a57d684a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127294"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="1c525-103">​Atualizar diários de comprovante único e reavaliações de moeda</span><span class="sxs-lookup"><span data-stu-id="1c525-103">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1c525-104">Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar.</span><span class="sxs-lookup"><span data-stu-id="1c525-104">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="1c525-105">Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611.</span><span class="sxs-lookup"><span data-stu-id="1c525-105">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="1c525-106">Siga estas etapas quando fizer o upgrade para o Microsoft Dynamics 365 for Operations versão 1611.</span><span class="sxs-lookup"><span data-stu-id="1c525-106">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="1c525-107">Antes de atualizar para o Finance and Operations, execute os processos de reavaliação de moeda estrangeira para Contas a receber e Contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="1c525-107">Before you upgrade to Finance and Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="1c525-108">Defina o campo **Método** para **Data da fatura**.</span><span class="sxs-lookup"><span data-stu-id="1c525-108">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="1c525-109">É criada uma transação de reavaliação que reverte a última reavaliação de moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="1c525-109">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="1c525-110">Portanto, as transações em aberto são avaliadas em sua moeda de contabilização original.</span><span class="sxs-lookup"><span data-stu-id="1c525-110">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="1c525-111">Atualize para a versão 1611.</span><span class="sxs-lookup"><span data-stu-id="1c525-111">Upgrade to version 1611.</span></span>
3.  <span data-ttu-id="1c525-112">Execute novamente os processos de reavaliação de contas a receber e contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="1c525-112">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="1c525-113">Agora, defina o campo **Método** para **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="1c525-113">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="1c525-114">É criada uma nova transação de reavaliação baseada nas taxas de câmbio atuais.</span><span class="sxs-lookup"><span data-stu-id="1c525-114">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="1c525-115">Essa transação registra o ganho/perda não realizado e a conta de razão contábil correta.</span><span class="sxs-lookup"><span data-stu-id="1c525-115">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>
