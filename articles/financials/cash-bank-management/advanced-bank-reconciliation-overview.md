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
ms.openlocfilehash: 5c76b38e957c1c76a80c76782f45405573b7f191
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842595"
---
# <a name="advanced-bank-reconciliation-overview"></a><span data-ttu-id="f5603-104">Visão geral da reconciliação bancária avançada</span><span class="sxs-lookup"><span data-stu-id="f5603-104">Advanced bank reconciliation overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5603-105">Este artigo descreve o fluxo do processo de reconciliação avançado do banco.</span><span class="sxs-lookup"><span data-stu-id="f5603-105">This article describes the flow for the advanced bank reconciliation process.</span></span> <span data-ttu-id="f5603-106">O recurso avançado de reconciliação bancária permite que você importe os extratos bancários que podem ser reconciliados automaticamente nas transações bancárias.</span><span class="sxs-lookup"><span data-stu-id="f5603-106">The advanced bank reconciliation feature lets you import bank statements that can be automatically reconciled from within bank transactions.</span></span>

<span data-ttu-id="f5603-107">O recurso de reconciliação bancária avançada permite que você importe extratos bancários.</span><span class="sxs-lookup"><span data-stu-id="f5603-107">The advanced bank reconciliation feature lets you import bank statements.</span></span> <span data-ttu-id="f5603-108">O extrato bancário importado pode ser reconciliado automaticamente nas transações bancárias.</span><span class="sxs-lookup"><span data-stu-id="f5603-108">The imported bank statement can then be automatically reconciled from within bank transactions.</span></span> <span data-ttu-id="f5603-109">Veja as etapas do fluxo de reconciliação bancária avançada.</span><span class="sxs-lookup"><span data-stu-id="f5603-109">Here are the steps in the advanced bank reconciliation flow.</span></span>

1.  <span data-ttu-id="f5603-110">Configurar uma importação de extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="f5603-110">Set up a bank statement import.</span></span>
    -   <span data-ttu-id="f5603-111">Importar extratos bancários por meio da estrutura de entidade de dados.</span><span class="sxs-lookup"><span data-stu-id="f5603-111">Import bank statements through the data entity framework.</span></span>
    -   <span data-ttu-id="f5603-112">Três formatos de extratos bancários típicos são internos: ISO20022, BAI2, e MT940.</span><span class="sxs-lookup"><span data-stu-id="f5603-112">Three typical bank statement formats are built in: ISO20022, BAI2, and MT940.</span></span>
    -   <span data-ttu-id="f5603-113">A funcionalidade pode se estendida para qualquer formato.</span><span class="sxs-lookup"><span data-stu-id="f5603-113">The functionality can be extended to any format.</span></span>

2.  <span data-ttu-id="f5603-114">Configure uma sequência numérica para a reconciliação bancária avançada e defina as regras de correspondência da reconciliação bancária.</span><span class="sxs-lookup"><span data-stu-id="f5603-114">Set up a number sequence to use for advanced bank reconciliation, and define the bank reconciliation matching rules.</span></span>
    -   <span data-ttu-id="f5603-115">Uma regra de correspondência de reconciliação é um conjunto de critérios usados para filtrar as linhas do extrato bancário e as linhas de transação bancária no Microsoft Dynamics 365 for Finance and Operations durante o processo de reconciliação.</span><span class="sxs-lookup"><span data-stu-id="f5603-115">A reconciliation matching rule is a set of criteria that are used to filter bank statement lines and Microsoft Dynamics 365 for Finance and Operations bank transaction lines during the reconciliation process.</span></span> <span data-ttu-id="f5603-116">Dependendo da prática empresarial, você pode configurar mais de uma regra de correspondência para automatizar e otimizar o processo de reconciliação.</span><span class="sxs-lookup"><span data-stu-id="f5603-116">Depending on your business practice, you can set up more than one matching rule to automate and optimize your reconciliation process.</span></span>

3.  <span data-ttu-id="f5603-117">Reconciliar extratos bancários com as transações bancárias do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f5603-117">Reconcile bank statements with Finance and Operations bank transactions.</span></span>
    -   <span data-ttu-id="f5603-118">Executar a correspondência e a criação automática de diários de reconciliação.</span><span class="sxs-lookup"><span data-stu-id="f5603-118">Perform automatic matching and creation of reconciliation journals.</span></span>
    -   <span data-ttu-id="f5603-119">Visualizar extratos bancários e as transações bancárias do Finance and Operations lado a lado.</span><span class="sxs-lookup"><span data-stu-id="f5603-119">View bank statements and Finance and Operations bank transactions side by side.</span></span>
    -   <span data-ttu-id="f5603-120">Lance automaticamente as transações bancárias do Finance and Operations se forem exibidas no extrato bancário, mas não forem exibidas no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f5603-120">Automatically post Finance and Operations bank transactions if they appear on a bank statement but don't appear in Finance and Operations.</span></span>
    -   <span data-ttu-id="f5603-121">Gere um demonstrativo da reconciliação.</span><span class="sxs-lookup"><span data-stu-id="f5603-121">Generate a reconciliation statement.</span></span>





