---
title: Visão geral do módulo de gerenciamento de reembolso
description: Este tópico fornece uma visão geral do módulo de gerenciamento de reembolso para o Microsoft Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 577d48e207c8ce5911d104e657101a8557100064
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6339985"
---
# <a name="rebate-management-module-overview"></a>Visão geral do módulo de gerenciamento de reembolso

[!include [banner](../includes/banner.md)]

Você pode usar o módulo **Gerenciamento de reembolso** para criar acordos ou contratos entre sua empresa e clientes ou fornecedores, de forma que possa calcular reembolsos, deduções e royalties. O gerenciamento de reembolso rastreia e mantém transações de reembolso e dedução em um local central em que os usuários podem criá-las, examiná-las e processá-las efetivamente.

O gerenciamento de reembolso oferece suporte à criação, manutenção e processamento de *reembolsos*. Um reembolso é a devolução de parte do preço de compra por um vendedor ou comprador. Geralmente, os reembolsos se baseiam na compra de uma quantidade ou valor específico de mercadorias durante um período específico. Diferente dos descontos, os reembolsos são feitos depois do faturamento total do valor da compra.

O gerenciamento de reembolso também oferece suporte a *deduções*. Uma dedução é uma compensação, uma consideração ou uma taxa que é paga para uma licença ou o privilégio de usar propriedade intelectual, como uma marca, um direito autoral ou uma patente, ou o privilégio de usar um recurso natural para uma finalidade, como pesca, caça ou mineração. As deduções geralmente são calculadas como uma porcentagem da receita ou do lucro do uso realizado. Quanto mais a propriedade intelectual ou o recurso natural for usado, maior será a dedução realizada.

Além disso, o gerenciamento de reembolso oferece suporte a *royalties* do cliente. Os royalties são pagamentos que uma entidade faz ao licenciado ou a franquia pelo direito de usar um ativo.

O gerenciamento de reembolso permite definir perfis de lançamentos para provisões, reembolsos e amortizações. Além disso, os lançamentos podem ser definidos para um cliente ou fornecedor específico. Dessa forma, os acordos que não se aplicam a todos os cenários de clientes ou fornecedores podem ser rastreados por meio de lançamentos.

As transações de reembolso são geradas automaticamente, com base no método de cálculo selecionado e agendado em trabalhos em lotes. Além disso, você pode configurar fluxos de trabalho para gerenciar, analisar e aprovar contratos.

## <a name="basis-calculation"></a>Cálculo de base

Os reembolsos de clientes, os royalties de clientes e os reembolsos de fornecedores podem usar uma base diferente, de acordo com as necessidades comerciais:

- Os reembolsos do cliente podem se basear em ordens de venda, notas de entrega ou faturas.
- Os royalties do cliente podem se basear em ordens de venda, notas de entrega ou faturas pagas.
- Os reembolsos do fornecedor podem se basear em ordens de compra ou ordens de venda. Eles podem ser calculados com base em produtos que são comprados do fornecedor de reembolso e vendidos para clientes por meio de faturas de vendas.

## <a name="flexible-calculations"></a>Cálculos flexíveis

Os períodos de cálculo de reembolso estão disponíveis para acordos de clientes e de fornecedores. Um período de cálculo define a duração do acordo, a frequência de cálculo e o período de cálculo. Os reembolsos podem ser acumulados com base nas quantidades de ordem de venda ou em valores de produtos qualificados durante o período de reembolso.

Para cada cálculo de contrato, um dos seguintes períodos pode ser definido:

- Fatura
- Dia
- Semana
- Mês
- Trimestre
- Ano
- Período personalizado
- Qualquer múltiplo dos períodos listados anteriormente

O cálculo pode ser aplicado a clientes e produtos individuais, grupos de clientes e produtos, ou todos os clientes e produtos. Os reembolsos com várias linhas de detalhes podem ter intervalos de datas qualificados diferentes. Os períodos de provisão e de declaração podem ser diferentes. Por exemplo, as provisões podem ser processadas todo dia, enquanto as declarações são processadas uma vez por mês.

Os reembolsos podem ser configurados com base em vários parâmetros diferentes. Por exemplo, eles podem ser configurados como uma porcentagem, uma taxa ou um valor fixo. Há quatro métodos de cálculo principais:

- Em etapas
- Cumulativo
- Contínuo
- Valor total

Os resultados do cálculo de reembolso também podem ser reduzidos por outros reembolsos. É preciso saber se o desconto está configurado para ser calculado com base no valor líquido.

No fornecedor, os reembolsos que são baseados em ordens de venda podem calcular o preço com base em uma regra PEPS (primeiro a entrar, primeiro a sair), o último preço de compra, o preço médio de compra ou o preço de venda.

## <a name="rebate-target-transactions"></a>Transações de destino de reembolso

As saídas geradas pelo acordo ou contrato de reembolso podem ser finanças ou itens.

As saídas financeiras são determinadas pelo tipo de pagamento atribuído ao contrato pelo perfil de lançamento. Essas saídas podem incluir diários de dedução do cliente, faturas de texto livre e faturas de fornecedor. Para fins de auditoria, as transações de destino de reembolso financeiro incluem uma referência ao acordo de reembolso original.

Saídas de itens criam uma ordem de venda de item livre para reembolsos de clientes e uma ordem de compra para reembolsos de fornecedores As transações de destino de reembolso de item contêm opções para determinar qual referência de reembolso deve ser inserida na ordem de compra ou de venda do item livre.

## <a name="accurate-rebate-calculations"></a>Cálculos de reembolso precisos

A combinação de acordos associados, frequência dos cálculos, base de cálculo e método de cálculo selecionado determina a precisão dos cálculos de reembolso. As provisões de reembolso podem ser usadas para acumular valores lançados e reivindicados.

Os provisionamentos podem ser gerenciados diariamente, semanalmente, mensalmente ou de acordo com um período personalizado. No entanto, a funcionalidade pode alocar ou pagar o reembolso, ou receber o pagamento dele, em qualquer frequência definida que seja da mesma duração ou maior do que a frequência de provisão. A baixa usa a mesma frequência do reembolso. Os usuários podem ajustar facilmente um plano ou valores de pagamento a qualquer momento durante o pagamento.

Os usuários não precisam mais lidar com acordos ou provisões em duas etapas. As provisões e as amortizações são lançadas diretamente no razão. Além disso, as notas de crédito podem ser criadas automaticamente. Portanto, há integração total com contas a pagar e contas a receber. Durante o processamento, os cálculos podem considerar descontos de liquidação, faturas pagas, descontos comerciais e notas de crédito existentes para garantir que os valores e as quantidades sejam calculados com precisão.

Quando os reembolsos são calculados, o processo cria transações que podem ser analisadas antes do lançamento. Um processo separado lança transações de gerenciamento reembolso. Em seguida, é possível criar um diário, uma nota de crédito ou uma transação de débito durante o lançamento das transações propostas. É possível obter instruções de relatório e listagens de transações para garantir a conformidade, a eficácia e a transparência.


## <a name="guaranteed-royalty-payments"></a>Pagamentos de royalties garantidos

No gerenciamento de reembolsos, a geração automática de pagamento permite que royalties sejam tratados de modo rápido e fácil, mesmo quando a garantia mínima se aplica. 

## <a name="maximizing-spend-versus-rebates"></a>Maximização de gastos x reembolsos

Os fornecedores e produtos podem ser agrupados por região e diferentes ofertas podem ser fornecidas, dependendo do país ou região da transação. Quando os usuários selecionam produtos, eles podem definir os itens incluídos e o número de itens que serão usados na liquidação de reembolsos.
