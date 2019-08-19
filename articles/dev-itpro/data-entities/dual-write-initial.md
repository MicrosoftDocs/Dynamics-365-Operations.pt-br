---
title: Ordem de execução para sincronização inicial do Finance and Operations e do Common Data Service
description: Esse tópico especifica a ordem de sincronização que você deve seguir para criar os dados iniciais.
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
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797289"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="95078-103">Ordem de execução para sincronização inicial do Finance and Operations e do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="95078-103">Execution order for initial sychronization of Finance and Operations and Common Data Service</span></span>

<span data-ttu-id="95078-104">Antes de usar a integração de dados, você deve criar os dados iniciais necessários para clientes, fornecedores e contatos.</span><span class="sxs-lookup"><span data-stu-id="95078-104">Before you use data integration, you must create the initial data required for customers, vendors and contacts.</span></span> <span data-ttu-id="95078-105">Por exemplo, se quiser criar um novo item **Grupo de fornecedores** e definir **Condições de Pagamento** como **Net30**, antes de tentar criar o item **Grupo de fornecedores**, você precisará garantir que exista **Net30** em Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="95078-105">For example, if you want to create a new **Vendor group** item and set its **Terms of Payment** as **Net30**, then before you attempt to create the **Vendor group** item you need to make sure that **Net30** exists in both Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="95078-106">(No futuro, liberaremos uma funcionalidade de plataforma de gravação dupla chamada **Sincronização Inicial**. Ela fará uma sincronização de dados única entre o Finance and Operations e o Common Data Service como parte da configuração de gravação dupla.)</span><span class="sxs-lookup"><span data-stu-id="95078-106">(In the future, we will release a  dual-write platform functionality called **Initial Sync**. It will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

<span data-ttu-id="95078-107">Dicas: estamos liberando um mapa de gravação dupla para todos os dados de referência, incluindo **Condições de Pagamento** (condições de pagamento).</span><span class="sxs-lookup"><span data-stu-id="95078-107">Tips: We are releasing a dual-write map for all reference data including **Terms of Payment** (Payment Terms).</span></span> <span data-ttu-id="95078-108">Se você já tiver os dados iniciais em um sistema, uma operação de atualização pequena em um registro poderá acionar uma gravação dupla nesse registro.</span><span class="sxs-lookup"><span data-stu-id="95078-108">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span> 

<span data-ttu-id="95078-109">Obedeça a ordem de precedência a seguir e verifique se os dados iniciais estão disponíveis no Finance and Operations e no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="95078-109">You must follow the following order of precedence and make sure that the initial data is available on both Finance and Operations and Common Data Service.</span></span>   

## <a name="vendor"></a><span data-ttu-id="95078-110">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="95078-110">Vendor</span></span>

<span data-ttu-id="95078-111">A ordem de execução do fornecedor é:</span><span class="sxs-lookup"><span data-stu-id="95078-111">The order of execution for Vendor is:</span></span>

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a><span data-ttu-id="95078-112">Cliente (Organização)</span><span class="sxs-lookup"><span data-stu-id="95078-112">Customer (Organization)</span></span>

<span data-ttu-id="95078-113">A ordem de execução do cliente é:</span><span class="sxs-lookup"><span data-stu-id="95078-113">The order of execution for Customer is:</span></span>

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a><span data-ttu-id="95078-114">Contato (Pessoa)</span><span class="sxs-lookup"><span data-stu-id="95078-114">Contact (Person)</span></span>

<span data-ttu-id="95078-115">A ordem de execução do contato é:</span><span class="sxs-lookup"><span data-stu-id="95078-115">The order of execution for Contact is:</span></span>

```
Customer
Vendor               
```
