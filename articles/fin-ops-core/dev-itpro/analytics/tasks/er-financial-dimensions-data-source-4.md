---
title: 'ER Usar dimensões financeiras como uma fonte de dados (Parte 4: Executar o relatório)'
description: Este tópico descreve como configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. (Parte 4)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1fe332de84339d3369ba495ca13f50c4901f366
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092266"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER Usar dimensões financeiras como uma fonte de dados (Parte 4: Executar o relatório)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. Essas etapas podem ser executadas na empresa DEMF.

Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento "ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)". Você também deve configurar os tipos de documento padrão na página Parâmetros de relatório eletrônico. Os tipos de documento padrão também são definidos quando você baixa e importa qualquer configuração ER. 


## <a name="run-report"></a>Executar relatório
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda "Modelo de exemplo de dimensões financeiras".
3. Na árvore, selecione "Modelo de exemplo de dimensões financeiras\Relatório de diário-razão".
4. Clique em Executar.
![Página de configurações de ER](../media/er-financial-dimensions-guides-run1.png)
5. No campo Nome da dimensão, insira ou selecione um valor.
    * Para selecionar todas as dimensões na empresa atual, insira as seguintes informações:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
![Página de configurações de ER](../media/er-financial-dimensions-guides-run2.png)
6. Expanda os Registros para incluir a seção.
7. Clique em Filtro.
8. Selecione a linha para a tabela Diário-razão e o campo Número do lote do diário.
9. No campo Critérios, digite "00057".
10. Clique em OK.
11. Clique em OK.
![Página de configurações de ER](../media/er-financial-dimensions-guides-run3.png)
    * Revise a saída gerada. Para cada transação do lote selecionado, as dimensões financeiras do conjunto de dimensões correspondentes são apresentadas. Execute esse relatório e selecione dimensões diferentes para verificar se o relatório não é dependente do número de dimensões selecionadas ou do número de dimensões configuradas para essa instância.  
![Página de configurações de ER](../media/er-financial-dimensions-guides-run4.png)
