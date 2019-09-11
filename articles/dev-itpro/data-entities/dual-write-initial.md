---
title: Ordem de execução para sincronização inicial do Finance and Operations e do Common Data Service
description: Este tópico especifica a ordem de sincronização que você deve seguir para criar os dados iniciais.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1473c3bad55734d5f83ee3e4c1654921b872f3bb
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873119"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="fb5e7-103">Ordem de execução para sincronização inicial do Finance and Operations e do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="fb5e7-103">Execution order for initial synchronization of Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="fb5e7-104">Antes de usar a integração de dados, você deve criar os dados iniciais necessários para clientes, fornecedores e contatos.</span><span class="sxs-lookup"><span data-stu-id="fb5e7-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="fb5e7-105">Por exemplo, você deseja criar um item **Grupo de Fornecedores** e definir seu valor **Condições de Pagamento** como **Net30**.</span><span class="sxs-lookup"><span data-stu-id="fb5e7-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="fb5e7-106">Nesse caso, antes de tentar criar o item **Vendor group**, você deve se certificar de que **Net30** existe no Microsoft Dynamics 365 for Finance and Operations e no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fb5e7-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both Microsoft Dynamics 365 for Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="fb5e7-107">(No futuro, a Microsoft liberará a funcionalidade de plataforma de gravação dupla chamada Sincronização Inicial. Ela fará uma sincronização de dados única entre o Finance and Operations e o Common Data Service como parte da configuração de gravação dupla.)</span><span class="sxs-lookup"><span data-stu-id="fb5e7-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="fb5e7-108">A Microsoft está liberando um mapa de gravação dupla para todos os dados de referência, incluindo **Condições de Pagamento**.</span><span class="sxs-lookup"><span data-stu-id="fb5e7-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="fb5e7-109">Se você já tiver os dados iniciais em um sistema, uma operação de atualização pequena em um registro poderá acionar uma gravação dupla nesse registro.</span><span class="sxs-lookup"><span data-stu-id="fb5e7-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="fb5e7-110">Obedeça a ordem de precedência a seguir e verifique se os dados iniciais estão disponíveis no Finance and Operations e no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fb5e7-110">You must follow the following order of precedence and make sure that the initial data is available in both Finance and Operations and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="fb5e7-111">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="fb5e7-111">Vendor</span></span>

<span data-ttu-id="fb5e7-112">Veja a ordem de execução da entidade **Fornecedor**:</span><span class="sxs-lookup"><span data-stu-id="fb5e7-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="fb5e7-113">Grupo de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="fb5e7-113">Vendor group</span></span>

    1. <span data-ttu-id="fb5e7-114">Condições de pagamento</span><span class="sxs-lookup"><span data-stu-id="fb5e7-114">Terms of payment</span></span>

        1. <span data-ttu-id="fb5e7-115">Dia e linhas de pagamento</span><span class="sxs-lookup"><span data-stu-id="fb5e7-115">Payment day and lines</span></span>
        2. <span data-ttu-id="fb5e7-116">Agenda de pagamento</span><span class="sxs-lookup"><span data-stu-id="fb5e7-116">Payment schedule</span></span>

2. <span data-ttu-id="fb5e7-117">Método de pagamento do fornecedor</span><span class="sxs-lookup"><span data-stu-id="fb5e7-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="fb5e7-118">Cliente (Organização)</span><span class="sxs-lookup"><span data-stu-id="fb5e7-118">Customer (Organization)</span></span>

<span data-ttu-id="fb5e7-119">Veja a ordem de execução da entidade **Cliente**:</span><span class="sxs-lookup"><span data-stu-id="fb5e7-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="fb5e7-120">Grupo de clientes</span><span class="sxs-lookup"><span data-stu-id="fb5e7-120">Customer group</span></span>

    1. <span data-ttu-id="fb5e7-121">Condições de pagamento</span><span class="sxs-lookup"><span data-stu-id="fb5e7-121">Terms of payment</span></span>

        1. <span data-ttu-id="fb5e7-122">Dia e linhas de pagamento</span><span class="sxs-lookup"><span data-stu-id="fb5e7-122">Payment day and lines</span></span>
        2. <span data-ttu-id="fb5e7-123">Pagamento</span><span class="sxs-lookup"><span data-stu-id="fb5e7-123">Payment</span></span> 

2. <span data-ttu-id="fb5e7-124">Método de pagamento do cliente</span><span class="sxs-lookup"><span data-stu-id="fb5e7-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="fb5e7-125">Contato (Pessoa)</span><span class="sxs-lookup"><span data-stu-id="fb5e7-125">Contact (Person)</span></span>

<span data-ttu-id="fb5e7-126">Veja a ordem de execução da entidade **Contato**:</span><span class="sxs-lookup"><span data-stu-id="fb5e7-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="fb5e7-127">Cliente</span><span class="sxs-lookup"><span data-stu-id="fb5e7-127">Customer</span></span>
2. <span data-ttu-id="fb5e7-128">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="fb5e7-128">Vendor</span></span>
