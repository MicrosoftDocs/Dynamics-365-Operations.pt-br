--- 
title: "Executar um formato que use intervalos expansíveis horizontalmente para adicionar dinamicamente colunas em relatórios do Excel"
description: "As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico (ER) pode configurar um formato para gerar relatórios como arquivos OPENXML de planilhas de Excel em que as colunas exigidas possam ser criadas dinamicamente como intervalos expansíveis horizontalmente."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2d705d0d2803b5254adc27e6715c1eac311898a7
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="run-a-format-that-uses-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports"></a>Executar um formato que use intervalos expansíveis horizontalmente para adicionar dinamicamente colunas em relatórios do Excel

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico (ER) pode configurar um formato para gerar relatórios como arquivos OPENXML de planilhas de Excel em que as colunas exigidas possam ser criadas dinamicamente como intervalos expansíveis horizontalmente. Essas etapas podem ser executadas na empresa DEMF.

Para concluir essas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar intervalos expansíveis horizontalmente para adicionar colunas a relatórios Excel dinamicamente (Parte 1: criar formato)".

Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.


## <a name="find-created-format"></a>Localizar formato criado
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda "Modelo de exemplo de dimensões financeiras".
3. Na árvore, selecione 'Modelo de exemplo de dimensão financeira\Relatório de exemplo com intervalos expansíveis horizontalmente'.

## <a name="execute-format-to-create-excel-output"></a>Executar o formato para criar saída do Excel
1. Clique em Executar.
2. No campo Nome da dimensão, digite 'BusinessUnit;CostCenter;Department'.
    * No campo Nome da dimensão, insira ou selecione um valor.  Para selecionar todas as dimensões da empresa atual, insira o seguinte: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
3. Expanda os Registros para incluir a seção.
4. Clique em Filtro.
5. Selecione a linha para a tabela Diário-razão e o campo Número do lote do diário.
6. No campo Critérios, digite '00057..00058'.
    * 00057..00058  
7. Clique em OK.
8. Clique em OK.
    * Revise a saída gerada. Observe que o arquivo Excel recém-criado contém o mesmo número de colunas que foram selecionadas para as dimensões financeiras. O cabeçalho do relatório nessas colunas representa os nomes das dimensões financeiras. As linhas das transações nessas colunas representam as dimensões financeiras. Execute esse relatório e selecione diferentes dimensões para verificar se o relatório não é dependente do número de dimensões selecionadas ou do número de dimensões configuradas para essa instância do Dynamics 365 for Finance and Operations.  


