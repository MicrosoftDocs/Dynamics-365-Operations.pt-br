---
title: Relatar como concluído para um local não controlado por placa de licença (solicitação de emprego, maio de 2016)
description: Esta guia mostra um exemplo de tarefas do relatório de conclusão para um local que não seja controlado por placa de licença.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdParmCostEstimation, ProdParmStartUp, ProdParmReportFinished, WHSWorkTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f891b2e3b20993a08138dfac1aed4f4bab33c6b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576703"
---
# <a name="report-as-finished-to-a-non-license-plate-controlled-location--application-may-2016"></a>Relatar como concluído para um local não controlado por placa de licença (solicitação de emprego, maio de 2016)

[!include [banner](../../includes/banner.md)]

Esta guia mostra um exemplo de tarefas do relatório de conclusão para um local que não seja controlado por placa de licença. Uma diretiva de trabalho aplicável é o pré-requisito para esta tarefa. Uma guia anterior da tarefa mostrou da instalação da diretiva de trabalho. Essa guia da tarefa requer o aplicativo do Dynamics AX 7.0.1 ou posterior.




## <a name="set-up-an-output-location"></a>Configurar uma localização de saída
1. Acesse Administração da organização > Recursos > Grupos de recursos.
2. Na lista, selecione grupo de recurso "5102".
3. Clique em Editar.
4. No campo Depósito de saída, insira "51".
5. No campo Local de saída, insira "001".
    * O local 001 não é um local controlado por placa de licença. Você pode configurar um local de saída em branco da licença não aplicável somente se uma diretiva de trabalho existir para o local.  

## <a name="create-a-production-order-and-report-it-as-finished"></a>Criar uma ordem de produção e relatar quando estiver concluída
1. Feche a página.
2. Acesse Controle de produção > Ordens de produção > Todas as ordens de produção.
3. Clique em Nova ordem de produção.
4. No campo Número do item, insira "L0101".
5. Clique em Criar.
6. No Painel de Ação, clique em Ordem de produção.
7. Clique em Estimar.
8. Clique em OK.
9. Clique em Iniciar.
10. Clique na guia Geral.
11. No campo Consumo automático de BOM, selecione 'Nunca'.
12. Clique em OK.
13. Clique em Relatório de conclusão.
14. Clique na guia Geral.
15. Selecione Sim no campo Aceitar erro.
16. Clique em OK.
17. No Painel de Ação, clique em Depósito.
18. Clique em Detalhes do trabalho.
    * Quando a ordem de produção foi informada como concluída, nenhum trabalho foi gerado para ser colocado de lado. Isso ocorre porque uma diretiva de trabalho que é definida impede que o trabalho seja gerado quando o produto L0101 é relatado como concluídos no local 001.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]