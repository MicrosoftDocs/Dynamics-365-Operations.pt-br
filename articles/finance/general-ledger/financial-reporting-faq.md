---
title: Perguntas frequentes sobre relatórios financeiros
description: Este tópico lista perguntas relacionadas a relatórios financeiros de outros usuários.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3f9381f5b656d0cc0b46c8828b2ef9d024e296b0
ms.sourcegitcommit: 14785208d84b2c1efd30f140c52df35a2ccd1577
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "5114720"
---
# <a name="financial-reporting-faq"></a>Perguntas frequentes sobre relatórios financeiros 

Este tópico lista perguntas relacionadas a relatórios financeiros de outros usuários. 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Como posso restringir o acesso a um relatório usando a segurança em árvore?

Cenário: a empresa de demonstração USMF tem um relatório de balanço e não quer que todos os usuários de relatórios financeiros sejam capazes de exibi-lo no D365. Solução: você pode usar a segurança em árvore para restringir o acesso a um único relatório. Assim, apenas determinados usuários podem acessar o relatório. 

1.  Faça login no Report Designer do relator financeiro

2.  Crie uma nova definição de árvore (Arquivo | Novo | Definição de árvore) a.    Clique duas vezes na linha **Resumo** na coluna **Segurança da unidade**.
  i.    Clique em Usuários e Grupos.  
          1. Selecione os Usuários ou Grupo que deseja acessar este relatório. 
          
[![tela do usuário](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)

[![tela de segurança](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)

  b.    Clique em **Salvar**.
  
[![botão salvar](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)

3.  Na Definição de Relatório, adicione sua nova Definição em Árvore

[![formulário definição em árvore](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)

A.  Em Definição em Árvore, clique em Configuração e, em "Seleção da unidade organizacional", marque "Incluir todas as unidades"

[![formulário de seleção da unidade organizacional](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)

**Antes:** [![captura de tela do "antes"](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)

**Depois:** [![captura de tela do "depois"](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)

Observação: o motivo para a mensagem acima é que meu usuário não tem acesso a este relatório depois da aplicação da Segurança da unidade



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a>Como determino quais contas não correspondem aos meus saldos no D365?

Veja aqui algumas etapas que podem ser executadas para identificar as contas e as variações quando você tem um relatório que não corresponde ao que esperava no D365. 

### <a name="in-financial-reporter-report-designer"></a>No Report Designer do relator financeiro

1.  Crie uma Definição de Linha a.    Clique em Editar | Inserir Linhas de Dimensões i.  Selecione MainAccount [![Selecionar conta principal_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)
    
    ii. Clique em OK b.    Salve a Definição de Linha

2.  Crie uma nova Definição de Coluna     [![Criar uma nova definição de coluna](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)

3.  Crie uma nova Definição de Relatório a.    Clique em Configurações e desmarque o [![formulário Configurações](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)
   
4.  Gere o relatório. 

5.  Exporte o relatório para o Excel.

### <a name="in-d365"></a>No D365: 
1.  Clique Contabilidade | Consultas e Relatórios | Balancete a.    Parâmetros i.  Data inicial: início do ano fiscal ii. Data final: data para a qual o relatório foi gerado iii.    Conjunto de dimensões financeiras "Conjunto de contas principais" [![formulário Conta Principal](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)
      
  b.    Clique em Calcular

2.  Exporte o relatório para o Excel

Agora, você poderá copiar os dados do relatório do Excel de FR e para o relatório Balancete do D365 e comparar as colunas "Saldo de fechamento".


[!INCLUDE[footer-include](../../includes/footer-banner.md)]