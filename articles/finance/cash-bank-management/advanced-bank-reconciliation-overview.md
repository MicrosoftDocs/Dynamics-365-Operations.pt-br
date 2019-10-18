---
title: Visão geral da reconciliação bancária avançada
description: Este artigo descreve o fluxo do processo de reconciliação avançado do banco. O recurso avançado de reconciliação bancária permite que você importe os extratos bancários que podem ser reconciliados automaticamente nas transações bancárias.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39ddfde74aaff8bf5d8f22861b7595be1f9b89a9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176444"
---
# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="d4862-104">Visão geral da reconciliação bancária avançada</span><span class="sxs-lookup"><span data-stu-id="d4862-104">Advanced bank reconciliation overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d4862-105">Este artigo descreve o fluxo do processo de reconciliação avançado do banco.</span><span class="sxs-lookup"><span data-stu-id="d4862-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="d4862-106">O recurso avançado de reconciliação bancária permite que você importe os extratos bancários que podem ser reconciliados automaticamente nas transações bancárias.</span><span class="sxs-lookup"><span data-stu-id="d4862-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="d4862-107">O recurso de reconciliação bancária avançada permite que você importe extratos bancários.</span><span class="sxs-lookup"><span data-stu-id="d4862-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="d4862-108">O extrato bancário importado pode ser reconciliado automaticamente nas transações bancárias.</span><span class="sxs-lookup"><span data-stu-id="d4862-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="d4862-109">Veja as etapas do fluxo de reconciliação bancária avançada.</span><span class="sxs-lookup"><span data-stu-id="d4862-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="d4862-110">Configurar uma importação de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="d4862-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="d4862-111">Importar extratos bancários por meio da estrutura de entidade de dados.</span><span class="sxs-lookup"><span data-stu-id="d4862-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="d4862-112">Três formatos de extratos bancários típicos são internos: ISO20022, BAI2, e MT940.</span><span class="sxs-lookup"><span data-stu-id="d4862-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="d4862-113">A funcionalidade pode se estendida para qualquer formato.</span><span class="sxs-lookup"><span data-stu-id="d4862-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="d4862-114">Configure uma sequência numérica para a reconciliação bancária avançada e defina as regras de correspondência da reconciliação bancária.</span><span class="sxs-lookup"><span data-stu-id="d4862-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="d4862-115">Uma regra de correspondência de reconciliação é um conjunto de critérios usados para filtrar as linhas do extrato bancário e as linhas de transações bancárias no Microsoft Dynamics 365 Finance durante o processo de reconciliação.</span><span class="sxs-lookup"><span data-stu-id="d4862-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 Finance bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="d4862-116">Dependendo da prática empresarial, você pode configurar mais de uma regra de correspondência para automatizar e otimizar o processo de reconciliação.</span><span class="sxs-lookup"><span data-stu-id="d4862-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="d4862-117">Reconciliar extratos bancários com as transações bancárias do Finance.</span><span class="sxs-lookup"><span data-stu-id="d4862-117">Reconcile bank statements with Finance bank transactions.</span></span>
    -   <span data-ttu-id="d4862-118">Executar a correspondência e a criação automática de diários de reconciliação.</span><span class="sxs-lookup"><span data-stu-id="d4862-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="d4862-119">Visualizar extratos bancários e as transações bancárias do Finance lado a lado.</span><span class="sxs-lookup"><span data-stu-id="d4862-119">View bank statements and Finance bank transactions side by side.</span></span>
    -   <span data-ttu-id="d4862-120">Lance as transações bancárias do Finance automaticamente se elas forem exibidas no extrato bancário, mas não aparecerem no aplicativo Finance.</span><span class="sxs-lookup"><span data-stu-id="d4862-120">Automatically post Finance bank transactions if they appear on a bank statement but don't appear in the Finance app.</span></span>
    -   <span data-ttu-id="d4862-121">Gere um demonstrativo da reconciliação.</span><span class="sxs-lookup"><span data-stu-id="d4862-121">Generate a reconciliation statement.</span></span>





