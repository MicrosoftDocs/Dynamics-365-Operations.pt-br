---
title: Ordens de venda do projeto
description: Este tópico explica como criar ordens de venda baseadas em projeto para projetos por tempo e material.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: 1d54c98a08dc7cccb5cafbbe401d0ce25a276c25
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/12/2019
ms.locfileid: "976628"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a><span data-ttu-id="be9b2-103">Ordens de venda de projeto para projetos por tempo e material</span><span class="sxs-lookup"><span data-stu-id="be9b2-103">Project sales orders for time and material projects</span></span>

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="be9b2-104">Este tópico descreve como criar uma ordem de venda para um projeto.</span><span class="sxs-lookup"><span data-stu-id="be9b2-104">This topic describes how to create a sales order for a project.</span></span> <span data-ttu-id="be9b2-105">As ordens de venda só podem ser criadas para projetos do tipo **tempo e material**.</span><span class="sxs-lookup"><span data-stu-id="be9b2-105">Sales orders can only be created for projects of type **time and material**.</span></span>

<span data-ttu-id="be9b2-106">Se um projeto por tempo e material tiver várias fontes de financiamento em seu contrato, você deverá habilitar o parâmetro **Permitir ordens de venda para projetos com várias fontes de financiamento** na página **Parâmetros de gerenciamento e contabilidade de projetos**.</span><span class="sxs-lookup"><span data-stu-id="be9b2-106">If a time and material project has multiple funding sources on the project contract, you must enable the **Allow sales orders for projects with multiple funding sources** parameter on the **Project management and accounting parameters** page.</span></span> 

> [!NOTE]
> - <span data-ttu-id="be9b2-107">O suporte para ordens de venda de projeto com várias fontes de financiamento está disponível a partir da versão 10.0.2 e posterior do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="be9b2-107">Support for project sales orders with multiple funding sources is available starting with application release 10.0.2 and higher.</span></span>
> - <span data-ttu-id="be9b2-108">O parâmetro para habilitar o suporte para ordens de venda de projeto com várias fontes de financiamento será removido na onda de lançamentos de abril de 2020, após a qual essa funcionalidade será habilitada sempre.</span><span class="sxs-lookup"><span data-stu-id="be9b2-108">The parameter to enable the support for project sales orders with multiple funding sources will be removed in the April 2020 release wave, after which the functionality will always be enabled.</span></span>

<span data-ttu-id="be9b2-109">Você pode criar ordens de venda baseadas em projeto de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="be9b2-109">You can create project-based sales orders in two ways:</span></span>

- <span data-ttu-id="be9b2-110">Acesse o projeto.</span><span class="sxs-lookup"><span data-stu-id="be9b2-110">Go to the project itself.</span></span> <span data-ttu-id="be9b2-111">No Painel de Ação, selecione **Gerenciar > Tarefas do item > Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="be9b2-111">On the Action Pane, select **Manage > Item tasks > Sales order**.</span></span> <span data-ttu-id="be9b2-112">As informações sobre o projeto terão como padrão a ordem de venda do projeto.</span><span class="sxs-lookup"><span data-stu-id="be9b2-112">The project information will default to the sales order from the project.</span></span> <span data-ttu-id="be9b2-113">Se o contrato de projeto tiver mais de uma fonte de financiamento, você precisará selecionar a fonte de financiamento para definir o cliente para a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="be9b2-113">If the project contract has more than one funding source, you will need to select the funding source to set the customer for the sales order.</span></span> <span data-ttu-id="be9b2-114">Se o projeto tiver apenas uma fonte de financiamento, o cliente será definido de forma automática.</span><span class="sxs-lookup"><span data-stu-id="be9b2-114">If there is only one funding source for the project, the customer will be automatically set.</span></span>
- <span data-ttu-id="be9b2-115">Vá para a página de listagem **Todas as ordens de venda** e crie uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="be9b2-115">Go to the **All sales order** list page and create a new sales order.</span></span> <span data-ttu-id="be9b2-116">Você precisará selecionar o projeto para a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="be9b2-116">You will need to select the project for the sales order.</span></span> <span data-ttu-id="be9b2-117">Depois que o projeto for selecionado, o cliente será definido com base na fonte de financiamento ou você terá de selecionar a fonte de financiamento se o contrato do projeto tiver várias.</span><span class="sxs-lookup"><span data-stu-id="be9b2-117">After the project is selected, the customer will be set from the funding source or you will need to select the funding source if the project contract has multiple funding sources.</span></span>

