---
title: Planejamento de modo misto - Combinar discreto, processo e lean sourcing
description: Este tópico fornece informações sobre planejamento de modo misto.
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9186d69e86798a5bd6541432518e407eff5700cc
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250040"
---
# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>Planejamento de modo misto - Combinar discreto, processo e lean sourcing

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre planejamento de modo misto. No planejamento de modo misto, você pode modelar sua cadeia de fornecedor baseada no fluxo de material. O Dynamics 365 Supply Chain Management garante que o fluxo de material segue seus modelos, independentemente da política de fornecimento que é selecionada (kanbans, ordens de produção, ordens de compra, ordens de lote ou ordens de transferência). 

Você pode selecionar a estratégia geral para fornecer um produto, seja qual for a estrutura de produtos.  

Por exemplo, você pode ter o controle do kanban no assembly, onde o material é originário da área do assembly por ordens de produção, kanbans, transferências, ordens de lote ou qualquer combinação adequado às características da sua cadeia de fornecimento, mas você ainda pode ter visibilidade total em fornecimentos. Este recurso resulta em processos otimizados da cadeia de suprimentos e na visibilidade avançada na cadeia de suprimentos.  

A granularidade das políticas de fornecimento que são usadas no planejamento mestre depende das dimensões de armazenamento que são habilitadas como dimensões de cobertura. Para habilitar o planejamento mestre para controlar o reabastecimento e o fornecimento de tipos diferentes de locais (por exemplo, separando o andar de produção para diferentes unidades de produção, ou separando tipos diferentes de materiais e de depósitos de bens acabados), recomendamos que você habilite Local e Depósito como dimensões de cobertura. Outra alternativa é omitir o depósito como uma dimensão de cobertura. Nesse caso, ao usar o gerenciamento de depósito avançado, todos os movimentos em um depósito são controlados pelo trabalho de depósito, enquanto todos os movimentos em depósitos podem ser controlados por kanbans de retirada.

## <a name="supply-policies"></a>Políticas de fornecimento
O planejamento em modo misto controla como um produto é fornecido e, com base no fornecimento, como os requisitos derivados (consumo de itens de uma lista de materiais \[BOM\]) são emitidos. Com base no tipo de ordem, o sistema automaticamente origina material para corresponder aos requisitos.  

As políticas de fornecimento podem ser definidas em nível de produto ou em qualquer granularidade com suporte aos seus requisitos. Você define a granularidade de políticas de fornecimento na página **Configurações padrão da ordem**.  

As políticas de fornecimento podem ser controladas por produto, dimensões de item (configuração, cor e tamanho), local e depósito. Essa configuração é feita na página **Cobertura de item**.  

O tipo de ordem padrão controla a ordem gerada pelo planejamento mestre.  

Independentemente de como a cadeia de fornecedores é modelada, o Supply Chain Management oferece suporte à sua mistura de políticas de fornecimento. Você pode ter ordens de produção originárias de kanbans. Como alternativa, você pode ter uma ordem de lote que exija um produto que é fornecido por transferências ou por kanbans.  

O Supply Chain Management garante que o fluxo de materiais siga o modelo.  

O depósito de separação de material é atribuído de forma dinâmica em tempo de execução, após a definição da política de fornecimento.  

Em geral, kanbans não são criados para datas futuras, pois um kanban tem um ciclo de vida curto. Para manter a visibilidade total na cadeia de fornecimento, apresentamos o novo conceito de planejamento de um “kanban planejado”, que é usado para calcular requisitos derivados e ajuda a garantir que os requisitos sejam originados com base na mesma lógica usada quando o kanban real é criado.  

A mesma lógica está presente em todos os outros tipos de política de fornecimento. Portanto, o planejamento de material de longo prazo se baseia na mesma lógica que você espera executar com as ordens reais após a aprovação de produção e fornecimento.

## <a name="materials-allocation-cross-supply-policy--resource-consumption-on-boms"></a>Política de alocação de material em fornecimentos – consumo de recursos em BOMs
O consumo de recursos é uma funcionalidade importante. O consumo de recursos permite que um depósito escolha materiais a serem selecionados dinamicamente, com base na política de fornecimento (tipo de ordem), e também facilita a manutenção de dados base.  

O consumo de recursos exige que o depósito de onde o material é retirado seja atribuído com base na forma como o produto é fornecido. Em outras palavras, em tempo de execução, o sistema localiza os recursos que devem ser usados na manufatura. Com base nesses recursos, o sistema encontra no depósito de separação.  

Para o trabalho que é independente de uma política de fornecimento, não é necessário alterar as informações no BOM se o fornecimento é alterado. Para alterações ad hoc, o Supply Chain Management garante que os materiais sejam originários do depósito certo.

## <a name="process-manufacturing--the-production-type"></a>Processo de fabricação – O tipo de produção
Para a flexibilidade total no modo misto, recomendamos que você use o tipo BOMs de produção para todos os produtos. Você pode usar ordens de produção, kanbans, ordens de transferência, ordens de compra ou fornecer um produto. No processo de fabricação, você deve usar um tipo de produção **Fórmula**, **Coproduto**, **Subproduto** ou **Item de planejamento**. Kanbans e ordens de produção não podem ser usados para esses tipos de produção.



