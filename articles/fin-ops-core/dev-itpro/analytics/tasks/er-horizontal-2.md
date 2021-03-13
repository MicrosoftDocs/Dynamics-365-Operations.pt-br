---
title: ER Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel (Parte 2 - Executar formato)
description: Este tópico descreve como configurar um formato de relatório eletrônico (ER) para gerar relatórios como arquivos de planilhas (Excel) OPENXML. (Parte 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: c13179f424d570b23615fe81ca5ddfb7afed582d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093467"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a>ER Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel (Parte 2 - Executar formato)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico (ER) pode configurar um formato para gerar relatórios como arquivos OPENXML de planilhas de Excel em que as colunas exigidas possam ser criadas dinamicamente como intervalos expansíveis horizontalmente. Essas etapas podem ser executadas na empresa DEMF.

Para concluir essas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar intervalos expansíveis horizontalmente para adicionar colunas a relatórios Excel dinamicamente (Parte 1: criar formato)".

Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


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
    * Revise a saída gerada. Observe que o arquivo Excel recém-criado contém o mesmo número de colunas que foram selecionadas para as dimensões financeiras. O cabeçalho do relatório nessas colunas representa os nomes das dimensões financeiras. As linhas das transações nessas colunas representam as dimensões financeiras. Execute esse relatório e selecione dimensões diferentes para verificar se o relatório não é dependente do número de dimensões selecionadas ou do número de dimensões configuradas para essa instância.  

