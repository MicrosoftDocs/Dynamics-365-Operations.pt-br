---
title: Status de manutenção
description: Este tópico explica como calcular o status de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetStatusCalculate, EntAssetStatus
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b5bac42d5cdc62361ee9a562e59bafa09ca7a215
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018487"
---
# <a name="maintenance-status"></a><span data-ttu-id="9abe5-103">Status de manutenção</span><span class="sxs-lookup"><span data-stu-id="9abe5-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="9abe5-104">No Gerenciamento de Ativos, você pode fazer um cálculo para obter uma visão geral de um período específico de atividades novas, ativas e concluídas de solicitações de manutenção, ordens de serviço e tempo de inatividade de manutenção.</span><span class="sxs-lookup"><span data-stu-id="9abe5-104">In Asset Management, you can make an overview calculation for a specific period for new, active, and completed maintenance requests, work orders, and maintenance downtime activities.</span></span> <span data-ttu-id="9abe5-105">Você também pode ver o número de avaliações de condição concluídas para o mesmo período.</span><span class="sxs-lookup"><span data-stu-id="9abe5-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="9abe5-106">Use esse cálculo para obter uma visão geral da carga de trabalho referente às solicitações de manutenção e ordens de serviço recebidas e concluídas.</span><span class="sxs-lookup"><span data-stu-id="9abe5-106">Use this calculation to get an overview of workload for incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="9abe5-107">Execute um cálculo de status de manutenção</span><span class="sxs-lookup"><span data-stu-id="9abe5-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="9abe5-108">Clique **Gerenciamento de ativos** > **Consultas** > **Status de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="9abe5-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="9abe5-109">Na caixa de diálogo **Calcular status**, selecione o período para o qual você deseja fazer o cálculo nos campos **Data inicial** e **Data final**.</span><span class="sxs-lookup"><span data-stu-id="9abe5-109">In the **Calculate status** dialog, select the time range that you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="9abe5-110">Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de manutenção em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="9abe5-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> 

  <span data-ttu-id="9abe5-111">Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todas as linhas de manutenção de um local funcional serão mostradas no nível superior e, portanto, o status de uma linha podem ser adicionado aos locais funcionais localizados em nível inferior.</span><span class="sxs-lookup"><span data-stu-id="9abe5-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> 
  
  <span data-ttu-id="9abe5-112">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de manutenção em todos os níveis do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="9abe5-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="9abe5-113">Clique em **OK** para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="9abe5-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="9abe5-114">Clique nos botões **Agrupar por** para mostrar o nível de detalhes necessário para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="9abe5-114">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="9abe5-115">Os botões selecionados de **Agrupar por** são realçados.</span><span class="sxs-lookup"><span data-stu-id="9abe5-115">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="9abe5-116">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="9abe5-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="9abe5-117">Lembre-se de clicar no botão **Atualizar** para atualizar o cálculo sempre que você fizer alterações, ativando ou desativando os botões **Agrupar por** ou fazendo um cálculo para um novo período.</span><span class="sxs-lookup"><span data-stu-id="9abe5-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="9abe5-118">Clique em **Status** se quiser criar um novo cálculo do status de manutenção.</span><span class="sxs-lookup"><span data-stu-id="9abe5-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="9abe5-119">Os resultados mostrados no **Status de manutenção** somente incluem solicitações de manutenção e ordens de serviço que têm data e hora inicial real.</span><span class="sxs-lookup"><span data-stu-id="9abe5-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="9abe5-120">A data e a hora de término podem estar em branco.</span><span class="sxs-lookup"><span data-stu-id="9abe5-120">End date and time may be blank.</span></span>

## <a name="example-1"></a><span data-ttu-id="9abe5-121">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="9abe5-121">Example 1</span></span>

<span data-ttu-id="9abe5-122">Na captura de tela abaixo, os botões **Ano** e **Mês** foram ativados.</span><span class="sxs-lookup"><span data-stu-id="9abe5-122">In the screenshot below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="9abe5-123">Com essas opções de **Agrupar por** selecionadas, você terá uma visão geral mensal da carga de trabalho e da produtividade relacionada às solicitações de manutenção e às ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="9abe5-123">With these **Group by** options selected, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![Exemplo de carga de trabalho mensal](media/13-controlling-and-reporting.png)

## <a name="example-2"></a><span data-ttu-id="9abe5-125">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="9abe5-125">Example 2</span></span>

<span data-ttu-id="9abe5-126">Na captura de tela abaixo, foram adicionadas informações sobre locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="9abe5-126">In the screenshot below, information about functional locations has been added.</span></span> <span data-ttu-id="9abe5-127">Agora, é possível comparar a carga de trabalho e a produtividade entre os locais funcionais, que podem representar locais geográficos, fábricas ou áreas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9abe5-127">Now it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![Exemplo de carga de trabalho mensal com locais funcionais](media/14-controlling-and-reporting.png)

