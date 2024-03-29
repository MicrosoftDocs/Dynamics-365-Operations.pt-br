---
title: Criar um novo contrato comercial
description: Este procedimento mostra como criar um contrato comercial no qual você registra um novo preço de venda de produtos que você combinou com um cliente específico.
author: Henrikan
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24290ec873da9e871c001bcdc97e14dcad0e3d1e
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111097"
---
# <a name="create-a-new-trade-agreement"></a>Criar um novo contrato comercial

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um contrato comercial no qual você registra um novo preço de venda de produtos que você combinou com um cliente específico. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Se você estiver usando seus próprios dados, antes de iniciar esse guia será preciso ter certeza de que um Nome de diário de contratos comerciais existe onde a Relação padrão está definida como "Preços (vendas)".

## <a name="create-and-post-a-new-trade-agreement-journal"></a>Criar e lançar um novo diário de contratos comerciais.

1. Acesse **Painel de navegação > Módulos > Vendas e marketing > Preços e descontos > Diários de contratos comerciais**.
2. Clique em **Novo**.
3. No campo **Nome**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o PDV desejado.
5. No **Painel de Ações**, clique em **Linhas**.
6. No campo **Código da conta**, selecione 'Tabela'.
    
    Neste exemplo, você está atualizando o preço para um cliente específico, o que significa quem você precisa selecionar Tabela. Se você estava atualizando o preço da lista de produtos, selecionaria 'Todos'; assim, o novo preço seria válido para todos os clientes. Se você estava diferenciando preços entre diferentes segmentos de clientes, então você deve selecionar Grupo. Para selecionar Grupo, é necessário configurar Grupos de preços ao cliente.  

7. No campo **Seleção de conta**, clique no botão suspenso para abrir a pesquisa.
8. Na lista, localize e selecione o PDV desejado.
9. No campo **Código do item**, selecione 'Tabela'.
    
    Quando você está inserindo um contrato comercial do tipo 'Preço (vendas)', deve selecionar apenas 'Tabela' no campo **Código do item**. Isso ocorre porque um preço é um valor absoluto e não pode ser o mesmo para todos os produtos ou para um grupo de produtos.
    
10. No campo **Relação do item**, clique no botão suspenso para abrir a pesquisa.
11. Na lista, selecione o produto que deseja incluir no contrato. Faça uma nota dos produtos que você selecionou.  
12. No campo **De**, insira uma quantidade mínima.
    - Se o cliente precisa solicitar uma quantidade mínima para se qualificar para o novo preço, especifique essa quantidade aqui.  
    - Insira um valor no campo **Para** para especificar a quantidade máxima acima da qual o preço do contrato não será válido. Se você oferecer preços e descontos com base em múltiplas divisões de quantidade, especifique cada faixa de quantidade como um par de quantidade mínima e máxima nos campos **De** e **Para**, respectivamente.
13. No campo **Valor em moeda**, insira um preço.
14. Na seção **Detalhes**, no campo **Data inicial**, insira uma data a partir da qual esse contrato será válido.
15. Clique em **Salvar**.
16. Clique em **Validar**.
17. Clique em **Validar as linhas selecionadas**.
18. Clique em **OK**.
19. Clique em **Enviar**.
20. Clique em **OK**.

## <a name="view-trade-agreements-for-a-product"></a>Exibir contratos comerciais para um produto

1. Acesse **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.
2. Na lista, localize e selecione o produto cujo preço você acabou de atualizar.
3. No **Painel de Ação**, clique em **Vender**.
4. Clique em **Exibir contratos comerciais**.
    
    Revise os detalhes do contrato comercial de preço que acabou de criar.

5. Feche a página.

## <a name="additional-resources"></a>Recursos adicionais

### <a name="whitepaper"></a>White paper

Para obter mais informações, baixe o white paper a seguir (escrito para dar suporte a AX2012, mas ainda é aplicável ao Dynamics 365 Supply Chain Management)

- [Contratos Comerciais](https://download.microsoft.com/download/0/2/9/02972c8b-0159-4936-a3ef-1e64252b2d2f/TradeAgreementsInAX.pdf)

### <a name="community-blogs"></a>Blogs da comunidade

- [Preços de venda em finanças e operações](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
