---
title: Modificar uma previsão de demanda manualmente
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
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889015"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="79a7b-103">Modificar uma previsão de demanda manualmente</span><span class="sxs-lookup"><span data-stu-id="79a7b-103">Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="79a7b-104">Este procedimento mostra como alterar a previsão para um item.</span><span class="sxs-lookup"><span data-stu-id="79a7b-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="79a7b-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="79a7b-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="79a7b-106">Esse procedimento é criado para o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="79a7b-106">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="79a7b-107">Modifique a previsão para um item selecionado</span><span class="sxs-lookup"><span data-stu-id="79a7b-107">Modify the forecast for a selected item</span></span>

<span data-ttu-id="79a7b-108">Para modificar a previsão para um item selecionado:</span><span class="sxs-lookup"><span data-stu-id="79a7b-108">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="79a7b-109">Vá para **Módulos \> Gerenciamento de informações do produto \> Produtos \> Produtos lançados**.</span><span class="sxs-lookup"><span data-stu-id="79a7b-109">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="79a7b-110">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="79a7b-110">In the list, find and select the desired record.</span></span> <span data-ttu-id="79a7b-111">Selecione o item cujo tipo deseja alterar a previsão.</span><span class="sxs-lookup"><span data-stu-id="79a7b-111">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="79a7b-112">No painel de ações, abra a guia **Planejar** e selecione **Previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="79a7b-112">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="79a7b-113">Na lista, selecione uma linha.</span><span class="sxs-lookup"><span data-stu-id="79a7b-113">In the list, select a row.</span></span> <span data-ttu-id="79a7b-114">Se não houver linhas de previsão, crie uma nova linha selecionando **Novo** no painel de ação.</span><span class="sxs-lookup"><span data-stu-id="79a7b-114">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="79a7b-115">No campo **Quantidade de vendas**, informe um número positivo.</span><span class="sxs-lookup"><span data-stu-id="79a7b-115">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="79a7b-116">Este número representa a quantidade prevista para o item.</span><span class="sxs-lookup"><span data-stu-id="79a7b-116">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="79a7b-117">Se você inserir um número negativo, será exibido um erro.</span><span class="sxs-lookup"><span data-stu-id="79a7b-117">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="79a7b-118">Preencha os outros campos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="79a7b-118">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="79a7b-119">Selecione **Salvar** no painel de ações.</span><span class="sxs-lookup"><span data-stu-id="79a7b-119">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a><span data-ttu-id="79a7b-120">Modifique a previsão para um ou mais itens no Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="79a7b-120">Modify the forecast for one or more items Microsoft Excel</span></span>

<span data-ttu-id="79a7b-121">Para modificar a previsão para um ou mais itens no Microsoft Excel:</span><span class="sxs-lookup"><span data-stu-id="79a7b-121">To modify the forecast for one or more items Microsoft Excel:</span></span>

1. <span data-ttu-id="79a7b-122">Execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="79a7b-122">Do one of the following:</span></span>
    - <span data-ttu-id="79a7b-123">Abra a página **Previsão de demanda** de um item (pode ser qualquer um) conforme descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="79a7b-123">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="79a7b-124">Acesse **Planejamento mestre \> Previsão \> Entrada de previsão manual \> Linhas de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="79a7b-124">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="79a7b-125">No painel de ações, abra a guia **Abrir no Microsoft Office \> Entradas da previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="79a7b-125">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="79a7b-126">Selecione um local para fazer download, salve e abra o arquivo baixado no Excel.</span><span class="sxs-lookup"><span data-stu-id="79a7b-126">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="79a7b-127">Se você vir um aviso, selecione a opção **Habilitar edição**.</span><span class="sxs-lookup"><span data-stu-id="79a7b-127">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="79a7b-128">No Excel, entre no Supply Chain Management usando o painel de tarefas do Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="79a7b-128">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="79a7b-129">Você deve conectar-se com a opção **Continuar conectado** habilitada e deve confiar no aplicativo de conexão de dados.</span><span class="sxs-lookup"><span data-stu-id="79a7b-129">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="79a7b-130">A planilha do Excel agora mostra todas as linhas de previsão de demanda atuais da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="79a7b-130">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="79a7b-131">Adicione, apague e edite as linhas de previsão de demanda, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="79a7b-131">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="79a7b-132">Selecione **Publicar** no painel da tarefas do Microsoft Dynamics para fazer o upload de suas alterações no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="79a7b-132">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
