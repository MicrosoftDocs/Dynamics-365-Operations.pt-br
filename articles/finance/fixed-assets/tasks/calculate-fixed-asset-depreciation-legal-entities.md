---
title: Calcular depreciação de ativo fixo entre entidades legais
description: A depreciação de ativo fixo pode ser executada nas entidades legais em uma única etapa.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 074a1b80584050302920a95c20fb547523a4866c
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142906"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Calcular depreciação de ativo fixo entre entidades legais

[!include [banner](../../includes/banner.md)]

A depreciação de ativo fixo pode ser executada nas entidades legais em uma única etapa. Este procedimento mostra como configurar e executar o processo para várias entidades legais. Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.


## <a name="set-up-cross-company-depreciation-run-journals"></a>Configurar diários de execução de depreciação interempresariais
1. Vá para Ativos fixos > Configuração > Parâmetros de ativos fixos.
2. Expanda a seção Propostas de ativos fixos.
3. Clique em Adicionar.
4. No campo Nível de lançamento, insira ou selecione um valor.
5. No campo Diário, insira ou selecione um valor.
    * Repita a configuração do diário na página dos parâmetros de Ativos fixos em cada entidade legal.  

## <a name="depreciation-run"></a>Execução de depreciação
1. Ir para Ativos fixos > Entradas de diário > Criar proposta de depreciação.
2. No campo Nível de lançamento, insira ou selecione um valor.
    * O nome de diário usará como padrão os parâmetros de Ativo fixo. É possível alterá-lo aqui para a entidade legal atual.  
3. No campo Para data, insira uma data.
    * Selecione as entidades legais a serem incluídas na execução da depreciação.  
    * Somente as entidades legais com diários configurados para Propostas de ativos fixos na página Parâmetros do ativo fixo serão mostradas na lista.  
4. Selecione Sim no campo Lançar diários.
    * Os campos de filtragem incluem todos os ativos fixos, grupos e registros das entidades legais selecionadas para esta execução.  
    * A opção Processamento em lotes está habilitada por padrão. Quando essa opção é habilitada, a criação e a postagem de diário de depreciação é executada em segundo plano.  
5. Clique em Criar diário.
6. Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.

