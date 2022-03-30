---
title: Sincronizar sob demanda com o mecanismo de preços do Supply Chain Management
description: Este tópico descreve como usar o mecanismo de preços no Microsoft Dynamics 365 Supply Chain Management do Microsoft Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6b0cc8f403be866ff00b89a33f6c59089c987bb0
ms.sourcegitcommit: 9c19898e1f41495f804c7f07e2636b53a098c4c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2022
ms.locfileid: "8402821"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Sincronizar sob demanda com o mecanismo de preços do Supply Chain Management

[!include [banner](../../includes/banner.md)]

O Microsoft Dynamics 365 Supply Chain Management inclui um mecanismo de preços que lida com acordos comerciais, listas de preços, programas de fidelidade do cliente, promoções e descontos. O mecanismo de preços usa regras complexas para determinar o melhor preço para uma determinada cotação ou ordem. Ao usar a gravação dupla, você usa os preços estáticos ou o mecanismo de preços do Supply Chain Management nas páginas **Cotação** e **Ordem** no Microsoft Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Usar o mecanismo de preços do Supply Chain Management no Sales

1. No Sales, acesse **Vendas \> Ordens**.
1. Selecione **Novo** para criar uma ordem ou selecione uma ordem existente na lista **Minhas ordens**.
1. Adicione uma nova linha de ordem.
1. Se você estiver criando uma ordem, selecione **Ordem de preço** no Painel de Ação. Se você estiver atualizando uma ordem existente, selecione **Recalcular** no Painel de Ação.
1. As seguintes colunas são preenchidas automaticamente:

    - Valor Detalhado
    - % de desconto
    - Desconto
    - Valor sem Frete
    - Valor do Frete
    - Imposto Total
    - Valor Total

> [!NOTE]
> Um processo semelhante se aplica ao criar cotações.

## <a name="how-it-works"></a>Como funciona

Quando você cria uma ordem em Vendas, essa ordem é imediatamente sincronizada com o Supply Chain Management usando os valores inseridos em Vendas. Quando você seleciona **Ordem de preço** ou **Cotação de preço** em Vendas, o Supply Chain Management calcula o preço de cada linha da ordem e a ordem total, com base nas regras do contrato comercial definidas no Supply Chain Management. Os novos valores calculados são sincronizados novamente com as Vendas.

## <a name="set-trade-agreement-evaluation-options-in-supply-chain-management"></a>Definir opções de avaliação de contrato comercial no Supply Chain Management

Você pode configurar o Supply Chain Management para respeitar ou ignorar contratos comerciais ao calcular o preço de uma ordem criada em Vendas. Siga estas etapas para configurar essa opção.

1. Entre no ambiente Supply Chain Management.
1. Acesse **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
1. Na guia **Preços**, na guia rápida **Avaliação de contrato comercial**, adicione ou remova a linha da política de **Entrada manual** conforme necessário. A presença ou a ausência dessa política controla se o mecanismo de definição de preços do Supply Chain Management anulará automaticamente o preço de venda inserido em Vendas.

    - Se a política de **Entrada manual** *não* estiver presente na configuração de **Avaliação de contrato comercial**, o Supply Chain Management é o preço principal. Quando um usuário seleciona **Ordem de preço** ou **Cotação de preço** no Painel de Ações em Vendas, o mecanismo de preços do Supply Chain Management é chamado, e o preço de venda inserido em Vendas é substituído, a menos que seja igual ao preço de venda calculado no Supply Chain Management.
    - Se a política de **Entrada manual** *estiver* presente na configuração de **Avaliação de contrato comercial**, Vendas é o preço principal. O preço de venda inserido em Vendas não é impedido de ser substituído automaticamente quando um usuário seleciona **Ordem de preço** ou **Cotação de preço** no Painel de Ações em Vendas.
    - As linhas da ordem e as linhas da cotação que têm um **preço por unidade** e/ou um valor de **desconto** de *0* (zero) em Vendas são tratadas como um caso especial. Se um preço de contrato comercial relevante estiver disponível, o Supply Chain Management *sempre* o aplicará a esses campos, independentemente da configuração de **Avaliação de contrato comercial**.

    Veja um exemplo de cada um desses casos nos cenários a seguir.

## <a name="example-scenario-1-trade-agreement-evaluation-without-the-manual-entry-option"></a>Exemplo de cenário 1: Avaliação de contrato comercial sem a opção Entrada manual

Nesse cenário, a configuração de **Avaliação de contrato comercial** no Supply Chain Management *não* inclui a política de **Entrada manual**. Um usuário de Vendas insere uma linha de ordem com um preço de venda diferente de zero em Vendas, e nenhum preço de venda é definido para o item no Supply Chain Management.

1. Em Vendas, um usuário cria uma linha de ordem com um valor de **preço por unidade** de 1 dólar (USD).
1. A linha da ordem é sincronizada com o Supply Chain Management com um preço de venda de 1 USD.
1. Em Vendas, o usuário seleciona **Ordem de preço** no Painel de Ações.
1. O Supply Chain Management pesquisa os preços e descontos relevantes e calcula os totais. Como o item não tem um preço de venda no Supply Chain Management, o cálculo atualiza a linha de modo que ele tenha um preço de venda de 0 USD.
1. O novo preço de venda da linha é sincronizado novamente com as Vendas.
1. O resultado é uma linha de ordem em Vendas que tem um preço de venda de 0 USD.

## <a name="example-scenario-2-trade-agreement-evaluation-with-the-manual-entry-option"></a>Exemplo de cenário 2: Avaliação de contrato comercial com a opção Entrada manual

Nesse cenário, a configuração de **Avaliação de contrato comercial** no Supply Chain Management *inclui* a política de **Entrada manual**. Um usuário de Vendas insere uma linha de ordem com um preço de venda diferente de zero em Vendas. O Supply Chain Management inclui um contrato comercial que define um preço de venda de 2 USD para o item encomendado.

1. Em Vendas, um usuário cria uma linha de ordem para um item com um valor de **preço por unidade** de 1 USD.
1. A linha da ordem é sincronizada com o Supply Chain Management com um preço de venda de 1 USD.
1. Em Vendas, o usuário seleciona **Ordem de preço** no Painel de Ações.
1. Como a configuração de **Avaliação de contrato comercial** no Supply Chain Management inclui a política de **Entrada manual**, o preço de venda não muda, mesmo que um contrato comercial aplicável especifique outro preço de venda.
1. O preço de venda permanece inalterado em Vendas e em Supply Chain Management.

## <a name="example-scenario-3-trade-agreement-evaluation-for-an-item-that-has-a-sales-price-of-zero-in-sales"></a>Cenário 3: avaliação de contrato comercial de um item com um preço de venda igual a zero em Vendas

Nesse cenário, a configuração de **Avaliação de contrato comercial** no Supply Chain Management *inclui* a política de **Entrada manual**. O usuário de Vendas insere uma linha de ordem com um preço de venda igual a 0 (zero) em Vendas. O Supply Chain Management inclui um contrato comercial que define um preço de venda de 2 USD para um item encomendado.

1. Em Vendas, um usuário cria uma linha de ordem com um valor de **preço por unidade** de 0 USD e um valor de **desconto de linha** de 0 USD.
1. A linha da ordem é sincronizada com o Supply Chain Management com um preço de venda de 0 USD.
1. Como recebeu uma linha da ordem com um preço de venda igual a 0 (zero), o Supply Chain Management chama o mecanismo de precificação, mesmo que a opção de **Entrada manual** esteja habilitada. O mecanismo de precificação retorna o preço de venda de 2 USD estabelecido pelo contrato comercial e atualiza a linha da ordem no Supply Chain Management.
1. O preço de venda atualizado ainda não foi sincronizado com a linha da ordem em Vendas.
1. Em Vendas, o usuário seleciona **Ordem de preço** no Painel de Ações.
1. A linha da ordem no Supply Chain Management mantém seu preço de venda 2 USD, que agora é sincronizado com as Vendas. Portanto, o valor de **preço por unidade** da linha da ordem em Vendas é atualizado de 0 USD para 2 USD.
1. Em Vendas, o usuário insere um novo valor de **desconto de linha** de 0,50 USD. As Vendas agora calculam que o **Valor estendido** da linha é de 1,50 USD.
1. A linha da ordem é sincronizada com o Supply Chain Management com um valor de **Desconto de linha** de 0,50 USD.
1. Em Vendas, o usuário seleciona **Ordem de preço** no Painel de Ações.
1. Nenhum preço ou desconto é alterado para a linha da ordem em Vendas.

## <a name="limitations"></a>Limitações

Quando as colunas no Sales são preenchidas, as seguintes limitações se aplicam:

- A configuração de encargos e alocações de encargos no Supply Chain Management não é replicada no Sales.
- Os preços não consideram os preços especiais de varejo especificados na coluna **Canal de Varejo** na página da linha de ordem de venda no Supply Chain Management.
- Os descontos definidos na seção **Gerenciamento de bonificação comercial** do Supply Chain Management não são considerados.
- O preço não considera os contratos de venda.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
