---
title: Configurar parâmetros de espaço de trabalho de controle de custo
description: Use este procedimento para configurar o espaço de trabalho de controle de custo, de forma que os gerentes de vários níveis em uma organização possam se aprofundar nos seus objetos de custo, como centros de custos e grupos de produtos.
author: kfend
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfigurationPerUser
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c38b6f2664426513ea46b16b4cd54d69d71d1399
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710547"
---
# <a name="configure-cost-control-workspace-parameters"></a>Configurar parâmetros de espaço de trabalho de controle de custo

[!include [banner](../../includes/banner.md)]

Use este procedimento para configurar o espaço de trabalho de controle de custo, de forma que os gerentes de vários níveis em uma organização possam se aprofundar nos seus objetos de custo, como centros de custos e grupos de produtos. A empresa de demonstração USP2 foi usada para criar esta gravação.

1. Acesse Contabilização de custos > Configuração > Configuração de espaço de trabalho de controle de custo.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Descrição, digite um valor.
5. Selecione Sim no campo Publicado.
    * Se definir esta opção como Sim, os usuários que foram atribuídos a uma dessas funções poderão consultar o relatório no espaço de trabalho de controle de custo: gerente de contabilidade de custo, contador de custos, funcionário de contador de custo ou controlador de objeto de custo. Se definir esta opção como Não, somente os usuários que foram atribuídos a uma dessas funções poderão consultar o relatório no espaço de trabalho de controle de custo: gerente de contabilidade de custo, contador de custos, funcionário de contador de custo.  
6. Expanda a seção Filtragem de dados.
7. No campo Unidade de controle de custo, insira ou selecione um valor.
8. No campo Versão original do orçamento, insira ou selecione um valor.
9. No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
10. No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
11. Expanda a seção Atribuir registros de cálculo.
12. Clique em Novo.
13. Na lista, marque a linha selecionada.
14. No campo Período do calendário fiscal, insira ou selecione um valor.
15. No campo Versão real, insira ou selecione um valor.
16. Expanda a seção Períodos fiscais por coluna.
17. Selecione Sim no campo Período atual.
18. Expanda a seção Colunas a serem exibidas para custos.
19. Selecione Sim no campo Custo fixo.
20. Selecione Sim no campo Custo variável.
21. Selecione Sim no campo Custo total.
22. Clique em Salvar.
23. Feche a página.
24. Acesse Contabilização de custos > Espaços de trabalho > Controle de custo.
25. Selecione um demonstrativo para exibir custos fixos, variáveis, totais e não classificados para os períodos fiscais selecionados.
26. No campo Período do calendário fiscal, insira ou selecione um valor.
27. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Depois de ter selecionado uma hierarquia de dimensão do objeto de Custo, expanda a hierarquia de dimensão do elemento de custo para ver os valores de custos desejados. Por exemplo, você pode expandir a hierarquia para Custos indiretos de fabricação para ver o valor.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
