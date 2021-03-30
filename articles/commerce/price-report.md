---
title: Relatórios de preços de varejo
description: Este tópico fornece uma visão geral do recurso de relatório de preços que pode ser usado para exibir as alterações de preço futuras dos produtos variados.
author: shajain
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: f317b22f2794dc71093068a51c8e9d4e6d7d55ac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231143"
---
# <a name="retail-price-reports"></a><span data-ttu-id="beee6-103">Relatórios de preços de varejo</span><span class="sxs-lookup"><span data-stu-id="beee6-103">Retail price reports</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="beee6-104">A fim de fornecer preços competitivos para seus clientes, os varejistas costumam alterar os preços dos produtos.</span><span class="sxs-lookup"><span data-stu-id="beee6-104">In order to provide competitive prices to their customers, retailers often change prices of products.</span></span> <span data-ttu-id="beee6-105">Os gerentes de lojas querem ter a capacidade de acessar facilmente as mudanças de preços recentes ou futuras para que possam planejar os recursos necessários para atualizar as etiquetas de preços exibidos nas prateleiras das lojas.</span><span class="sxs-lookup"><span data-stu-id="beee6-105">Store managers want the ability to easily access recent or upcoming price changes so that they can plan for the required resources to update the price labels displayed on the store shelves.</span></span> <span data-ttu-id="beee6-106">Com a versão 10.0 do Retail, um gerente de loja pode abrir o relatório **Preço** navegando até **Todas as lojas \> Loja \> Relatório de preço** e exibindo os preços atualizados dos produtos associados à loja.</span><span class="sxs-lookup"><span data-stu-id="beee6-106">With release 10.0 of Retail, a store manager can open the **Price** report by navigating to **All stores \> Store \> Price report** and viewing the updated prices for the products associated to the store.</span></span> 

<span data-ttu-id="beee6-107">Para habilitar o relatório de preço, o parâmetro **Habilitar o relatório de preço para loja** deve ser ativado.</span><span class="sxs-lookup"><span data-stu-id="beee6-107">To enable the price report, the **Enable price report for store** parameter must be turned on.</span></span> <span data-ttu-id="beee6-108">Esse parâmetro está localizado na guia **Parâmetros do Commerce \> Descontos \> Diversos**. Abrir a página **Relatório de preço** exibe uma caixa de diálogo com várias configurações.</span><span class="sxs-lookup"><span data-stu-id="beee6-108">This parameter is located on the **Commerce parameters \> Discounts \> Miscellaneous** tab. Opening the **Price report** page displays a dialog box with various configurations.</span></span> <span data-ttu-id="beee6-109">As configurações disponíveis estão listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="beee6-109">The available configurations are listed below.</span></span>

| <span data-ttu-id="beee6-110">Configuração</span><span class="sxs-lookup"><span data-stu-id="beee6-110">Configuration</span></span> | <span data-ttu-id="beee6-111">descrição</span><span class="sxs-lookup"><span data-stu-id="beee6-111">Description</span></span> |
|---|---|
| <span data-ttu-id="beee6-112">Data inicial/data final</span><span class="sxs-lookup"><span data-stu-id="beee6-112">From date / To date</span></span>| <span data-ttu-id="beee6-113">O intervalo de datas para o qual o relatório de preço deve ser gerado.</span><span class="sxs-lookup"><span data-stu-id="beee6-113">The date range for which the price report should be generated.</span></span> <span data-ttu-id="beee6-114">A duração é atualmente limitada a 7 dias.</span><span class="sxs-lookup"><span data-stu-id="beee6-114">The duration is currently limited to 7 days.</span></span> |
| <span data-ttu-id="beee6-115">Canal</span><span class="sxs-lookup"><span data-stu-id="beee6-115">Channel</span></span>| <span data-ttu-id="beee6-116">A loja para a qual o relatório de preço deve ser gerado.</span><span class="sxs-lookup"><span data-stu-id="beee6-116">The store for which the price report should be generated.</span></span> |
| <span data-ttu-id="beee6-117">Exibir produtos com estoque disponível</span><span class="sxs-lookup"><span data-stu-id="beee6-117">Display products with available inventory</span></span>| <span data-ttu-id="beee6-118">Definir isso como **Sim** mostrará os preços apenas para os produtos que atualmente possuem inventário físico disponível na loja.</span><span class="sxs-lookup"><span data-stu-id="beee6-118">Setting this to **Yes** will show the prices for only those products which currently have physical inventory available in the store.</span></span> |
| <span data-ttu-id="beee6-119">Exibir preços para grades</span><span class="sxs-lookup"><span data-stu-id="beee6-119">Display prices for variants</span></span> | <span data-ttu-id="beee6-120">Definir isso como **Sim** mostrará os preços das variantes juntamente com os produtos mestre.</span><span class="sxs-lookup"><span data-stu-id="beee6-120">Setting this to **Yes** will display the prices of the variants along with the product masters.</span></span> <span data-ttu-id="beee6-121">Isso só deve ser **Ativado** se você tiver preços específicos de variantes, porque o número de linhas aumenta muito.</span><span class="sxs-lookup"><span data-stu-id="beee6-121">This should only be turned **On** if you have variant-specific prices, because the number of rows grows very large.</span></span> <span data-ttu-id="beee6-122">Em versões futuras, habilitaremos os preços baseados em dimensões para que o gerente da loja possa escolher as dimensões para as quais os preços devem ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="beee6-122">In future releases, we will enable the dimensions-based prices so that the store manager can choose the dimensions for which the prices should be displayed.</span></span> |
| <span data-ttu-id="beee6-123">Exibir produtos com alterações de preço</span><span class="sxs-lookup"><span data-stu-id="beee6-123">Display products with price changes</span></span> | <span data-ttu-id="beee6-124">Definir isso como **Sim** mostrará os preços apenas para as datas em que o preço foi alterado.</span><span class="sxs-lookup"><span data-stu-id="beee6-124">Setting this to **Yes** will display the prices for only those dates on which the price has been changed.</span></span> <span data-ttu-id="beee6-125">O preço de *um dia antes* da **data inicial** selecionada sempre será exibido, para que o gerente da loja possa identificar facilmente os produtos que não alteraram os preços durante toda a duração selecionada e também pode exibir o preço atual.</span><span class="sxs-lookup"><span data-stu-id="beee6-125">The price for *one day before* the selected **From date** will always be displayed, so that the store manager can easily identity the products which have not changed prices for the entire selected duration, and can also view the current price.</span></span> |

<span data-ttu-id="beee6-126">Depois que o relatório é gerado, o arquivo do Excel pode ser baixado para qualquer necessidade adicional de filtragem.</span><span class="sxs-lookup"><span data-stu-id="beee6-126">After the report is generated, the Excel file can be downloaded for any additional filtering needs.</span></span> <span data-ttu-id="beee6-127">O relatório de preços também pode ser usado para verificar os preços históricos de produtos para datas passadas.</span><span class="sxs-lookup"><span data-stu-id="beee6-127">The price report can also be used to check the historical prices of products for past dates.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]