---
title: 'Guia: Modificar uma previsão de demanda manualmente'
description: Este tópico descreve como alterar a previsão para um item
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e12ccf90b9971379e8931bd48d6243a855bb795
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6224001"
---
# <a name="guide-modify-a-demand-forecast-manually"></a><span data-ttu-id="057b4-103">Guia: Modificar uma previsão de demanda manualmente</span><span class="sxs-lookup"><span data-stu-id="057b4-103">Guide: Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="057b4-104">Este procedimento mostra como alterar a previsão para um item.</span><span class="sxs-lookup"><span data-stu-id="057b4-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="057b4-105">Esse procedimento é criado para o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="057b4-105">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="057b4-106">Modifique a previsão para um item selecionado</span><span class="sxs-lookup"><span data-stu-id="057b4-106">Modify the forecast for a selected item</span></span>

<span data-ttu-id="057b4-107">Para modificar a previsão para um item selecionado:</span><span class="sxs-lookup"><span data-stu-id="057b4-107">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="057b4-108">Vá para **Módulos \> Gerenciamento de informações do produto \> Produtos \> Produtos lançados**.</span><span class="sxs-lookup"><span data-stu-id="057b4-108">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="057b4-109">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="057b4-109">In the list, find and select the desired record.</span></span> <span data-ttu-id="057b4-110">Selecione o item cujo tipo deseja alterar a previsão.</span><span class="sxs-lookup"><span data-stu-id="057b4-110">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="057b4-111">No painel de ações, abra a guia **Planejar** e selecione **Previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="057b4-111">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="057b4-112">Na lista, selecione uma linha.</span><span class="sxs-lookup"><span data-stu-id="057b4-112">In the list, select a row.</span></span> <span data-ttu-id="057b4-113">Se não houver linhas de previsão, crie uma nova linha selecionando **Novo** no painel de ação.</span><span class="sxs-lookup"><span data-stu-id="057b4-113">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="057b4-114">No campo **Quantidade de vendas**, informe um número positivo.</span><span class="sxs-lookup"><span data-stu-id="057b4-114">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="057b4-115">Este número representa a quantidade prevista para o item.</span><span class="sxs-lookup"><span data-stu-id="057b4-115">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="057b4-116">Se você inserir um número negativo, será exibido um erro.</span><span class="sxs-lookup"><span data-stu-id="057b4-116">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="057b4-117">Preencha os outros campos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="057b4-117">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="057b4-118">Selecione **Salvar** no painel de ações.</span><span class="sxs-lookup"><span data-stu-id="057b4-118">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a><span data-ttu-id="057b4-119">Modificar a previsão para um ou mais itens com o Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="057b4-119">Modify the forecast for one or more items with Microsoft Excel</span></span>

<span data-ttu-id="057b4-120">Como modificar a previsão para um ou mais itens com o Microsoft Excel:</span><span class="sxs-lookup"><span data-stu-id="057b4-120">To modify the forecast for one or more items with Microsoft Excel:</span></span>

1. <span data-ttu-id="057b4-121">Execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="057b4-121">Do one of the following:</span></span>
    - <span data-ttu-id="057b4-122">Abra a página **Previsão de demanda** de um item (pode ser qualquer um) conforme descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="057b4-122">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="057b4-123">Acesse **Planejamento mestre \> Previsão \> Entrada de previsão manual \> Linhas de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="057b4-123">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="057b4-124">No painel de ações, abra a guia **Abrir no Microsoft Office \> Entradas da previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="057b4-124">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="057b4-125">Selecione um local para fazer download, salve e abra o arquivo baixado no Excel.</span><span class="sxs-lookup"><span data-stu-id="057b4-125">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="057b4-126">Se você vir um aviso, selecione a opção **Habilitar edição**.</span><span class="sxs-lookup"><span data-stu-id="057b4-126">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="057b4-127">No Excel, entre no Supply Chain Management usando o painel de tarefas do Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="057b4-127">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="057b4-128">Você deve conectar-se com a opção **Continuar conectado** habilitada e deve confiar no aplicativo de conexão de dados.</span><span class="sxs-lookup"><span data-stu-id="057b4-128">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="057b4-129">A planilha do Excel agora mostra todas as linhas de previsão de demanda atuais da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="057b4-129">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="057b4-130">Adicione, apague e edite as linhas de previsão de demanda, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="057b4-130">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="057b4-131">Selecione **Publicar** no painel da tarefas do Microsoft Dynamics para fazer o upload de suas alterações no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="057b4-131">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
