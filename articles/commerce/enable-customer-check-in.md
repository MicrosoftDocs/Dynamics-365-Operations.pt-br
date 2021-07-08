---
title: Habilitar notificações de check-in do cliente no ponto de venda (PDV)
description: Este tópico descreve como habilitar notificações de check-in do cliente no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b42dc7766f8a69a7409c28d21b49cc96eca18dd4
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271416"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a><span data-ttu-id="700d4-103">Habilitar notificações de check-in do cliente no ponto de venda (PDV)</span><span class="sxs-lookup"><span data-stu-id="700d4-103">Enable customer check-in notifications in point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="700d4-104">Este tópico descreve como habilitar notificações de check-in do cliente no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="700d4-104">This topic describes how to enable customer check-in notifications in Microsoft Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="700d4-105">Em emails "ordem pronta para retirada", as organizações podem fornecer um link ou botão que permita aos clientes notificar a loja em que estão no local e aguardar que o pacote seja trazido para eles.</span><span class="sxs-lookup"><span data-stu-id="700d4-105">In their "order ready for pickup" emails, organizations can provide a link or button that lets customers notify the store that they are on the premises and waiting for their package to be brought out to them.</span></span> <span data-ttu-id="700d4-106">Em seguida, os clientes recebem uma confirmação de check-in e a loja recebe uma notificação como uma tarefa no aplicativo de PDV.</span><span class="sxs-lookup"><span data-stu-id="700d4-106">Customers then receive a check-in confirmation, and the store receives a notification as a task in its POS application.</span></span> <span data-ttu-id="700d4-107">Essa tarefa serve como um aviso para que um representante de vendas forneça a ordem ao veículo do cliente.</span><span class="sxs-lookup"><span data-stu-id="700d4-107">This task serves as a prompt for a sales associate to deliver the order to the customer's vehicle.</span></span> <span data-ttu-id="700d4-108">Portanto, o cliente não precisa inserir a loja.</span><span class="sxs-lookup"><span data-stu-id="700d4-108">Therefore, the customer doesn't have to enter the store.</span></span>

<span data-ttu-id="700d4-109">O fluxo de trabalho de check-in do cliente também pode ser configurado para coletar informações adicionais de clientes, como o número de vaga de estacionamento, a marca, o modelo, a cor do veículo e instruções de entrega.</span><span class="sxs-lookup"><span data-stu-id="700d4-109">The customer check-in workflow can also be configured to collect additional information from customers, such as their parking spot number, the make, model, and color of their vehicle, and delivery instructions.</span></span> <span data-ttu-id="700d4-110">O atendente da loja de varejo pode usar essas informações para facilitar o atendimento da ordem.</span><span class="sxs-lookup"><span data-stu-id="700d4-110">The retail store attendant can use this information to facilitate order fulfillment.</span></span>

## <a name="enable-customer-check-in"></a><span data-ttu-id="700d4-111">Habilitar o check-in do cliente</span><span class="sxs-lookup"><span data-stu-id="700d4-111">Enable customer check-in</span></span>

<span data-ttu-id="700d4-112">Quando o recurso de check-in do cliente é ativado, o Commerce gera uma ID de confirmação de ordem (também conhecida como ID de referência do canal).</span><span class="sxs-lookup"><span data-stu-id="700d4-112">When the customer check-in feature is turned on, Commerce generates an order confirmation ID (also known as the channel reference ID).</span></span> <span data-ttu-id="700d4-113">Ele também gera IDs de confirmação de ordens para ordens criadas por meio de canais de ponto de venda (PDV) ou de call center.</span><span class="sxs-lookup"><span data-stu-id="700d4-113">It also generates order confirmation IDs for orders that are created through point of sale (POS) or call center channels.</span></span> 

<span data-ttu-id="700d4-114">Para ativar o recurso de check-in de cliente na sede do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="700d4-114">To turn on the customer check-in feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="700d4-115">Acesse **Espaços de trabalho \> Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="700d4-115">Go to **Workspaces \> Feature management**.</span></span>
2. <span data-ttu-id="700d4-116">Procure o recurso **Gerar um formato de ID de referência de canal consistente entre canais**.</span><span class="sxs-lookup"><span data-stu-id="700d4-116">Search for the **Generate a consistent channel reference ID format across channels** feature.</span></span> 
3. <span data-ttu-id="700d4-117">Selecione o recurso e, depois, **Habilitar agora** no painel de propriedades.</span><span class="sxs-lookup"><span data-stu-id="700d4-117">Select the feature, and then select **Enable now** in the properties pane.</span></span> 

## <a name="create-a-check-in-confirmation-page"></a><span data-ttu-id="700d4-118">Criar uma página de confirmação de check-in</span><span class="sxs-lookup"><span data-stu-id="700d4-118">Create a check-in confirmation page</span></span>

<span data-ttu-id="700d4-119">No site de comércio eletrônico, você deve criar uma nova página que servirá como a experiência de confirmação do check-in.</span><span class="sxs-lookup"><span data-stu-id="700d4-119">On your e-commerce site, you must create a new page that will serve as the check-in confirmation experience.</span></span> <span data-ttu-id="700d4-120">Por meio de configuração adicional, a página também pode incluir um formulário que coleta informações adicionais de clientes para facilitar o atendimento da ordem.</span><span class="sxs-lookup"><span data-stu-id="700d4-120">Through additional configuration, the page can also include a form that collects additional information from customers to facilitate order fulfillment.</span></span> <span data-ttu-id="700d4-121">Para obter informações sobre como configurar a página e o módulo, consulte [Módulo de check-in do cliente](check-in-pickup-module.md).</span><span class="sxs-lookup"><span data-stu-id="700d4-121">For information about how to set up the page and module, see [Customer check-in module](check-in-pickup-module.md).</span></span>

## <a name="configure-the-transactional-email-template"></a><span data-ttu-id="700d4-122">Configurar o modelo de email transacional</span><span class="sxs-lookup"><span data-stu-id="700d4-122">Configure the transactional email template</span></span>

<span data-ttu-id="700d4-123">Você deve adicionar um link **Estou aqui** ou um botão ao modelo para o email transacional que os clientes recebem quando a ordem está pronta para retirada.</span><span class="sxs-lookup"><span data-stu-id="700d4-123">You must add an **I am here** link or button to the template for the transactional email that customers receive when their order is ready for pickup.</span></span> <span data-ttu-id="700d4-124">Os clientes usarão este link ou botão para notificar a loja de que chegaram para retirar a ordem.</span><span class="sxs-lookup"><span data-stu-id="700d4-124">Customers will use this link or button to notify the store that they have arrived to pick up their order.</span></span> 

<span data-ttu-id="700d4-125">Adicione o link ou botão ao modelo mapeado para o tipo de notificação **Remessa concluída** e o modo de entrega que você está usando para o atendimento da ordem em frente à loja.</span><span class="sxs-lookup"><span data-stu-id="700d4-125">Add the link or button to the template that is mapped to the **Packing completed** notification type and the mode of delivery that you're using for curbside order fulfillment.</span></span> <span data-ttu-id="700d4-126">No modelo, crie um link ou botão HTML que aponta para a URL da página de confirmação de check-in criada.</span><span class="sxs-lookup"><span data-stu-id="700d4-126">In the template, create an HTML link or button that points to the URL of the check-in confirmation page that you created.</span></span> <span data-ttu-id="700d4-127">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="700d4-127">Here is an example.</span></span>

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
<span data-ttu-id="700d4-128">Para obter mais informações sobre como configurar modelos de email, consulte [Personalizar emails transacionais por modo de entrega](customize-email-delivery-mode.md).</span><span class="sxs-lookup"><span data-stu-id="700d4-128">For more information about how to configure email templates, see [Customize transactional emails by mode of delivery](customize-email-delivery-mode.md).</span></span> 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a><span data-ttu-id="700d4-129">Uma tarefa de confirmação de check-in é criada no PDV</span><span class="sxs-lookup"><span data-stu-id="700d4-129">A check-in confirmation task is created in POS</span></span>

<span data-ttu-id="700d4-130">Depois que um cliente notificar a loja em que estão presentes para retirada, eles receberão uma notificação de confirmação de check-in e uma tarefa será criada na lista de tarefas no PDV para a loja em que o cliente retira a ordem.</span><span class="sxs-lookup"><span data-stu-id="700d4-130">After a customer notifies the store that they are present for pickup, they receive a check-in confirmation notification, and a task is created in the tasks list in POS for the store where the customer is picking up the order.</span></span> <span data-ttu-id="700d4-131">A tarefa contém todas as informações de cliente e ordem necessárias para atender à ordem.</span><span class="sxs-lookup"><span data-stu-id="700d4-131">The task contains all the customer and order information that is required to fulfill the order.</span></span> <span data-ttu-id="700d4-132">Na tarefa, o campo de instruções mostra todas as informações coletadas do cliente por meio do formulário de informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="700d4-132">In the task, the instructions field shows any information that was collected from the customer through the additional information form.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="700d4-133">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="700d4-133">Additional resources</span></span>

[<span data-ttu-id="700d4-134">Fazer check-in para o módulo de retirada</span><span class="sxs-lookup"><span data-stu-id="700d4-134">Check-in for pickup module</span></span>](check-in-pickup-module.md)
