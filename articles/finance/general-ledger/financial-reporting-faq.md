---
title: Perguntas frequentes sobre relatórios financeiros
description: Este tópico lista perguntas relacionadas a relatórios financeiros de outros usuários.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923016"
---
# <a name="financial-reporting-faq"></a>Perguntas frequentes sobre relatórios financeiros 

Este tópico fornece respostas a perguntas frequentes sobre relatórios financeiros. 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Como posso restringir o acesso a um relatório usando a segurança em árvore?

O exemplo a seguir mostra como restringir o acesso a um relatório usando a segurança em árvore.

A empresa de demonstração USMF tem um relatório de balanço ao qual nem todos os usuários do relatório financeiro devem ter acesso. Você pode usar a segurança em árvore para restringir o acesso a um único relatório. Assim, apenas determinados usuários podem acessar o relatório. Siga estas etapas para restringir o acesso: 

1. Entre no Financial Reporter Report Designer.
2. Crie uma definição em árvore. Vá para **Arquivo > Novo > Definição em Árvore**.
3. Clique duas vezes na linha **Resumo** na coluna **Segurança da unidade**.
4. Selecione **Usuários e Grupos**.  
5. Selecione os usuários ou os grupos que precisam acessar este relatório. 
6. Selecione **Salvar**.
7. Na definição de relatório, adicione sua nova definição em árvore.
8. Na definição em árvore, selecione **Configuração**. Em **Seleção de unidade organizacional**, selecione **Incluir todas as unidades**.

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a>Como posso identificar quais contas não correspondem aos meus saldos?

Veja aqui algumas etapas que podem ser executadas para identificar as contas e as variações se você tiver um relatório que não possui saldos correspondentes. 

**Financial Reporter Report Designer**
1. No Financial Reporter Report Designer, crie uma definição de linha. 
2. Selecione **Editar > Inserir Linhas de Dimensões**.
3. Selecione **MainAccount**.  
4. Selecione **OK**.
5. Salve a definição de linha.
6. Crie uma definição de coluna
7. Crie uma definição de relatório.
8. Selecione **Configurações** e desmarque esta opção.  
9. Gere o relatório. 
10. Exporte o relatório para o Microsoft Excel.

**Dynamics 365 Finance** 
1. No Dynamics 365 Finance, vá para **Contabilidade > Consultas e Relatórios > Balancete**.
2. Defina os seguintes parâmetros:
   - **Data de Início** – insira o início do ano fiscal.
   - **Data de Término** – insira a data para a qual você está gerando o relatório.
   - **Dimensão Financeira** – defina este campo como **Conta principal definida**.
 3. Selecione **Calcular**.
 4. Exporte o relatório para o Microsoft Excel.

Agora, você poderá copiar os dados do relatório do Excel do Relator Financeiro para o relatório Balancete a fim de comparar as colunas **Saldo de fechamento**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]