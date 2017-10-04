--- 
title: "Criar tipos de solicitação e critérios de avaliação para RFQs"
description: "Este guia mostra como criar um tipo da solicitação e associar esse tipo com um método de avaliação."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 04f8cb1a6375be9371bca2af7e4044392ce7322b
ms.openlocfilehash: c77173c5dd9f0513de5d794f7453715ceff550da
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Criar tipos de solicitação e critérios de avaliação para RFQs

[!include[task guide banner](../../includes/task-guide-banner.md)]

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
4. Clique em OK.
5. Clique em Critérios de pontuação.
    * Os critérios de avaliação que são mostrados são esses do método de avaliação que você associou com o tipo da solicitação. Você pode escolher adicionar ou suprimir critérios nesta página. É igualmente possível adicionar critérios novos copiando os de outros métodos de avaliação.  
6. Clique em Copiar critérios.
7. No campo Método de avaliação, insira ou selecione um valor.
8. Clique em OK.
9. Feche a página.

