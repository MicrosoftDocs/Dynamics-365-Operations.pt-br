---
title: Configurar e executar trabalho para lançar declarações
description: Este procedimento orienta como configurar e executar um trabalho em lotes recorrente para lançar demonstrativos para uma loja ou grupo de lojas selecionado.
author: josaw1
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52baa707c36f3468263782dc8ec735e44af88e38
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804224"
---
# <a name="configure-and-run-job-to-post-statements"></a>Configurar e executar trabalho para lançar declarações

[!include [banner](../includes/banner.md)]

Este procedimento orienta como configurar e executar um trabalho em lotes recorrente para lançar demonstrativos para uma loja ou grupo de lojas selecionado. Este procedimento usa a empresa USRT nos dados de demonstração.

1. Vá para Todos os espaços de trabalho > .. > Finanças da loja.
2. Clique em Lançar demonstrativos em lote.
    * Selecione uma hierarquia da organização e, na árvore de nós da organização, selecione uma loja individual ou um nó. Selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.  
    * Clique na seta para adicionar sua seleção.  
3. Clique na guia Executar em segundo plano. ![Executar em segundo plano](../dev-itpro/media/runbackground.png "Executar em segundo plano") 
4. Marque ou desmarque a caixa de seleção Processamento em lotes.
![Processamento em lotes](../dev-itpro/media/batchprocessing.png "Recorrência e processamento em lotes") 
5. Clique em Recorrência.
6. No campo Data de início, insira uma data.
7. No campo Hora de início, insira um horário.
    * Escolha se deseja terminar a recorrência após um número específico de execuções, em uma data específica ou nunca. Escolha dentre as várias opções para definir com que frequência deseja que o trabalho seja executado.  
8. Clique em OK.
9. Clique em OK.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]