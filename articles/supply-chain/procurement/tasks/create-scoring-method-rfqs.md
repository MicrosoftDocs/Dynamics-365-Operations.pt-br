---
title: Criar um método de avaliação para RFQs
description: Este procedimento mostra como criar um método de avaliação.
author: GalynaFedorova
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a6b715caa57d8ceb2e91af88538fa735568a997
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671049"
---
# <a name="create-a-scoring-method-for-rfqs"></a>Criar um método de avaliação para RFQs

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um método de avaliação. Um método de avaliação é um grupo de critérios que pode ser usado para comparar as ofertas que são enviadas em resposta a um pedido para a cotação (RFQ). Por exemplo, talvez você queira classificar o desempenho passado de um fornecedor, ou avaliar se a empresa é ambientalmente correta ou uma boa parceira, ou você pode querer comparar lances com base em preços. Se um método de pontuação estiver associado ao tipo de solicitação, esse será o método de pontuação padrão para a RFQs que você estiver criando. Essas tarefas são normalmente realizadas por um Gerente de compras. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.

1. Acesse Compras > Configuração > Solicitação de cotação > Método de pontuação.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Salvar.
6. Clique em Novo.
7. No campo Nome, digite um valor.
8. No campo Descrição, digite um valor.
    * Esta descrição é exibida junto com o nome do método de avaliação quando um método de avaliação é selecionado para um RFQ.  
9. No campo Variar de, insira um número.
    * A variação limita o que o profissional de obtenção pode inserir como avaliação. Quando há um múltiplo que marca critérios em um RFQ, as contagens que foram incorporadas são adicionadas entre si e a soma feita está disponível para permitir que as ofertas sejam comparadas.  
10. No campo Variar a, insira um número.
11. Clique em Novo.
12. No campo Nome, digite um valor.
13. No campo Descrição, digite um valor.
14. No campo Variar de, insira um número.
15. No campo Variar a, insira um número.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]