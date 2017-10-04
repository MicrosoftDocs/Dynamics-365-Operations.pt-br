---
title: "Autorizar uma previsão ajustada"
description: "Nem todos os dados de previsão precisam ser autorizados imediatamente. Este artigo explica como é possível especificar o período em que uma previsão estará autorizada. Ele também explica como você pode autorizar a previsão para empresas e modelos de previsão específicos."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 324f7385e8064eedcf35f0f07bb3b2ef6474f410
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="authorize-an-adjusted-forecast"></a>Autorizar uma previsão ajustada

[!include[banner](../includes/banner.md)]


Nem todos os dados de previsão precisam ser autorizados imediatamente. Este artigo explica como é possível especificar o período em que uma previsão estará autorizada. Ele também explica como você pode autorizar a previsão para empresas e modelos de previsão específicos.

Nem todos os dados de previsão precisam ser autorizados imediatamente. Você pode especificar as datas inicial e final do período em que a previsão está autorizada. Essa funcionalidade permite congelar classificação específicas. 

As datas inicial e final especificadas devem corresponder às datas inicial e final da classificação em que a previsão é gerada. O sistema aplica essa restrição e ajusta automaticamente as datas, se o ajuste for necessário. 

Na guia **Detalhes** da página **Autorização**, você pode exibir os detalhes sobre a previsão que foi gerada por último. 

É possível selecionar as empresas e os modelos de previsão para autorizar o uso da previsão. Por padrão, a grade inclui todas as empresas para as quais a demanda de previsão foi criada. Para cada empresa, o modelo de previsão correspondente ao plano de previsão atual configurado nos parâmetros de planejamento mestre é previamente preenchido. No entanto, você pode alterar esse modelo para qualquer outro modelo de previsão pertencente à empresa. Se nenhum dado de demanda de previsão for gerado para uma empresa selecionada, você receberá uma mensagem de aviso no momento da importação. 

É muito importante que você compreenda como funciona a caixa de seleção **Salvar os ajustes manuais feitos na previsão de demanda da linha de base**. Se você tiver feito ajustes manuais na previsão estatística, os valores ajustados serão autorizados para uso, mesmo se essa caixa de seleção estiver desmarcada. Contudo, as alterações serão descartadas após a autorização. Portanto, na próxima vez que uma previsão for gerada, ela será apenas uma previsão estatística e não terá nenhuma substituição manual, mesmo se a opção **Transferir ajustes manuais para a previsão de demanda** for selecionada. Portanto, considere a caixa de seleção **Salvar os ajustes manuais feitos na previsão de demanda da linha de base** como um mecanismo que lhe permitirá manter ou descartar qualquer alteração manual.

<a name="see-also"></a>Consulte também
--------

[Ajustes manuais na previsão estatística](manual-adjustments-baseline-forecast.md)

[Monitorando a precisão da previsão](monitor-forecast-accuracy.md)



