---
title: Adicionar uma atividade existente a uma versão de fluxo de produção
description: Ao criar novas versões de fluxos de produção, você pode escolher adicionar atividades criadas para as versões anteriores à nova versão.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f36ace43c12563805e17c0dcc667f12c1befa74829c92a941999ec5ece819306
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773192"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>Adicionar uma atividade existente a uma versão de fluxo de produção

[!include [banner](../../includes/banner.md)]

Ao criar novas versões de fluxos de produção, você pode escolher adicionar atividades criadas para as versões anteriores à nova versão. Este procedimento mostra como uma nova versão é criada para um fluxo de produção existente, sem copiar as atividades. Na próxima etapa, uma atividade existente será adicionada à nova versão. 

Esta tarefa requer o fluxo de produção com a versão e as atividades já criadas.


## <a name="create-a-new-production-flow-version"></a>Criar uma nova versão de fluxo de produção
1. Acesse Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Clique em Editar.
5. Na lista, marque a linha selecionada.
6. No campo Data de vencimento, insira uma data e hora.
    * Observe que antes de você criar uma nova versão do fluxo de produção, certifique-se de verificar a data e hora de vencimento da versão ativa. A nova versão será criada com uma data de início efetiva, conectada à data de vencimento da versão selecionada.  
7. Clique em Adicionar.
8. Selecione Não no campo Copiar da versão.
    * Selecione Não para iniciar com uma versão vazia se a maioria das atividades da versão copiada for substituída por novas atividades. Adicione manualmente as atividades inalteradas à função Adicionar existente no formulário da atividade.  
9. Selecione Não no campo Duplicar regras kanban.
    * Quando as atividades não são copiadas na nova versão, não é possível copiar as regras kanban no momento da criação da nova versão.   Em vez disso, você usará a função Criar kanban de substituição posteriormente no formulário da regra kanban para substituir as regras kanban da versão antiga do fluxo de produção com regras kanban usando as atividades da nova versão.  
10. Clique em OK.
11. Na lista, localize e selecione o PDV desejado.

## <a name="add-an-existing-activity"></a>Adicionar uma atividade existente
1. Clique em Atividades.
2. Clique em Adicionar existente para abrir a caixa de diálogo suspensa.
    * Localizar e selecionar uma atividade existente que será adicionada à nova versão do fluxo de produção  Observe que a lista mostra todas as atividades criadas para este fluxo de produção para todas as versões anteriores do fluxo.  
3. No campo Atividade, insira ou selecione um valor.
4. Clique em OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]