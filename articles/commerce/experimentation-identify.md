---
title: Identificar uma hipótese e determinar as métricas para um experimento
description: Este tópico descreve como identificar a hipótese e métricas de sucesso para um experimento que será executado em um site de comércio eletrônico no Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 43358264a2107fb139c00ce617054be16a74f935
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "4410326"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a><span data-ttu-id="dccfd-103">Identificar uma hipótese e determinar as métricas de sucesso para um experimento</span><span class="sxs-lookup"><span data-stu-id="dccfd-103">Identify a hypothesis and determine success metrics for an experiment</span></span>
<span data-ttu-id="dccfd-104">A primeira fase no ciclo de vida de experimentação inclui a identificação da hipótese de fazer experimentos e determinar as métricas que você rastreará para avaliar o êxito.</span><span class="sxs-lookup"><span data-stu-id="dccfd-104">The first phase in the experimentation lifecycle includes identifying the hypothesis for the experiment and determining the metrics you'll track to evaluate success.</span></span> <span data-ttu-id="dccfd-105">O diagrama a seguir mostra todas as etapas envolvidas na [configuração e na execução de um experimento](experimentation-overview.md) em um site de comércio eletrônico no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dccfd-105">The following diagram shows all of the steps involved in [setting up and running an experiment](experimentation-overview.md) on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="dccfd-106">Etapas adicionais são abordadas em tópicos separados.</span><span class="sxs-lookup"><span data-stu-id="dccfd-106">Additional steps are covered in separate topics.</span></span> 

<span data-ttu-id="dccfd-107">[ ![Usuário de teste de experimentação - identificar](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="dccfd-107">[ ![Experimentation user journey - Identify](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span></span>

<span data-ttu-id="dccfd-108">Uma hipótese é um instrução na qual você prevê o resultado do experimento.</span><span class="sxs-lookup"><span data-stu-id="dccfd-108">A hypothesis is a statement where you predict the outcome of the experiment.</span></span> <span data-ttu-id="dccfd-109">Muitos fatores vão para a definição de uma hipótese, por exemplo, pesquisar sobre comportamento do usuário e dados de sites que você coletou.</span><span class="sxs-lookup"><span data-stu-id="dccfd-109">Many factors go into defining a hypothesis, for example, research about user behavior and website data you've collected.</span></span> <span data-ttu-id="dccfd-110">Com a hipótese, você definirá a suposição ou teoria que deseja validar com seu experimento.</span><span class="sxs-lookup"><span data-stu-id="dccfd-110">With the hypothesis, you'll define the assumption or theory you want to validate with your experiment.</span></span> <span data-ttu-id="dccfd-111">Um exemplo de uma hipótese de seu experimento pode ser "*uma imagem de uma camiseta branca na minha página inicial vai impulsionar uma taxa de clickthrough maior do que um suéter azul-marinho durante os meses de verão, pois as pessoas desejam usar algo leve e claro no verão.*"</span><span class="sxs-lookup"><span data-stu-id="dccfd-111">An example of a hypothesis for your experiment may be "*a picture of a white t-shirt on my home page will drive a higher clickthrough rate than a navy sweater during summer months because people want to wear something lightweight and light colored in the summer.*"</span></span> <span data-ttu-id="dccfd-112">Nesse caso, você criará variações que incluem uma camiseta branca e um suéter azul-marinho e publicará ambas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="dccfd-112">In that case, you'll create variations that include a white t-shirt and a navy sweater, and publish both at the same time.</span></span>

<span data-ttu-id="dccfd-113">Para validar uma hipótese, o êxito ou a falha de um experimento deve estar diretamente ligado às ações do usuário; por exemplo, se o usuário do site clicar em um link ou botão.</span><span class="sxs-lookup"><span data-stu-id="dccfd-113">To validate a hypothesis, the success or failure of an experiment should be directly tied to user actions; for example, if the website user clicks on a link or button.</span></span> <span data-ttu-id="dccfd-114">Essas ações devem corresponder a eventos que serão informados ao serviço de terceiros que rastreia o experimento.</span><span class="sxs-lookup"><span data-stu-id="dccfd-114">These actions must correspond with events that will be reported to the third-party service tracking the experiment.</span></span> <span data-ttu-id="dccfd-115">Com o tempo, a porcentagem de usuários que executam a ação será registrada como uma métrica que pode ser usada para gerar relatórios e realizar análises.</span><span class="sxs-lookup"><span data-stu-id="dccfd-115">Over time, the percentage of users that take the action will be tallied as a metric you can use to generate reports and conduct analyses.</span></span> <span data-ttu-id="dccfd-116">Para revisar todos os eventos e atributos disponíveis, consulte [Eventos do componente do Commerce para diagnóstico e solução de problemas](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="dccfd-116">To review all of the available events and attributes, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>

## <a name="previous-step"></a><span data-ttu-id="dccfd-117">Etapa anterior</span><span class="sxs-lookup"><span data-stu-id="dccfd-117">Previous step</span></span>
[<span data-ttu-id="dccfd-118">Experimentação no Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="dccfd-118">Experimentation in Dynamics 365 Commerce</span></span>](experimentation-overview.md)


## <a name="next-step"></a><span data-ttu-id="dccfd-119">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="dccfd-119">Next step</span></span>
[<span data-ttu-id="dccfd-120">Configurar um experimento</span><span class="sxs-lookup"><span data-stu-id="dccfd-120">Set up an experiment</span></span>](experimentation-setup.md)
