---
title: Criar tipos de solicitação e critérios de avaliação para RFQs
description: Este guia mostra como criar um tipo da solicitação e associar esse tipo com um método de avaliação.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf196711799b78d7f4106b6693127d7f356b1d4e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262204"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Criar tipos de solicitação e critérios de avaliação para RFQs

[!include [banner](../../includes/banner.md)]

Este guia mostra como criar um tipo da solicitação e associar esse tipo com um método de avaliação. Ele também mostra como usar o tipo de solicitação em uma solicitação de cotação (RFQ) que então define o padrão do método de avaliação. Essas tarefas são normalmente realizadas por um Gerente de compras. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados. Você precisa ter um método de marcação disponível antes de começar.


## <a name="create-a-solicitation-type"></a>Criar um tipo de solicitação.
1. Vá para Compras > Configuração > Solicitação de cotação > Tipo de solicitação.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Método de avaliação, selecione o método de avaliação que você deseja usar para este tipo de solicitação.
6. Clique em Salvar.
7. Feche a página.

## <a name="use-the-solicitation-type"></a>Use o tipo de solicitação
1. Vá para Aquisição e fornecimento > Solicitações de cotações > Todas as solicitações de cotações.
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