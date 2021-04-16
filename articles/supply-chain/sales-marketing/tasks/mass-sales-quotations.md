---
title: Criar cotações de venda em massa
description: Este procedimento demonstra como criar cotações de forma eficiente que oferecem um conjunto de produtos ou serviços que devem ser enviados a vários clientes.
author: omulvad
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0422817576d9d93d0ec6bbfb5f3777013ee09ece
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817692"
---
# <a name="mass-create-sales-quotations"></a>Criar cotações de venda em massa

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como criar cotações de forma eficiente que oferecem um conjunto de produtos ou serviços que devem ser enviados a vários clientes. A criação de cotação em massa foi baseada em modelos de cotação. Você pode realizar esse procedimento em seus próprios dados ou na empresa USMF de dados de demonstração.


## <a name="create-a-quotation-template"></a>Criar um modelo de cotação
1. Vá para Vendas e marketing > Configuração > Cotações > Grupos de modelo.
2. Clique em Novo.
3. No campo de ID de grupo, digite uma ID de sua escolha.
4. No campo Descrição, digite um valor.
5. Clique em Salvar.
6. Feche a página.
7. Vá para Vendas e marketing > Cotações de venda > Todas as cotações.
8. Clique em Novo.
9. No tipo Conta, selecione 'Cliente'.
10. No campo Conta de cliente, insira ou selecione um valor.
11. Clique em OK.
    * Para que uma cotação se torne um modelo, você deve executar etapas de instalação do cabeçalho da cotação. Isso deve ser feito antes para adicionar linhas à cotação.   
12. No Painel de Ação, clique em Opções.
13. Clique em Alterar exibição.
14. Clique em Exibição do cabeçalho.
15. Expandir a seção Instalação.
16. No campo ID do Grupo, insira ou selecione um valor.
17. No campo Nome de modelo, digite um valor.
18. Selecione Sim no campo Ativo.
    * Somente os modelos ativos podem ser usados quando você aplica um modelo a uma nova cotação de venda.  
19. No Painel de Ação, clique em Opções.
20. Clique em Alterar exibição.
21. Clique em Exibição em linha.
22. No campo Item, insira ou selecione um valor.
23. No campo Item, digite um valor.
24. Feche a página.
25. No campo Percentual de desconto, insira um número.
26. Clique em Adicionar nova linha.
27. No campo Item, insira ou selecione um valor.
28. No campo Item, digite um valor.
29. Feche a página.
30. No campo Preço unitário, insira um novo preço ou altere o atual.
31. Clique em Adicionar nova linha.
32. No campo Item, insira ou selecione um valor.
33. No campo Item, digite um valor.
34. Feche a página.
35. No campo Quantidade, insira um número.
36. No campo Desconto, insira um número.
37. Clique em Salvar.

## <a name="apply-the-template-to-create-a-single-quotation"></a>Aplique o modelo para criar uma única cotação
1. Vá para Vendas e marketing > Cotações de venda > Todas as cotações.
    * Observe que a cotação que você acabou de criar está marcada como modelo.  
2. Clique em Novo.
3. No tipo Conta, selecione 'Cliente'.
4. No campo Conta de cliente, insira ou selecione um valor.
5. Expanda a seção Modelo.
6. No campo ID do Grupo, insira ou selecione um valor.
7. No campo Nome do modelo, insira ou selecione um valor.
8. No campo Método de cálculo, selecione 'Com base em valores modelo'.
9. Clique em OK.
    * A nova cotação agora foi criada, com base nos dados e nas condições do modelo.  
10. Feche a página.
11. Feche a página.

## <a name="apply-the-template-to-mass-create-quotations"></a>Aplique o modelo para criar cotações em massa
1. Vá para Vendas e marketing > Cotações de venda > Atualização da cotação > Criar cotações em massa.
2. No tipo Conta, selecione 'Cliente'.
3. No campo ID do Grupo, insira ou selecione um valor.
4. No campo Nome do modelo, insira ou selecione um valor.
5. No campo Método de cálculo, selecione 'Com base em valores modelo'.
6. Expanda os Registros para incluir a seção.
7. Clique em Filtro.
8. No campo Critérios, defina o filtro para cobrir um intervalo de clientes que você deseja incluir nesta criação de cotação em massa. Use o seguinte formato "Customer1..CustomerN.
    * Por exemplo, você pode definir o filtro: US-001.US-004  
9. Clique em OK.
10. Clique em OK.
11. Vá para Vendas e marketing > Cotações de venda > Todas as cotações.
    * Verifique se as cotações foram criadas para todos os clientes especificados na rotina de atualização em massa, conforme baseado no modelo selecionado.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]