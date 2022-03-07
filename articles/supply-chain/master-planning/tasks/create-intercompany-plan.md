---
title: Criar um plano intercompanhia
description: Este procedimento mostra como criar um plano intercompanhia.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ef1484e6925427454f819a5effdc911f762b48b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578263"
---
# <a name="create-an-intercompany-plan"></a>Criar um plano intercompanhia

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um plano intercompanhia. A empresa de dados demo usada para criar este procedimento é USMF.

## <a name="set-up-an-intercompany-planning-group"></a>Configurar um grupo de planejamento intercompanhia

1. No **Painel de Navegação**, acesse **Módulos > Planejamento mestre > Configuração > Grupos de planejamento intercompanhia**.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Nome com um valor de '10'.
3. Na lista, marque a linha selecionada.
4. Selecione **Excluir**. Esta etapa é necessária para encurtar a execução de planejamento intercompanhia.   O planejamento intercompanhia executará o planejamento mestre em todas as empresas de um grupo de planejamento a partir da sequência de planejamento mais baixa.  
5. Selecione **Sim**.
6. Feche a página.

## <a name="create-an-intercompany-master-plan"></a>Criar um plano mestre intercompanhia

1. No **Painel de Navegação**, acesse **Módulos > Planejamento mestre > Espaços de trabalho > Planejamento mestre**.
2. Selecione **Planejamento mestre intercompanhia**.  
3. No campo **Grupo de planejamento intercompanhia**, selecione o botão suspenso para abrir a pesquisa.
4. Na lista, selecione o link na linha selecionada. Selecione Grupo de planejamento intercompanhia 10.  
5. No campo **Número de iterações de planejamento intercompanhia**, insira "2". O grupo de planejamento intercompanhia 10 tem dois membros. Para propagar os atrasos da empresa de origem (USMF) para a empresa do cliente (DEMF), será necessário executar a intercompanhia nas duas empresas duas vezes. A primeira iteração propagará a demanda e identificará os atrasos na empresa de origem (USMF). A segunda iteração propagará os atrasos da USMF para a DEMF.  
6. No campo **Primeira iteração**, selecione "Regeneração".
7. No campo **Iterações subsequentes**, selecione "Regeneração".
8. No campo **Número de threads**, insira um número. Isso representa o número de threads paralelos usados no planejamento.  
9. Selecione **OK**.

## <a name="view-the-result-of-the-plan"></a>Exibir o resultado do plano

1. No campo **Plano**, selecione o botão suspenso para abrir a pesquisa.
2. Na lista, selecione o link na linha selecionada. Selecione o link para StaticPlan. Você precisa estar na empresa USMF.  
3. Selecione **Ordens planejadas**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]