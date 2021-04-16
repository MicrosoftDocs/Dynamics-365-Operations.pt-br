---
title: Criar um plano intercompanhia
description: Este procedimento mostra como criar um plano intercompanhia.
author: ShylaThompson
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0fb787955a67776b24b626eb23b7c1a9df87a0c0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841686"
---
# <a name="create-an-intercompany-plan"></a>Criar um plano intercompanhia

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um plano intercompanhia. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="set-up-an-intercompany-planning-group"></a>Configurar um grupo de planejamento intercompanhia 
1. No **Painel de Navegação**, acesse **Módulos > Planejamento mestre > Configuração > Grupos de planejamento intercompanhia**. 
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Nome com um valor de '10'.
3. Na lista, marque a linha selecionada.
4. Clique em **Excluir**. Esta etapa é necessária para encurtar a execução de planejamento intercompanhia.   O planejamento intercompanhia executará o planejamento mestre em todas as empresas de um grupo de planejamento a partir da sequência de planejamento mais baixa.  
5. Clique em **Sim**.
6. Feche a página.

## <a name="create-an-intercompany-plan"></a>Criar um plano intercompanhia
1. No **Painel de Navegação**, acesse **Módulos > Planejamento mestre > Espaços de trabalho > Planejamento mestre**.
2. Clique em **Planejamento mestre intercompanhia**.  
3. No campo **Grupo de planejamento intercompanhia**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada. Selecione Grupo de planejamento intercompanhia 10.  
5. No campo **Número de iterações de planejamento intercompanhia**, insira "2". O grupo de planejamento intercompanhia 10 tem dois membros. Para propagar os atrasos da empresa de origem (USMF) para a empresa do cliente (DEMF), será necessário executar a intercompanhia nas duas empresas duas vezes. A primeira iteração propagará a demanda e identificará os atrasos na empresa de origem (USMF). A segunda iteração propagará os atrasos da USMF para a DEMF.  
6. No campo **Primeira iteração**, selecione "Regeneração".
7. No campo **Iterações subsequentes**, selecione "Regeneração".
8. No campo **Número de threads**, insira um número. Isso representa o número de threads paralelos usados no planejamento.  
9. Clique em **OK**.

## <a name="view-the-result-of-the-plan"></a>Exibir o resultado do plano
1. No campo **Plano**, clique no botão suspenso para abrir a pesquisa.
2. Na lista, clique no link na linha selecionada. Clique no link para StaticPlan. Você precisa estar na empresa USMF.  
3. Clique em **Ordens planejadas**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]