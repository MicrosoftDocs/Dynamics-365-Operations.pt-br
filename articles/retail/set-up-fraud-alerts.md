---
title: Configurar alertas de fraude
description: "Este tópico explica como configurar regras para alertar representantes de atendimento ao cliente sobre informações potencialmente fraudulentas quando as ordens são processadas. Você também pode especificar códigos a serem usados para colocar ordens suspeitas manualmente ou manualmente em espera."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09d80015298c3d0219b6ffb290dc456990536a62
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-fraud-alerts"></a><span data-ttu-id="aee88-104">Configurar alertas de fraude</span><span class="sxs-lookup"><span data-stu-id="aee88-104">Set up fraud alerts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="aee88-105">Este tópico explica como configurar regras para alertar representantes de atendimento ao cliente sobre informações potencialmente fraudulentas quando as ordens são processadas.</span><span class="sxs-lookup"><span data-stu-id="aee88-105">This topic explains how to set up rules to alert customer service representatives of potentially fraudulent information when orders are processed.</span></span> <span data-ttu-id="aee88-106">Você também pode especificar códigos a serem usados para colocar ordens suspeitas manualmente ou manualmente em espera.</span><span class="sxs-lookup"><span data-stu-id="aee88-106">You can define specific codes to use to automatically or manually put suspicious orders on hold.</span></span> 

<span data-ttu-id="aee88-107">Antes de configurar e usar as regras de verificação de fraude, você deve habilitar a verificação de fraude e definir os valores básicos de verificação de fraude nos parâmetros do call center.</span><span class="sxs-lookup"><span data-stu-id="aee88-107">Before you set up and use fraud checking rules, you must enable fraud checking and define the basic fraud checking values in the call center parameters.</span></span> <span data-ttu-id="aee88-108">Há dois tipos de regras de fraude:</span><span class="sxs-lookup"><span data-stu-id="aee88-108">There are two types of fraud rules:</span></span>

-   <span data-ttu-id="aee88-109">**Regras estáticas** - usam um valor específico; por exemplo, um número de telefone inserido em uma lista de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="aee88-109">**Static rules** use a specific value, such as a phone number that has been blacklisted.</span></span>
-   <span data-ttu-id="aee88-110">**Regras dinâmicas** - podem ser compostas por variáveis e condições.</span><span class="sxs-lookup"><span data-stu-id="aee88-110">**Dynamic rules** can be composed from variables and conditions.</span></span>

<span data-ttu-id="aee88-111">Antes de criar uma regra dinâmica, você deve criar as variáveis e as condições que definem a quem a regra se aplica e quando a regra deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="aee88-111">Before you create a dynamic rule, you must create the variables and conditions that define who the rule applies to and when the rule should be applied.</span></span> <span data-ttu-id="aee88-112">Por exemplo, você deseja criar uma regra para exigir que qualquer ordem de venda criada pelo cliente 1202 com valor de 1.000,00 ou mais seja colocada em espera até que o pagamento do cliente seja verificado.</span><span class="sxs-lookup"><span data-stu-id="aee88-112">For example, you want to create a rule to require that any sales order that customer 1202 places that is worth 1,000.00 or more be put on hold until the customer payment can be verified.</span></span> <span data-ttu-id="aee88-113">Nesse caso, as variáveis são o cliente 1202 e um valor total de 1.000,00 da ordem.</span><span class="sxs-lookup"><span data-stu-id="aee88-113">In this case, the variables are customer 1202 and an order total of 1,000.00.</span></span> <span data-ttu-id="aee88-114">A condição especifica que, se o cliente 1202 fizer um pedido, e o valor total da ordem for igual ou superior a 1.000,00, a ordem de venda deverá ser colocada em espera até que o pagamento do cliente seja verificado.</span><span class="sxs-lookup"><span data-stu-id="aee88-114">The condition specifies that if customer 1202 places an order, and the total amount of the order is equal to or more than 1,000.00, the sales order must be put on hold until the customer payment can be verified.</span></span>




