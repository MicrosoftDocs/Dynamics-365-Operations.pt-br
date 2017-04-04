---
title: Planejar o modo misto - combine discreto, processamento, e a fonte magra
description: "Este artigo fornece informações sobre planejamento de modo misto. No planejamento de modo misto, você pode modelar sua cadeia de fornecedor baseada no fluxo de material. Microsoft Dynamics 365 para operações garante que o fluxo material rastrear seus modelos, independentemente diretiva de fonte selecionado (kanban, ordens de produção, ordens de compra, ordens de lote, ou ordens de transferência.)"
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d635421112f6d1e79a47090de3ffc4178b36b132
ms.lasthandoff: 03/31/2017


---

# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>Planejar o modo misto - combine discreto, processamento, e a fonte magra

Este artigo fornece informações sobre planejamento de modo misto. No planejamento de modo misto, você pode modelar sua cadeia de fornecedor baseada no fluxo de material. Microsoft Dynamics 365 para operações garante que o fluxo material rastrear seus modelos, independentemente diretiva de fonte selecionado (kanban, ordens de produção, ordens de compra, ordens de lote, ou ordens de transferência.) 

Você pode selecionar a estratégia geral para fornecer um produto, seja qual for a estrutura de produtos.  

Por exemplo, você pode ter o controle do kanban no assembly, onde o material é originário da área do assembly por ordens de produção, kanbans, transferências, ordens de lote ou qualquer combinação adequado às características da sua cadeia de fornecimento, mas você ainda pode ter visibilidade total em fornecimentos. Este recurso resulta em processos otimizados da cadeia de suprimentos e na visibilidade avançada na cadeia de suprimentos.  

A granularidade das políticas de fornecimento que são usadas no planejamento mestre depende das dimensões de armazenamento que são habilitadas como dimensões de cobertura. Para habilitar o planejamento mestre para controlar o reabastecimento e o fornecimento de tipos diferentes de locais (por exemplo, separando o andar de produção para diferentes unidades de produção, ou separando tipos diferentes de materiais e de depósitos de bens acabados), recomendamos que você habilite Local e Depósito como dimensões de cobertura. Outra alternativa é omitir o depósito como uma dimensão de cobertura. Nesse caso, ao usar o gerenciamento de depósito avançado, todos os movimentos em um depósito são controlados pelo trabalho de depósito, enquanto todos os movimentos em depósitos podem ser controlados por kanbans de retirada.

## <a name="supply-policies"></a>Políticas de fornecimento
Dynamics 365 para o modo misto operações que planeja controla como um produto ser fornecidos e, na base de imposto, como requisitos derivados (consumo de itens de uma lista de materiais BOM \[\]) são emitidos. Com base no tipo de ordem, o sistema automaticamente origina material para corresponder aos requisitos.  

As políticas de fornecimento podem ser definidas em nível de produto ou em qualquer granularidade com suporte aos seus requisitos. Você define a granularidade de políticas de fornecimento na página **Configurações padrão da ordem**.  

As políticas de fornecimento podem ser controladas por produto, dimensões de item (configuração, cor e tamanho), local e depósito. Essa configuração é feita na página **Cobertura de item**.  

O tipo de ordem padrão controla a ordem gerada pelo planejamento mestre.  

Independentemente como a cadeia de fornecimento é modelada, o dynamics 365 para operações suporta sua combinação de diretivas de fornecimento. Você pode ter ordens de produção originárias de kanbans. Como alternativa, você pode ter uma ordem de lote que exija um produto que é fornecido por transferências ou por kanbans.  

O dynamics 365 para operações garante que o fluxo material também o modelo.  

O depósito de separação de material é atribuído de forma dinâmica em tempo de execução, após a definição da política de fornecimento.  

Em geral, kanbans não são criados para datas futuras, pois um kanban tem um ciclo de vida curto. Para manter a visibilidade total na cadeia de fornecimento, apresentamos o novo conceito de planejamento de um “kanban planejado”, que é usado para calcular requisitos derivados e ajuda a garantir que os requisitos sejam originados com base na mesma lógica usada quando o kanban real é criado.  

A mesma lógica está presente em todos outros tipos de política de fornecimento. Portanto, o planejamento de material de longo prazo se baseia na mesma lógica que você espera executar com as ordens reais após a aprovação de produção e fornecimento.

## <a name="materials-allocation-crosssupply-policy--resource-consumption-on-boms"></a>Sobre materiais de alocação crosssupply diretiva – consumo em As BOMs de recurso
O consumo do recurso é uma funcionalidade importante. O consumo de recursos permite que um depósito escolha materiais a serem selecionados dinamicamente, com base na política de fornecimento (tipo de ordem), e também facilita a manutenção de dados base.  

O consumo de recursos exige que o depósito de onde o material é retirado seja atribuído com base na forma como o produto é fornecido. Em outras palavras, em tempo de execução, o sistema localiza os recursos que devem ser usados na manufatura. Com base nesses recursos, o sistema encontra no depósito de separação.  

Para o trabalho que é independente de uma política de fornecimento, não é necessário alterar as informações no BOM se o fornecimento é alterado. Para alterações ad hoc, o dynamics 365 para operações garantirá que os materiais são originários de depósito direito.

## <a name="process-manufacturing--the-production-type"></a>Processo de fabricação – O tipo de produção
Para a flexibilidade total no modo misto, recomendamos que você usa o tipo BOMs de produção para todos os produtos. Você pode usar ordens de produção, kanban, ordens de transferência, ordens de compra ou fornecer um produto. No processo de fabricação, você deve usar um tipo de produção **Fórmula**, **Coproduto**, **Subproduto** ou **Item de planejamento**. Kanbans e ordens de produção não podem ser usados para esses tipos de produção.


