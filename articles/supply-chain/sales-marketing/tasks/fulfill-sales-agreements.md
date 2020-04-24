---
title: Cumprir contratos de venda
description: Este procedimento mostra como atender a um contrato de venda associando ordens de venda a ele.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51ea8afc7c2f683790f697185d6637e0d24462fc
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204300"
---
# <a name="fulfill-sales-agreements"></a>Cumprir contratos de venda

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como atender a um contrato de venda associando ordens de venda a ele. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Antes de iniciar esta guia, certifique-se de que tem um contrato de venda efetivo do tipo "Compromisso de valor do produto". Como alternativa, você pode executar a guia de tarefas chamada "Criar contratos de venda".  




## <a name="release-a-sales-order-from-the-agreement"></a>Liberar uma ordem de venda do contrato
1. Vá para Vendas e marketing > Contratos de venda > Contratos de venda.
2. Na lista, abra o contrato com o qual você deseja liberar a ordem.
3. No Painel de Ação, clique em Contrato de venda.
4. Clique em Liberar ordem.
    * Como indica o texto na parte superior da pagina Criar ordem de liberação, os detalhes necessários para as linhas da ordem de venda serão diferentes, dependendo se o contrato é baseado em quantidade ou em valor.  
    * O contrato nessa guia é do tipo "Compromisso de valor do produto". Este é o motivo pelo qual a seção Linhas desta página está em branco. Se o compromisso fosse baseado na quantidade, as informações da linha seriam copiadas do contrato.  
5. Clique em Criar.
    * A mensagem informa que a ordem de vendas foi criada. Como a ordem não contém nenhuma linha, você deve adicionar os detalhes da linha da ordem para concluir o processo de liberação.   
6. Feche a página.
7. Feche a página.
8. Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.
9. Na lista, localize e abra a ordem que foi criada como resultado da versão da ordem na tarefa anterior.
10. Clique em Adicionar nova linha.
11. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
12. No campo Número do item, digite ou selecione o item que é especificado no contrato de venda associado.
13. No campo Quantidade, insira um número.
    * Certifique-se de inserir uma quantidade que coloque o Valor líquido abaixo do valor do contrato de venda associado.  
    * Observe que como a ordem de venda está vinculada ao contrato, a porcentagem de desconto negociada será aplicada à linha da ordem.  
14. Clique em Atualizar linha.
15. Clique em Anexado.
    * A página Contrato anexado mostra o ID e as condições do contrato dos quais a linha é liberada.  
16. Feche a página.
17. No Painel de Ação, clique em Geral.
18. Clique em Contrato de venda anexado.
19. Expanda a seção Detalhes da linha.
20. Clique na guia Atendimento.
    * A guia Atendimento mostra um resumo de todas as linhas da ordem de venda associadas a esse compromisso, e o estado de atendimento, bem como o valor ou a quantidade que ainda não foram liberados.   
21. Feche a página.
22. Feche a página.
23. Feche a página.

## <a name="apply-sales-agreement-in-the-order-process"></a>Aplicar contrato de venda no processo de ordem
1. Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o cliente especificado no contrato de venda.
5. Na lista, clique no link na linha selecionada.
6. Expanda a seção Geral.
7. No campo ID do contrato de venda, clique no botão suspenso para abrir a pesquisa.
8. Na lista, clique no link na linha selecionada.
9. Clique em Sim.
10. Clique em OK.
11. Na lista, marque a linha selecionada.
12. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
13. No campo Número do item, digite ou selecione o item que é especificado no contrato de venda associado.
14. Na lista, clique no link na linha selecionada.
15. Clique em Salvar.
16. No Painel de Ação, clique em Separar e empacotar.
17. Clique em Lançar guia de remessa.
18. Expanda a seção Parâmetros.
19. Selecione Sim no campo Lançamento.
20. Clique em OK.
21. Clique em OK.
22. No Painel de Ação, clique em Geral.
23. Clique em Contrato de venda anexado.
24. Clique na guia Atendimento.

