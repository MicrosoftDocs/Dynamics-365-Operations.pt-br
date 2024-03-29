---
title: Criar tipos de solicitação e critérios de avaliação para RFQs
description: Este guia mostra como criar um tipo da solicitação e associar esse tipo com um método de avaliação.
author: GalynaFedorova
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69d62941629d0b1321a714df5ce6d81c6f94b9f5
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678649"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Criar tipos de solicitação e critérios de avaliação para RFQs

[!include [banner](../../includes/banner.md)]

Este guia mostra como criar um tipo da solicitação e associar esse tipo com um método de avaliação. Ele também mostra como usar o tipo de solicitação em uma solicitação de cotação (RFQ) que então define o padrão do método de avaliação. Essas tarefas são normalmente realizadas por um Gerente de compras. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados. Você precisa ter um método de marcação disponível antes de começar.


## <a name="create-a-solicitation-type"></a>Criar um tipo de solicitação.
1. Acesse Compras > Configuração > Solicitação de cotação > Tipo de solicitação.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Método de avaliação, selecione o método de avaliação que você deseja usar para este tipo de solicitação.
6. Clique em Salvar.
7. Feche a página.

## <a name="use-the-solicitation-type"></a>Use o tipo de solicitação
1. Acesse Aquisição e fornecimento > Solicitações de cotações > Todas as solicitações de cotações.
2. Clique em Novo.
3. No campo Tipo de solicitação, selecione o tipo de solicitação que você acabou de criar. 
    *   
4. Clique em OK.
5. Clique em Critérios de pontuação.
    * Os critérios de avaliação que são mostrados são esses do método de avaliação que você associou com o tipo da solicitação. Você pode escolher adicionar ou suprimir critérios nesta página. É igualmente possível adicionar critérios novos copiando os de outros métodos de avaliação.  
6. Clique em Copiar critérios.
7. No campo Método de avaliação, insira ou selecione um valor.
8. Clique em OK.
9. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]