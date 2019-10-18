---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (24 de setembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6001b3c777be005dfc0b22ca0b64d5c56a56cb1e
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010052"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-september-24-2018"></a><span data-ttu-id="34a28-103">Novidades ou alterações no Dynamics 365 Talent: Core HR (24 de setembro de 2018)</span><span class="sxs-lookup"><span data-stu-id="34a28-103">What's new or changed in Dynamics 365 Talent: Core HR (September 24, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="34a28-104">**Compilação 8.1.1015.0**</span><span class="sxs-lookup"><span data-stu-id="34a28-104">**Build 8.1.1015.0**</span></span>

<span data-ttu-id="34a28-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="34a28-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="currency-added-to-benefits"></a><span data-ttu-id="34a28-106">Moeda adicionada aos benefícios</span><span class="sxs-lookup"><span data-stu-id="34a28-106">Currency added to Benefits</span></span>

<span data-ttu-id="34a28-107">Os planos de benefício foram atualizados para incluir a moeda do benefício.</span><span class="sxs-lookup"><span data-stu-id="34a28-107">Benefit plans have been updated to include the currency of the benefit.</span></span> <span data-ttu-id="34a28-108">Este novo campo também está disponível em benefícios do trabalhador inscrito.</span><span class="sxs-lookup"><span data-stu-id="34a28-108">This new field is also available on worker enrolled benefits.</span></span> <span data-ttu-id="34a28-109">Este novo campo faz parte do privilégio de segurança Manter benefícios e Exibir uma lista de benefícios.</span><span class="sxs-lookup"><span data-stu-id="34a28-109">This new field is part of the Maintain benefits and View a list of benefits security privilege.</span></span>

## <a name="update-proration-process--leave-and-absence"></a><span data-ttu-id="34a28-110">Atualizar processo de rateio – Licença e ausência</span><span class="sxs-lookup"><span data-stu-id="34a28-110">Update proration process – Leave and Absence</span></span>

<span data-ttu-id="34a28-111">As organizações concedem folgas de maneira diferente com base em quando os funcionários entraram e saíram da empresa.</span><span class="sxs-lookup"><span data-stu-id="34a28-111">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="34a28-112">Para funcionários que estão deixando de trabalhar na organização, pode ser necessários alguns deles encerrem a concessão na data de demissão, enquanto outros dependem do último dia de trabalho para interromper o processo de competência.</span><span class="sxs-lookup"><span data-stu-id="34a28-112">For employees leaving the organization, some may need to end the award on the termination date, while others rely on the last day worked to stop the accrual process.</span></span> <span data-ttu-id="34a28-113">Essas alterações oferecem às organizações a capacidade de escolher quando encerrar a inscrição durante o processo de demissão.</span><span class="sxs-lookup"><span data-stu-id="34a28-113">These changes provide organizations the ability to choose when to end enrollment during the termination process.</span></span> <span data-ttu-id="34a28-114">As novas opções são parte dos privilégios para Demitir um trabalhador e Demitir um trabalhador do autoatendimento para gerentes.</span><span class="sxs-lookup"><span data-stu-id="34a28-114">These new options are part of the privileges for Terminate a worker and Terminate a worker from manager self service.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="34a28-115">Outras alterações</span><span class="sxs-lookup"><span data-stu-id="34a28-115">Other changes</span></span>

<span data-ttu-id="34a28-116">Esta versão inclui várias correções de bug adicionais.</span><span class="sxs-lookup"><span data-stu-id="34a28-116">This release includes several additional bug fixes.</span></span>

## <a name="known-issue"></a><span data-ttu-id="34a28-117">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="34a28-117">Known Issue</span></span>

-   <span data-ttu-id="34a28-118">**Problema:** ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. **Solução alternativa:** antes de abrir a página do anexo, verifique se os quadros de fatos na página **Trabalhador** estão fechados.</span><span class="sxs-lookup"><span data-stu-id="34a28-118">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the fact boxes on the **Worker** page are closed.</span></span> <span data-ttu-id="34a28-119">Se os quadros de fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões de anexos serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="34a28-119">If the fact boxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="34a28-120">(Esse problema será corrigido na próxima atualização de plataforma.)</span><span class="sxs-lookup"><span data-stu-id="34a28-120">(This issue will be fixed in the next platform update.)</span></span>
