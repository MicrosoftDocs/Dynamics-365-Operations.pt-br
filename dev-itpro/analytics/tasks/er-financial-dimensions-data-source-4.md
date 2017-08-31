--- 
title: "Executar um relatório que usa dimensões financeiras como uma fonte de dados para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f07e640d4b2a7f67d48df4c081819a55e7e68cda
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="run-a-report-that-uses-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a>Executar um relatório que usa dimensões financeiras como uma fonte de dados para relatório eletrônico (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. Essas etapas podem ser executadas na empresa DEMF.

Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento “ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório). Você também deve configurar os tipos de documento padrão na página Parâmetros de relatório eletrônico. Os tipos de documento padrão também são definidos quando você baixa e importa qualquer configuração ER. 


## <a name="run-report"></a>Executar relatório
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda "Modelo de exemplo de dimensões financeiras".
3. Na árvore, selecione "Modelo de exemplo de dimensões financeiras\Relatório de diário-razão".
4. Clique em Executar.
5. No campo Nome de dimensão, insira ou selecione um valor.
    * Para selecionar todas as dimensões na empresa atual, insira o seguinte:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
6. Expanda os Registros para incluir a seção.
7. Clique em Filtro.
8. Selecione a linha para a tabela Diário-razão e o campo Número do lote do diário.
9. No campo Critérios, digite "00057".
10. Clique em OK.
11. Clique em OK.
    * Revise a saída gerada. Observe que, para cada transação do lote selecionado, as dimensões financeiras do conjunto de dimensões correspondentes são apresentadas. Execute esse relatório e selecione diferentes dimensões para verificar se o relatório não é dependente do número de dimensões selecionadas ou do número de dimensões configuradas para essa instância do Dynamics 365 for Finance and Operations, edição Enterprise.  


