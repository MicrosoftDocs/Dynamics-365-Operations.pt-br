---
title: Solucionar problemas de atualização e migração para gerenciamento avançado de depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao atualizar e migrar para o gerenciamento avançado de depósito.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f5bfee31ce27e919086f978fb3ff88ca61a65eba
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208078"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a><span data-ttu-id="58fae-103">Solucionar problemas de atualização e migração para gerenciamento avançado de depósito</span><span class="sxs-lookup"><span data-stu-id="58fae-103">Troubleshoot upgrade and migration to advanced warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58fae-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao atualizar e migrar para o gerenciamento avançado de depósito.</span><span class="sxs-lookup"><span data-stu-id="58fae-104">This topic describes how to fix common issues that you might encounter while you upgrade and migrate to advanced warehouse management.</span></span>

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a><span data-ttu-id="58fae-105">Recebo a seguinte mensagem de erro: "java.security.cert.certPathValidatorException: A âncora de confiança para o caminho de certificação não foi encontrada."</span><span class="sxs-lookup"><span data-stu-id="58fae-105">I receive the following error message: "java.security.cert.certPathValidatorException: Trust anchor for certification path is not found."</span></span>

### <a name="issue-description"></a><span data-ttu-id="58fae-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="58fae-106">Issue description</span></span>

<span data-ttu-id="58fae-107">Você recebe esta mensagem de erro no aplicativo do depósito, porque os certificados autoassinados não são confiáveis no Android 8 ou posterior em ambientes locais.</span><span class="sxs-lookup"><span data-stu-id="58fae-107">You receive this error message in the warehouse app, because self-signed certificates aren't trusted on Android 8+ in on-premises environments.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="58fae-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="58fae-108">Issue resolution</span></span>

<span data-ttu-id="58fae-109">Use uma autoridade de certificação (CA) externa (pública).</span><span class="sxs-lookup"><span data-stu-id="58fae-109">Use an external (public) certifying authority (CA).</span></span> <span data-ttu-id="58fae-110">Uma correção para esse problema está disponível na versão 1.9.0.0 do aplicativo de depósito.</span><span class="sxs-lookup"><span data-stu-id="58fae-110">A fix for this issue is available in version 1.9.0.0 of the warehouse app.</span></span> <span data-ttu-id="58fae-111">Para obter mais informações sobre esse problema e como corrigi-lo, consulte [Solucionar problemas de conexão do aplicativo de depósito](troubleshoot-warehouse-app-connection.md).</span><span class="sxs-lookup"><span data-stu-id="58fae-111">For more information about this issue and how to fix it, see [Troubleshoot warehouse app connection issues](troubleshoot-warehouse-app-connection.md).</span></span>

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a><span data-ttu-id="58fae-112">Qual é o processo aprovado para passar do depósito básico para o avançado?</span><span class="sxs-lookup"><span data-stu-id="58fae-112">What is the approved process for moving from basic warehousing to advanced warehousing?</span></span>

### <a name="issue-description"></a><span data-ttu-id="58fae-113">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="58fae-113">Issue description</span></span>

<span data-ttu-id="58fae-114">No momento, você está executando o gerenciamento de estoque e usando a funcionalidade de estoque básico e deseja passar para o depósito avançado para aproveitar as vantagens de dispositivos móveis, ciclos e trabalho.</span><span class="sxs-lookup"><span data-stu-id="58fae-114">You're currently running under stock/inventory management and using basic stock functionality, and you want to move to advanced warehousing to take advantage of mobile devices, waves, and work.</span></span> <span data-ttu-id="58fae-115">Contudo, você está tendo problemas ao tentar fazer essa mudança.</span><span class="sxs-lookup"><span data-stu-id="58fae-115">However, you're experiencing issues when you try to make this move.</span></span> <span data-ttu-id="58fae-116">Por exemplo, você não pode alterar seus produtos para que usem dimensões de armazenamento (site, depósito e local), porque os produtos têm transações em relação a eles.</span><span class="sxs-lookup"><span data-stu-id="58fae-116">For example, you can't change your products so that they use storage dimensions (site, warehouse, and location), because the products have transactions against them.</span></span> <span data-ttu-id="58fae-117">Portanto, você deve conhecer o processo aprovado para passar do depósito básico para o avançado.</span><span class="sxs-lookup"><span data-stu-id="58fae-117">Therefore, you must learn the approved process for moving from basic warehousing to advanced warehousing.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="58fae-118">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="58fae-118">Issue resolution</span></span>

<span data-ttu-id="58fae-119">Para obter mais informações sobre o processo de mudança do depósito básico para o avançado, consulte as seguintes postagens e documentação no blog:</span><span class="sxs-lookup"><span data-stu-id="58fae-119">For more information about the process for moving from basic warehousing to advanced warehousing, see the following blog posts and documentation:</span></span>

- [<span data-ttu-id="58fae-120">Habilitar processo de gerenciamento de depósito para itens e depósitos existentes</span><span class="sxs-lookup"><span data-stu-id="58fae-120">Enable warehouse management process for existing items and warehouses</span></span>](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [<span data-ttu-id="58fae-121">Migração do Microsoft Dynamics AX WMS para o novo depósito R3 e funcionalidade de transporte</span><span class="sxs-lookup"><span data-stu-id="58fae-121">Migration of Microsoft Dynamics AX WMS to new R3 warehouse and transportation functionality</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [<span data-ttu-id="58fae-122">Migração de item WMSI/WMS2</span><span class="sxs-lookup"><span data-stu-id="58fae-122">WMSI/WMS2 item migration</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [<span data-ttu-id="58fae-123">Atualizar o gerenciamento de depósito do Microsoft Dynamics AX 2012 para o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="58fae-123">Upgrade warehouse management from Microsoft Dynamics AX 2012 to Supply Chain Management</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]