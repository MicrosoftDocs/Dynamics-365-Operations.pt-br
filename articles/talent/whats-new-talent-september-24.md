---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (24 de setembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
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
ms.openlocfilehash: 24526a5884c6c5d30d1f49077b88a24364aa4365
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517342"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-24-2018"></a><span data-ttu-id="52710-103">Novidades ou alterações no Dynamics 365 for Talent Core HR (24 de setembro de 2018)</span><span class="sxs-lookup"><span data-stu-id="52710-103">What's new or changed in Dynamics 365 for Talent Core HR (September 24, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="52710-104">**Compilação 8.1.1015.0**</span><span class="sxs-lookup"><span data-stu-id="52710-104">**Build 8.1.1015.0**</span></span>

<span data-ttu-id="52710-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="52710-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="currency-added-to-benefits"></a><span data-ttu-id="52710-106">Moeda adicionada aos benefícios</span><span class="sxs-lookup"><span data-stu-id="52710-106">Currency added to Benefits</span></span>

<span data-ttu-id="52710-107">Os planos de benefício foram atualizados para incluir a moeda do benefício.</span><span class="sxs-lookup"><span data-stu-id="52710-107">Benefit plans have been updated to include the currency of the benefit.</span></span> <span data-ttu-id="52710-108">Este novo campo também está disponível em benefícios do trabalhador inscrito.</span><span class="sxs-lookup"><span data-stu-id="52710-108">This new field is also available on worker enrolled benefits.</span></span> <span data-ttu-id="52710-109">Este novo campo faz parte do privilégio de segurança Manter benefícios e Exibir uma lista de benefícios.</span><span class="sxs-lookup"><span data-stu-id="52710-109">This new field is part of the Maintain benefits and View a list of benefits security privilege.</span></span>

## <a name="update-proration-process--leave-and-absence"></a><span data-ttu-id="52710-110">Atualizar processo de rateio – Licença e ausência</span><span class="sxs-lookup"><span data-stu-id="52710-110">Update proration process – Leave and Absence</span></span>

<span data-ttu-id="52710-111">As organizações concedem folgas de maneira diferente com base em quando os funcionários entraram e saíram da empresa.</span><span class="sxs-lookup"><span data-stu-id="52710-111">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="52710-112">Para funcionários que estão deixando de trabalhar na organização, pode ser necessários alguns deles encerrem a concessão na data de demissão, enquanto outros dependem do último dia de trabalho para interromper o processo de competência.</span><span class="sxs-lookup"><span data-stu-id="52710-112">For employees leaving the organization, some may need to end the award on the termination date, while others rely on the last day worked to stop the accrual process.</span></span> <span data-ttu-id="52710-113">Essas alterações oferecem às organizações a capacidade de escolher quando encerrar a inscrição durante o processo de demissão.</span><span class="sxs-lookup"><span data-stu-id="52710-113">These changes provide organizations the ability to choose when to end enrollment during the termination process.</span></span> <span data-ttu-id="52710-114">As novas opções são parte dos privilégios para Demitir um trabalhador e Demitir um trabalhador do autoatendimento para gerentes.</span><span class="sxs-lookup"><span data-stu-id="52710-114">These new options are part of the privileges for Terminate a worker and Terminate a worker from manager self service.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="52710-115">Outras alterações</span><span class="sxs-lookup"><span data-stu-id="52710-115">Other changes</span></span>

<span data-ttu-id="52710-116">Esta versão inclui várias correções de bug adicionais.</span><span class="sxs-lookup"><span data-stu-id="52710-116">This release includes several additional bug fixes.</span></span>

## <a name="known-issue"></a><span data-ttu-id="52710-117">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="52710-117">Known Issue</span></span>

-   <span data-ttu-id="52710-118">**Problema:** ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. **Solução alternativa:** antes de abrir a página do anexo, verifique se os quadros de fatos na página **Trabalhador** estão fechados.</span><span class="sxs-lookup"><span data-stu-id="52710-118">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the fact boxes on the **Worker** page are closed.</span></span> <span data-ttu-id="52710-119">Se os quadros de fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões de anexos serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="52710-119">If the fact boxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="52710-120">(Esse problema será corrigido na próxima atualização de plataforma.)</span><span class="sxs-lookup"><span data-stu-id="52710-120">(This issue will be fixed in the next platform update.)</span></span>
