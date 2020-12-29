---
title: Adicionar uma política de cálculo de quantidade de kanbans a uma regra kanban
description: Este procedimento foca na criação de uma política de cálculo da quantidade kanban e na sua adição à uma regra kanban visando otimizar as quantidades e tamanho kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 039c4aaa355cf2b850ded06913e8e39ee8cac543
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421916"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Adicionar uma política de cálculo de quantidade de kanbans a uma regra kanban

[!include [banner](../../includes/banner.md)]

Este procedimento foca na criação de uma política de cálculo da quantidade kanban e na sua adição à uma regra kanban visando otimizar as quantidades e tamanho kanban. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é destinado ao gerente de fluxo de valor. Esse procedimento é um pré-requisito para a criação do procedimento Calcular sugestões da quantidade kanban. 


## <a name="create-a-kanban-quantity-calculation-policy"></a>Crie uma política de cálculo de quantidade kanban
1. Vá para Controle de produção > Tarefas periódicas > Cálculo da quantidade de kanbans > Políticas de cálculo da quantidade de kanbans.
2. Clique em Novo.
3. No campo Nome, digite um valor.
    * Por exemplo, tipo Speaker2016.  
4. No campo Plano mestre, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione o PDV desejado.
    * Selecione StaticPlan para calcular a demanda.  
6. Na lista, clique no link na linha selecionada.
7. Clique em Salvar.
8. No campo Quantidade kanban mínima, insira '1'.
    * Este é o número adicional de kanbans incluído no cálculo da quantidade de kanbans.  
9. Defina Fator de segurança como '1'.
    * Este é o fator usado para calcular a quantidade adicional de estoque de segurança.  
10. No campo Dias de antecedência, insira '30'.
    * Este é o número de dias antes da data de cálculo da quantidade de kanbans em que a demanda é incluída no cálculo  
11. No campo Dias atrasados, insira '30'.
    * Este é o número de dias à frente da data de cálculo da quantidade de kanbans em que a demanda é incluída no cálculo.  A fórmula usada para o cálculo é mostrada com os valores reais. Por exemplo, quantidade de kanbans = ((demanda diária média x prazo de entrega x 2,00) / quantidade de produtos por unidade de manuseio de material) + 1  
12. Feche a página.

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Adicione a política de cálculo da quantidade kanban à uma regra kanban
1. Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione a regra kanban 000020 para esse procedimento.  
3. Na lista, clique no link na linha selecionada.
4. Ative a expansão da seção Políticas de cálculo da quantidade kanban.
5. Clique em Adicionar.
    * Adicione a política de cálculo da quantidade kanban que você acabou de criar na subtarefa anterior.  
6. Na lista, marque a linha selecionada.
7. No campo Nome, clique no botão suspenso para abrir a pesquisa.
8. Na lista, clique no link na linha selecionada.
    * Selecione a política Speaker2016 que você acabou de criar na subtarefa anterior.  

