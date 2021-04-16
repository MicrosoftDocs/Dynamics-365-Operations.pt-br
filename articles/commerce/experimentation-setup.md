---
title: Configurar um experimento
description: Este tópico descreve como configurar um experimento em um serviço de terceiros.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 9976ca461f7e988c32b81565fa2d084709e5ad6e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792495"
---
# <a name="set-up-an-experiment"></a><span data-ttu-id="831fd-103">Configurar um experimento</span><span class="sxs-lookup"><span data-stu-id="831fd-103">Set up an experiment</span></span>

<span data-ttu-id="831fd-104">Depois de [definir uma hipótese e determinar quais métricas de sucesso você deseja usar](experimentation-identify.md), você precisará configurar seu experimento no serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="831fd-104">After you [define a hypothesis and determine what success metrics you want to use](experimentation-identify.md), you'll need to set up your experiment in the third-party service.</span></span> <span data-ttu-id="831fd-105">O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="831fd-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="831fd-106">Etapas adicionais são abordadas em tópicos separados.</span><span class="sxs-lookup"><span data-stu-id="831fd-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="831fd-107">[ ![Usuário de teste de experimentação - configuração](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="831fd-107">[ ![Experimentation user journey - Setup](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span></span>


## <a name="set-up-your-experiment-in-the-third-party-service"></a><span data-ttu-id="831fd-108">Configurar seu experimento no serviço de terceiros</span><span class="sxs-lookup"><span data-stu-id="831fd-108">Set up your experiment in the third-party service</span></span>
<span data-ttu-id="831fd-109">Você já deve ter escolhido o serviço de terceiros para ser executado e monitorar seu experimento e configurar o conector de experimentação.</span><span class="sxs-lookup"><span data-stu-id="831fd-109">By now you should have chosen your third-party service to run and monitor your experiment, and set up the experimentation connector.</span></span> <span data-ttu-id="831fd-110">Esses pré-requisitos estão listados em [Experimentação no Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="831fd-110">These prerequisites are listed in  [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="831fd-111">Siga as etapas necessárias para criar seu experimento no serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="831fd-111">Follow the steps required to create your experiment in the third-party service.</span></span> <span data-ttu-id="831fd-112">Se o conector estiver configurado corretamente, a lista completa de experimentos configurados no serviço de terceiros aparecerá no construtor de sites do Commerce em cerca de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="831fd-112">If the connector is configured properly, the complete list of experiments you set up in the third-party service will appear in Commerce site builder within about 5 minutes.</span></span>

## <a name="set-up-your-success-metrics"></a><span data-ttu-id="831fd-113">Configurar métricas de sucesso</span><span class="sxs-lookup"><span data-stu-id="831fd-113">Set up your success metrics</span></span>
<span data-ttu-id="831fd-114">Cada experimento precisa de métricas para medir o impacto das variações e para validar a hipótese.</span><span class="sxs-lookup"><span data-stu-id="831fd-114">Every experiment needs metrics to measure the impact of the variations and to validate the hypothesis.</span></span> <span data-ttu-id="831fd-115">Siga as etapas abaixo para habilitar o cálculo de métricas no serviço de terceiros usando eventos de telemetria ativos do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="831fd-115">Follow the steps below to enable the computation of metrics in the third-party service using live telemetry events from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="831fd-116">Para configurar suas métricas de êxito, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="831fd-116">To set up your success metrics, follow these steps.</span></span>

1. <span data-ttu-id="831fd-117">No construtor de sites do Commerce, selecione **Páginas** no painel de navegação esquerdo e, em seguida, selecione a página na qual deseja retirar métricas.</span><span class="sxs-lookup"><span data-stu-id="831fd-117">In Commerce site builder, select **Pages** in the left navigation pane, and then select the page that you want to collect metrics for.</span></span> 
1. <span data-ttu-id="831fd-118">Vá para a seção **IDs de evento para rastrear** no painel de propriedades à direita da página ou do módulo que você deseja rastrear.</span><span class="sxs-lookup"><span data-stu-id="831fd-118">Go to the **Event IDs to track** section in the right property pane of the page or module you want to track.</span></span>
1. <span data-ttu-id="831fd-119">Selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="831fd-119">Select **View**.</span></span> <span data-ttu-id="831fd-120">Uma lista de todas as IDs de evento é exibida.</span><span class="sxs-lookup"><span data-stu-id="831fd-120">A list of all event IDs is displayed.</span></span> <span data-ttu-id="831fd-121">Copie o evento que você deseja rastrear e cole a chave de evento no local designado no serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="831fd-121">Copy the event you want to track, and paste the event key into the designated location in the third-party service.</span></span> <span data-ttu-id="831fd-122">Se você precisar de mais de um evento, copie as chaves uma de cada vez.</span><span class="sxs-lookup"><span data-stu-id="831fd-122">If you need more than one event, copy the keys one at a time.</span></span> 
    - <span data-ttu-id="831fd-123">Para saber como exibir todos os atributos e eventos disponíveis, incluindo exibições de página e controle de receita, consulte [Eventos de componente do Commerce para diagnóstico e solução de problemas](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="831fd-123">To learn how to view all of the available events and attributes, including page views and revenue tracking, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>
1. <span data-ttu-id="831fd-124">Execute outras etapas para controlar as métricas necessárias no serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="831fd-124">Take any other steps for tracking metrics as required in the third-party service.</span></span>

## <a name="previous-step"></a><span data-ttu-id="831fd-125">Etapa anterior</span><span class="sxs-lookup"><span data-stu-id="831fd-125">Previous step</span></span>
[<span data-ttu-id="831fd-126">Identificar uma hipótese e determinar as métricas para um experimento</span><span class="sxs-lookup"><span data-stu-id="831fd-126">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md) 


## <a name="next-step"></a><span data-ttu-id="831fd-127">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="831fd-127">Next step</span></span>
[<span data-ttu-id="831fd-128">Conectar e editar um experimento</span><span class="sxs-lookup"><span data-stu-id="831fd-128">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]