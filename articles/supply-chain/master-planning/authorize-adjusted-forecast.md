---
title: Autorizar uma previsão ajustada
description: Nem todos os dados de previsão precisam ser autorizados imediatamente. Este artigo explica como é possível especificar o período em que uma previsão estará autorizada. Ele também explica como você pode autorizar a previsão para empresas e modelos de previsão específicos.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67098f6008086788ef8814f45fd0dd5add990460
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813690"
---
# <a name="authorize-an-adjusted-forecast"></a><span data-ttu-id="c7f72-105">Autorizar uma previsão ajustada</span><span class="sxs-lookup"><span data-stu-id="c7f72-105">Authorize an adjusted forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7f72-106">Nem todos os dados de previsão precisam ser autorizados imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c7f72-106">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="c7f72-107">Este artigo explica como é possível especificar o período em que uma previsão estará autorizada.</span><span class="sxs-lookup"><span data-stu-id="c7f72-107">This article explains how you can specify the period that a forecast is authorized for.</span></span> <span data-ttu-id="c7f72-108">Ele também explica como você pode autorizar a previsão para empresas e modelos de previsão específicos.</span><span class="sxs-lookup"><span data-stu-id="c7f72-108">It also explains how you can authorize the forecast for specific companies and forecast models.</span></span>

<span data-ttu-id="c7f72-109">Nem todos os dados de previsão precisam ser autorizados imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c7f72-109">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="c7f72-110">Você pode especificar as datas inicial e final do período em que a previsão está autorizada.</span><span class="sxs-lookup"><span data-stu-id="c7f72-110">You can specify the start and end dates of the period that the forecast is authorized for.</span></span> <span data-ttu-id="c7f72-111">Essa funcionalidade permite congelar classificação específicas.</span><span class="sxs-lookup"><span data-stu-id="c7f72-111">This functionality lets you freeze specific buckets.</span></span> 

<span data-ttu-id="c7f72-112">As datas inicial e final especificadas devem corresponder às datas inicial e final da classificação em que a previsão é gerada.</span><span class="sxs-lookup"><span data-stu-id="c7f72-112">The start and end dates that you specify must correspond to the start and end dates of the bucket that the forecast is generated in.</span></span> <span data-ttu-id="c7f72-113">O sistema aplica essa restrição e ajusta automaticamente as datas, se o ajuste for necessário.</span><span class="sxs-lookup"><span data-stu-id="c7f72-113">The system enforces this restriction and automatically adjusts the dates, if adjustment is required.</span></span> 

<span data-ttu-id="c7f72-114">Na guia **Detalhes** da página **Autorização**, você pode exibir os detalhes sobre a previsão que foi gerada por último.</span><span class="sxs-lookup"><span data-stu-id="c7f72-114">On the **Details** tab of the **Authorization** page, you can view details about the forecast that was most recently generated.</span></span> 

<span data-ttu-id="c7f72-115">É possível selecionar as empresas e os modelos de previsão para autorizar o uso da previsão.</span><span class="sxs-lookup"><span data-stu-id="c7f72-115">You can select the companies and the forecast models to authorize the forecast for use.</span></span> <span data-ttu-id="c7f72-116">Por padrão, a grade inclui todas as empresas para as quais a demanda de previsão foi criada.</span><span class="sxs-lookup"><span data-stu-id="c7f72-116">By default, the grid includes all the companies that forecast demand has been created for.</span></span> <span data-ttu-id="c7f72-117">Para cada empresa, o modelo de previsão correspondente ao plano de previsão atual configurado nos parâmetros de planejamento mestre é previamente preenchido.</span><span class="sxs-lookup"><span data-stu-id="c7f72-117">For each company, the forecast model that corresponds to the current forecast plan that is set up in the master planning parameters is prefilled.</span></span> <span data-ttu-id="c7f72-118">No entanto, você pode alterar esse modelo para qualquer outro modelo de previsão pertencente à empresa.</span><span class="sxs-lookup"><span data-stu-id="c7f72-118">However, you can change this forecast model to any forecast model that belongs to that company.</span></span> <span data-ttu-id="c7f72-119">Se nenhum dado de demanda de previsão for gerado para uma empresa selecionada, você receberá uma mensagem de aviso no momento da importação.</span><span class="sxs-lookup"><span data-stu-id="c7f72-119">If no forecast demand data has been generated for a selected company, you receive a warning message at import time.</span></span> 

<span data-ttu-id="c7f72-120">É muito importante que você compreenda como funciona a caixa de seleção **Salvar os ajustes manuais feitos na previsão de demanda da linha de base**.</span><span class="sxs-lookup"><span data-stu-id="c7f72-120">It's very important that you understand how the **Save the manual adjustments made to the baseline demand forecast** check box works.</span></span> <span data-ttu-id="c7f72-121">Se você tiver feito ajustes manuais na previsão estatística, os valores ajustados serão autorizados para uso, mesmo se essa caixa de seleção estiver desmarcada.</span><span class="sxs-lookup"><span data-stu-id="c7f72-121">If you've made manual adjustments to the statistical baseline forecast, the adjusted values are authorized for use, even if this check box is cleared.</span></span> <span data-ttu-id="c7f72-122">Contudo, as alterações serão descartadas após a autorização.</span><span class="sxs-lookup"><span data-stu-id="c7f72-122">However, the changes are discarded after the authorization.</span></span> <span data-ttu-id="c7f72-123">Portanto, na próxima vez que uma previsão for gerada, ela será apenas uma previsão estatística e não terá nenhuma substituição manual, mesmo se a opção **Transferir ajustes manuais para a previsão de demanda** for selecionada.</span><span class="sxs-lookup"><span data-stu-id="c7f72-123">Therefore, the next time that a forecast is generated, that forecast is only a statistical forecast and doesn't have any manual overrides, even if **Transfer manual adjustments to the demand forecast** is selected.</span></span> <span data-ttu-id="c7f72-124">Portanto, considere a caixa de seleção **Salvar os ajustes manuais feitos na previsão de demanda da linha de base** como um mecanismo que lhe permitirá manter ou descartar qualquer alteração manual.</span><span class="sxs-lookup"><span data-stu-id="c7f72-124">Therefore, you can consider the **Save the manual adjustments made to the baseline demand forecast** check box a mechanism that lets you keep or discard all manual changes.</span></span>

<a name="additional-resources"></a><span data-ttu-id="c7f72-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c7f72-125">Additional resources</span></span>
--------

[<span data-ttu-id="c7f72-126">Faça ajustes manuais para a previsão estatística</span><span class="sxs-lookup"><span data-stu-id="c7f72-126">Make manual adjustments to the baseline forecast</span></span>](manual-adjustments-baseline-forecast.md)

[<span data-ttu-id="c7f72-127">​Monitorar precisão da previsão​</span><span class="sxs-lookup"><span data-stu-id="c7f72-127">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]