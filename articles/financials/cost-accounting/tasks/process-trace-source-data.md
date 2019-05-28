---
title: Processar e rastrear dados de origem
description: Todo o processamento de dados é executado por trabalhos.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e476416420875ba0f2401cf251d34977ae84b8f5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546515"
---
# <a name="process-and-trace-source-data"></a>Processar e rastrear dados de origem

[!include [task guide banner](../../includes/task-guide-banner.md)]

Todo o processamento de dados é executado por trabalhos. Para cada trabalho e provedor de dados, é criado um diário para documentar que o processo foi executado, e que as entradas foram processadas no trabalho atual. Use este procedimento para configurar uma fonte de dados e para rastrear a origem de uma entrada de custos específica. Esta gravação usa os dados da empresa de demonstração USP2. Antes de concluir esta tarefa, certifique-se de que executou os guias de tarefas "Criar um razão de contabilização de custos" e "Definir unidades de controle de custos".

1. Vá para Contabilização de custos > Configuração do razão > Razões de contabilização de custos.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione o razão de contabilização de custo criado anteriormente.  
3. Clique em Versões reais.
4. No Painel de Ação, clique em Processamento de dados de origem.
5. Clique em Diários de transferência de entradas de contabilidade.
6. Na lista, localize e selecione o PDV desejado.
7. Clique em Entradas de Diário.
8. Na lista, marque a linha selecionada.
9. Clique em Entradas de custo.
10. Clique em Entrada de origem.
11. No Painel de Ação, clique em Processamento de dados de origem.
12. Clique em Contabilidade.
13. No campo Período do calendário fiscal, insira ou selecione um valor.
    * Para este exemplo, selecione 9, Período Fiscal 2017.  
14. Clique em OK.

