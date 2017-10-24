--- 
title: "Configurar regras de comissão de vendas"
description: "Este procedimento mostra como configurar e habilitar cálculo e controle de vendas."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8d81765884f741443d1c0f5b0cb8bc545945e1a1
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-commission-rules"></a>Configurar regras de comissão de vendas

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar e habilitar cálculo e controle de vendas. Este procedimento mostra como criar grupos de comissão de cliente e item e depois como vincular um cliente e produto selecionado aos respectivos grupos. Esses grupos são usados na configuração do cálculo da comissão para criar uma combinação de cliente, item e representantes de venda que deve ser correspondida pela ordem de venda para que os vendedores tenham direito à comissão. A criação de grupos de comissões de cliente e item é opcional, pois o cálculo da comissão também pode ser feito para um cliente e/ou item individuais. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.


## <a name="set-up-commission-groups-and-commission-rates"></a>Defina grupos de comissões e taxas de comissões.
1. Vá para Vendas e marketing > Comissões > Grupos de cliente para comissão.
2. Clique em Novo.
3. No campo Grupo, digite um valor.
4. No campo Nome, digite um valor.
5. Clique em Salvar.
6. Feche a página.
7. Vá para Vendas e marketing > Comissões > Grupos de itens.
8. Clique em Novo.
9. No campo Grupo, digite um valor.
10. No campo Nome, digite um valor.
11. Feche a página.
12. Vá para Vendas e marketing > Comissões > Grupos de vendas.
    * Um grupo de vendas por comissão especifica os funcionários em funções de representante de vendas que têm o direito a receber uma comissão quando um cliente associado ao grupo de vendas relevante compra determinados itens.  
    * Na empresa de dados de demonstração USMF, há um grupo de vendas chamado "Reps de vendas EUA".  
13. No Painel de Ação, clique em Geral.
14. Clique em Rep. de vendas.
    * A página Rep. de vendas exibe uma lista de vendedores da empresa que estão associados a um grupo de comissões específico. Você pode atribuir vários representantes de vendas ao mesmo grupo e definir suas respectivas cotas da taxa de comissão total como um valor percentual. A cota de comissão total de todos os funcionários não deve exceder 100.  
15. Na lista, marque a linha selecionada.
16. Clique em Editar.
17. Defina a Cota de comissão como '50'.
18. Clique em Novo.
19. No campo Nome, clique no botão suspenso para abrir a pesquisa.
20. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo Nome com um valor de 'Susan Burk'.
21. Clique em Selecionar.
22. Defina a Cota de comissão como '50'.
23. Clique em Salvar.
24. Vá para Vendas e marketing > Comissões > Cálculo de comissão.
    * Na página Cálculo de comissão, você define a taxa de comissão que o funcionário receberá por transações de vendas quando elas contêm a combinação predefinida de cliente e produto. Como parte da configuração da taxa de comissão, você precisa especificar a base do cálculo de comissões e se descontos devem ser incluídos ou excluídos. Você também pode inserir um período de validade para quando a comissão está ativa.  
25. Clique em Novo.
26. No campo Código de item, selecione 'Grupo'.
27. No campo Relação do item, clique no botão suspenso para abrir a pesquisa.
28. Na lista, localize e selecione o grupo que você criou antes.
29. Na lista, clique no link na linha selecionada.
30. No campo Código de cliente, selecione 'Grupo'.
31. No campo Relação de cliente, clique no botão suspenso para abrir a pesquisa.
32. Na lista, selecione o grupo que você definiu antes.
33. No campo Relação de rep. de vendas, clique no botão suspenso para abrir a pesquisa.
34. Na lista, localize e selecione o PDV desejado.
    * Mantenha a opção "Antes de desconto de linha".  
    * Mantenha a opção "Receita" como a base para o cálculo do valor da comissão.    
35. No campo Porcentagem de comissão, insira um número.
36. Clique em Salvar.

## <a name="setting-up-commission-posting"></a>Configuração de lançamento de comissões
1. Vá para Vendas e marketing > Comissões > Lançamento de comissão.
    * Taxas de comissão são pagáveis aos funcionários e, portanto, devem ser configuradas para assegurar um lançamento financeiro correto nas contas apropriadas da contabilidade. Isso é feito na página Lançamento de comissão. Revise a configuração que está disponível para a empresa atual. Normalmente, os valores de comissão são lançados em uma conta de despesas exclusiva e são compensados em uma conta a pagar exclusiva. Se não houver regras de lançamento de comissão configuradas, o sistema não poderá concluir o faturamento de uma ordem de venda com comissões elegíveis.  
2. Feche a página.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Atribua um grupo de comissões a um cliente e produto
1. Vá para Vendas e marketing > Clientes >Todos os clientes.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Clique em Editar.
5. Expanda a seção Padrões da ordem de venda.
6. No campo Grupo de comissões, clique no botão suspenso para abrir a pesquisa.
7. Na lista, selecione o grupo que você criou antes.
8. No campo Grupo de vendas, clique no botão suspenso para abrir a pesquisa.
9. Na lista, localize e selecione o PDV desejado.
10. Clique em Salvar.
11. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
12. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo Número do item com um valor de 'T0020'.
13. Na lista, clique no link na linha selecionada.
14. Clique em Editar.
15. Expanda a seção Venda.
16. No campo Grupo de comissões, clique no botão suspenso para abrir a pesquisa.
17. Na lista, selecione o grupo de comissões que você criou antes.


