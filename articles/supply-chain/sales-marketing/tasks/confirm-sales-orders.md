---
title: Confirmar ordens de venda
description: Este procedimento demonstra como confirmar ordens de venda.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup, SalesUnconfirmedOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f53fea1c1a998b5d3ec4669d772ace2561cb2cec
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252741"
---
# <a name="confirm-sales-orders"></a>Confirmar ordens de venda

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como confirmar ordens de venda. Será mostrado a você como confirmar uma única ordem, e como confirmar várias ordens de uma só vez. Essas tarefas seriam normalmente realizadas por um processador de ordens de venda. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados. Antes de começar, verifique se existem várias ordens de venda em aberto para o mesmo cliente. Se você estiver usando USMF, é possível usar o cliente US-027.


## <a name="confirm-a-single-sales-order"></a>Confirmar uma única ordem de venda
1. Vá para **Painel de navegação > Módulos > Vendas e marketing > Ordens de venda > Todas as ordens de venda**.
2. Na lista, localize e selecione a ordem que você deseja confirmar.
3. Clique no link no número da ordem de venda para abrir a ordem selecionada.
4. No **Painel de Ações**, clique em **Vender**.
5. Clique em **Confirmar ordem de venda**.
6. Expanda a seção **Parâmetros**. Verifique se a opção **Lançamento** está definida como 'Sim'.  
7. Defina a opção **Imprimir confirmação** como 'Sim'. O campo **Verificar limite de crédito** especifica o método usado para calcular o crédito restante de um cliente. Por padrão, ele é copiado da página Parâmetros de contas a receber. Para ignorar a verificação de limite de crédito ao confirmar uma ordem de venda específica, defina **Verificar limite de crédito** como 'Nenhum'. No entanto, você deve estar ciente de que mesmo com este campo definido como 'Nenhum', a verificação de limite de crédito será executada se a opção **Limite de crédito obrigatório** estiver selecionada nos dados mestres do cliente. 
8. Clique em **OK**.
9. Clique em **Sim**.
10. Feche a página.
11. No **Painel de Ação**, clique em **Opções**.
12. Clique em **Alterar exibição**.
13. Clique em **Exibição do cabeçalho**. Quando uma ordem é confirmada, o **Status do documento** é definido como 'Confirmação'. 
14. No **Painel de Ações**, clique em **Vender**.
15. Clique em **Confirmação de ordem de venda**.
16. Feche a página.

## <a name="confirm-multiple-sales-orders-at-once"></a>Confirmar várias ordens de venda de uma vez
1. Vá para **Vendas e marketing > Ordens de venda > Confirmação da ordem > Confirmar ordem de venda**.
2. Clique em **Selecionar**.
3. Na lista da guia **Intervalo**, localize e selecione o registro que faz referência ao campo **Conta de cliente**.
4. No campo **Critérios**, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione a conta de cliente que contêm várias ordens que você deseja confirmar em massa. Se você estiver usando USMF, é possível selecionar a conta US-027.  
6. Clique em **OK**.
    - A guia **Visão geral** exibe uma lista de ordens que correspondem aos critérios de consulta. Essas serão incluídas na confirmação.  
    - O campo **Atualização resumida de** na seção **Parâmetros** especifica o parâmetro pelo qual as diversas ordens devem ser resumidas em um documento de confirmação. Por padrão, a opção é copiada da configuração **Valores padrão da atualização resumida** na página **Parâmetros de contas a receber**.  
7. No campo **Atualização resumida de**, selecione 'Ordem'. Os parâmetros mínimos necessários para criar atualizações resumidas são **Conta de fatura** e **Moeda**. Isso significa que atualizações resumidas que têm tanto contas de fatura como moedas diferentes não serão permitidas. Parâmetros adicionais podem ser configurados na página **Parâmetros de atualização resumida**, que pode ser acessada pela página **Parâmetros de contas a receber**. 
8. No campo **Ordem de venda**, clique no botão suspenso para abrir a pesquisa.
9. Na lista, selecione o número da ordem que você deseja que seja a ordem resumida.
10. Clique em **Organizar**.
11. Clique em **OK**.
12. Clique em **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]