--- 
title: "Calcular depreciação de ativo fixo entre entidades legais"
description: "Este procedimento mostra como configurar e executar o processo para várias entidades legais."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: pt-br
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Calcular depreciação de ativo fixo entre entidades legais

[!include [task guide banner](../../includes/task-guide-banner.md)]

A depreciação de ativo fixo pode ser executada nas entidades legais em uma única etapa. Este procedimento mostra como configurar e executar o processo para várias entidades legais. Ele usa a função de contador.  

Este registro usa a empresa de dados de demonstração USMF.


Subtarefa de etapas (16): Configurar diários de execução de depreciação interempresarial. 

1. Primeiro, você deve configurar os diários a serem usados na depreciação interempresarial executada em cada entidade legal. Vá para Ativos fixos > Configuração > Parâmetros de ativos fixos. 
2. Expanda a seção Propostas de ativos fixos. 
3. Crie um registro com o nome do diário a ser usado para cada nível de lançamento na entidade legal. Se os registros não forem lançados na contabilidade, a opção Nenhum nível de lançamento deve ser selecionada com o diário associado. Clique em Adicionar. 
4. No campo Nível de lançamento, insira ou selecione um valor. 
5. No campo Diário, insira ou selecione um valor. 
6. Repita a configuração do diário na página dos parâmetros de Ativos fixos em cada entidade legal. 

Subtarefa: Calcular depreciação

1. Use a página Criar proposta de depreciação para iniciar a execução da depreciação nas entidades legais. Ir para Ativos fixos > Entradas de diário > Criar proposta de depreciação. 
2. No campo Nível de lançamento, insira ou selecione um valor. 
3. O nome de diário usará como padrão os parâmetros de Ativo fixo. É possível alterá-lo aqui para a entidade legal atual. 
4. No campo Para data, insira uma data. 
5. Selecione as entidades legais a serem incluídas na execução da depreciação. Somente as entidades legais com diários configurados para Propostas de ativos fixos na página Parâmetros do ativo fixo serão mostradas na lista. 
6. Quando habilitada, a opção Lançar diários lançará automaticamente os diários de depreciação quando eles forem criados. Quando não selecionada, os diários serão criados, mas não lançados, portanto, você poderá revisar os detalhes antes de lançá-los. Selecione Sim no campo Lançar diários. 
7. Os campos de filtragem incluem todos os ativos fixos, grupos e registros das entidades legais selecionadas para esta execução. 
8. A opção Processamento em lotes está habilitada por padrão. Quando essa opção é habilitada, a criação e a postagem de diário de depreciação é executada em segundo plano. 
9. Clique em Criar diário. 
10. Você deve exibir os diários de depreciação criados nas respectivas entidades legais. Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.

