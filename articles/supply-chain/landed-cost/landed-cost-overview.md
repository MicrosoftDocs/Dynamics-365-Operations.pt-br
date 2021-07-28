---
title: Módulo de custo de entrega
description: O módulo de custo de entrega ajuda as empresas a simplificar as operações de remessa de entrada, permitindo que os usuários concluam o controle financeiro e logístico sobre o frete importado, do fabricante ao depósito.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e646b5fed29aa4c6e67a83703a51c4a322a1918b
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6338414"
---
# <a name="landed-cost-module"></a>Módulo de custo de entrega

[!include [banner](../../includes/banner.md)]

O módulo **Custo de entrega** ajuda as empresas a simplificar as operações de remessa de entrada, permitindo que os usuários concluam o controle financeiro e logístico sobre o frete importado, do fabricante ao depósito. Para mercadorias importadas, os custos de entrega podem contabilizar 40% ou mais do custo total de cada item importado. Portanto, o desafio é fornecer estimativas precisas para custos de entrega.

As empresas podem usar o custo de entrega para concluir as seguintes tarefas:

- Estime os custos de entrega na criação da hora da viagem.
- Distribua custos de entrega a vários itens e ordens de compra ou ordens de transferência em uma única viagem.
- Suporte a transferência de mercadorias entre locais físicos reconhecendo custos de entrega.
- Reconheça acúmulos de mercadorias em trânsito.

O custo de entrega fornece estimativas de custo precisas e oportunas para custos de entrega indiretos. Ao mesmo tempo, ele oferece uma maior visibilidade financeira e logística na cadeia de suprimentos estendida. Isso também ajuda a reduzir a administração de erros de custos e custos.

## <a name="highlights"></a>Destaques

### <a name="voyages"></a>Viagens

No custo de entrega, uma viagem é um movimento distinto de um local de saída, por meio de um conjunto específico de destinos em um período específico, para um local de depósito de entrada especificado. As ordens de compra e linhas de ordem podem ser adicionadas a um único contêiner ou a vários contêineres para uma viagem, e os custos serão corretamente alocados novamente para a linha do item. Também é possível adicionar ordens e linhas de ordem em entidades legais para uma única viagem.

### <a name="item-ownership"></a>Propriedade de item

No Microsoft Dynamics 365 Supply Chain Management, as mercadorias são normalmente recebidas no destino do depósito e, em seguida, faturadas. No entanto, na maioria dos acordos comerciais internacionais, uma empresa se apropria das mercadorias do momento em que deixam a porta original antes de serem fisicamente recebidas. O custo de entrega habilita empresas a faturar mercadorias antes do recebimento físico delas. Esse conceito é conhecido como uma ordem de mercadorias em trânsito. Ele cria um novo tipo de ordem para gerenciar o recebimento de mercadorias depois do faturamento da ordem de compra original.

### <a name="costs"></a>Custos

Quando você cria uma viagem no custo de entrega, os custos podem ser adicionados automaticamente a ela. Esses custos são configurados no custo de entrega; várias opções de custo e bases de custo estão disponíveis para eles. Cada custo pode ser configurado para diferentes níveis de uma viagem e distribuído para o nível de item por meio de regras de divisão que dão suporte a quantidade, volume, peso, valor e divisores volumétricos definidos. Esses custos estimados fornecem uma estimativa precisa de todos os custos de uma viagem.

O custo de entrega executa um lançamento/acúmulo preliminar dos custos de entrega estimados para garantir que um cálculo preciso dos custos estimados seja fornecido no momento da criação da viagem. À medida que esses custos automáticos são faturados, os custos estimados são revertidos e substituídos pelos custos reais, com base nas faturas de custo.

Os custos reais são custos estimados revertidos que são lançados no momento do faturamento de custo, usando contas de compensação que são configuradas para cada tipo de custo (por exemplo, imposto, frete e seguro). Esses lançamentos seguem o comportamento de lançamento associado ao item específico. Eles atualizam automaticamente o lançamento de estoque, seja o tipo de lançamento o primeiro a entrar, primeiro a sair (PEPS), o último a entrar, primeiro a sair (UEPS), a média ponderada móvel ou a média móvel. Há suporte para todos os tipos de lançamento do grupo de modelos de estoque. Para a média móvel e lançamento de custo padrão, as contas de variação de preço de compra estão disponíveis para lançar as diferenças entre custos estimados e custos reais.

### <a name="item-and-order-tracking"></a>Acompanhamento de itens e ordens

À medida que a viagem se desloca do local de saída de origem para o depósito de destino final, os usuários podem atualizar cada etapa, ou *trecho*, da viagem, conforme necessário. Para cada trecho, um prazo de entrega e um status de remessa são identificados. As datas de entrega confirmadas para movimentação para o próximo trecho do percurso também são identificadas. Juntas, essas datas de entrega fornecem uma data de entrega estimada das mercadorias para o depósito de entrada. Os usuários podem alterar essas datas de entrega. Nesse caso, a data de entrega estimada das mercadorias é atualizada automaticamente, com base nos prazos de entrega e nos trechos do percurso. A visibilidade de mercadorias em trânsito por viagem e embarcação está disponível em uma base por contêiner antes do recebimento das mercadorias. Como as datas são atualizadas em cada linha da ordem de compra, as empresas têm mais controle sobre a logística e o planejamento de depósito.

## <a name="landed-cost-concepts"></a>Conceitos de custo de entrega

A tabela a seguir resume alguns conceitos principais do custo de entrega.

| Conceito | Descrição |
|---|---|
| Viagem | Uma viagem costuma ser uma embarcação. No entanto, dependendo das práticas e dos procedimentos, ela pode ser um fornecedor ou uma ordem de compra. Não há limitações quanto ao uso deste conceito. |
| Fólio | Um fólio costuma ser determinado pelas regulamentações alfandegárias. Ele consiste em mercadorias de um fornecedor para uma entidade/empresa por remessa. As mercadorias em um fólio podem estar em um contêiner ou espalhadas entre vários contêineres. |
| Contêiner de remessa | Os contêineres de remessa armazenam linhas de ordem de compra. Eles estão a um nível abaixo do nível de remessa. Normalmente, eles são usados se os custos são distribuídos para mercadorias por contêiner ou se o recebimento é feito por contêiner. |
| Tipo de contêiner de remessa | Os tipos de contêiner de remessa podem determinar o preço de um tipo de custo (por exemplo, frete). Eles também fornecem informações de remessa úteis. |
| Tipo de custo | Os tipos de custo identificam os custos associados a importações, como imposto, frete e seguro. |
| Custo automático | Os custos automáticos funcionam como contratos comerciais. Um custo automático é vinculado a um nível de viagem. |
| Porta | Portas são áreas nas quais as mercadorias são recebidas e transferidas. |
| Embarcação | Uma embarcação é o meio usado para transportar mercadorias, como navio ou avião. |
| Mercadorias em trânsito | Dependendo das configurações, as mercadorias são colocadas em um depósito em trânsito após a atualização de uma fatura. |
| Atividade | As atividades podem ser usadas para armazenar cada etapa significativa do percurso entre duas portas. Elas podem ser usadas para atualizar datas. |
| Modelo de percurso | Os modelos de percurso são roteiros das mercadorias entre duas portas. |

Para uma comparação entre a terminologia e os recursos dos módulos **Custo de entrega** e **Gerenciamento de transporte** (TMS), consulte [Custo de entrega x Gerenciamento de transporte](landed-cost-vs-tms.md).
