---
title: Ordem de execução da sincronização inicial entre aplicativos do Finance and Operations e o Common Data Service
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
ms.openlocfilehash: cf444ef1192fed3a6a49282da37374dd8c443356
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769628"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="df702-103">Ordem de execução da sincronização inicial entre aplicativos do Finance and Operations e o Common Data Service</span><span class="sxs-lookup"><span data-stu-id="df702-103">Execution order for initial synchronization of Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df702-104">Antes de usar a integração de dados, você deve criar os dados iniciais necessários para clientes, fornecedores e contatos.</span><span class="sxs-lookup"><span data-stu-id="df702-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="df702-105">Por exemplo, você deseja criar um item **Grupo de Fornecedores** e definir seu valor **Condições de Pagamento** como **Net30**.</span><span class="sxs-lookup"><span data-stu-id="df702-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="df702-106">Nesse caso, antes de tentar criar o item **Grupo de fornecedores**, você deve verificar se **Net30** existe no aplicativo e no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="df702-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both the application and Common Data Service.</span></span> <span data-ttu-id="df702-107">(No futuro, a Microsoft liberará a funcionalidade de plataforma de gravação dupla chamada Sincronização Inicial. Ela fará uma sincronização de dados única entre o aplicativo e o Common Data Service como parte da configuração de gravação dupla.)</span><span class="sxs-lookup"><span data-stu-id="df702-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between the application and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="df702-108">A Microsoft está liberando um mapa de gravação dupla para todos os dados de referência, incluindo **Condições de Pagamento**.</span><span class="sxs-lookup"><span data-stu-id="df702-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="df702-109">Se você já tiver os dados iniciais em um sistema, uma operação de atualização pequena em um registro poderá acionar uma gravação dupla nesse registro.</span><span class="sxs-lookup"><span data-stu-id="df702-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="df702-110">Obedeça à ordem de precedência a seguir e verifique se os dados iniciais estão disponíveis no aplicativo e no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="df702-110">You must follow the following order of precedence and make sure that the initial data is available in the application and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="df702-111">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="df702-111">Vendor</span></span>

<span data-ttu-id="df702-112">Veja a ordem de execução da entidade **Fornecedor**:</span><span class="sxs-lookup"><span data-stu-id="df702-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="df702-113">Grupo de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="df702-113">Vendor group</span></span>

    1. <span data-ttu-id="df702-114">Condições de pagamento</span><span class="sxs-lookup"><span data-stu-id="df702-114">Terms of payment</span></span>

        1. <span data-ttu-id="df702-115">Dia e linhas de pagamento</span><span class="sxs-lookup"><span data-stu-id="df702-115">Payment day and lines</span></span>
        2. <span data-ttu-id="df702-116">Agenda de pagamento</span><span class="sxs-lookup"><span data-stu-id="df702-116">Payment schedule</span></span>

2. <span data-ttu-id="df702-117">Método de pagamento do fornecedor</span><span class="sxs-lookup"><span data-stu-id="df702-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="df702-118">Cliente (Organização)</span><span class="sxs-lookup"><span data-stu-id="df702-118">Customer (Organization)</span></span>

<span data-ttu-id="df702-119">Veja a ordem de execução da entidade **Cliente**:</span><span class="sxs-lookup"><span data-stu-id="df702-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="df702-120">Grupo de clientes</span><span class="sxs-lookup"><span data-stu-id="df702-120">Customer group</span></span>

    1. <span data-ttu-id="df702-121">Condições de pagamento</span><span class="sxs-lookup"><span data-stu-id="df702-121">Terms of payment</span></span>

        1. <span data-ttu-id="df702-122">Dia e linhas de pagamento</span><span class="sxs-lookup"><span data-stu-id="df702-122">Payment day and lines</span></span>
        2. <span data-ttu-id="df702-123">Pagamento</span><span class="sxs-lookup"><span data-stu-id="df702-123">Payment</span></span> 

2. <span data-ttu-id="df702-124">Método de pagamento do cliente</span><span class="sxs-lookup"><span data-stu-id="df702-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="df702-125">Contato (Pessoa)</span><span class="sxs-lookup"><span data-stu-id="df702-125">Contact (Person)</span></span>

<span data-ttu-id="df702-126">Veja a ordem de execução da entidade **Contato**:</span><span class="sxs-lookup"><span data-stu-id="df702-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="df702-127">Cliente</span><span class="sxs-lookup"><span data-stu-id="df702-127">Customer</span></span>
2. <span data-ttu-id="df702-128">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="df702-128">Vendor</span></span>
