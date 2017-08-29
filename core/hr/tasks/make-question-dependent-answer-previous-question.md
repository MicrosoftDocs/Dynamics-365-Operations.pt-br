--- 
title: "Fazer uma pergunta dependente da pergunta da questão anterior"
description: "Perguntas condicionais permitem que você especifique qual será a próxima pergunta a ser apresentada ao entrevistado, com base na resposta dada a pergunta anterior."
author: twheeloc
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 6e532241d719aa013fcbc0c03f88fbda9cc06b99
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Fazer uma pergunta dependente da pergunta da questão anterior

[!include[task guide banner](../../includes/task-guide-banner.md)]

Perguntas condicionais permitem que você especifique qual será a próxima pergunta a ser apresentada ao entrevistado, com base na resposta dada a pergunta anterior. Por exemplo, se você perguntar "Você prefere café ou chá", a próxima pergunta pode ser determinada de maneira lógica de acordo com a escolha do entrevistado. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="find-the-existing-questionnaire"></a>Localize o questionário existente
1. Vá para Questionário > Design > Questionários.
2. Na lista, selecione o questionário WorkFH.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>Adicione todas as perguntas e subperguntas ao questionário
1. Clique em Perguntas.
2. Clique em Novo.
3. No campo Pergunta, selecione a pergunta número 00016.
4. Na lista, localize e selecione o PDV desejado.
5. Na lista, clique no link na linha selecionada.
6. Clique em Salvar.
7. Feche a página.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>Defina a Sequência do Questionário para Condicional e defina a questão apropriada como dependente.
1. Clique em Editar.
2. Expandir a seção Instalação.
3. No campo Ordem das perguntas, selecione 'Condicional'.
4. Clique em Pergunta condicional.
5. Na árvore, selecione 'Perguntas\Explique o motivo da resposta fornecida à questão anterior?'.
6. No campo Pergunta principal, selecione a pergunta 00009.
7. Na lista, clique no link na linha selecionada.
8. No campo Resposta, insira o ID da sequência de resposta da opção de resposta que torna a pergunta dependente dela. Por exemplo, insira 1 para a primeira opção de resposta.
9. Clique em Salvar.
10. Na árvore, selecione 'Perguntas\Eu sou bem pago pelo trabalho que faço.'.
    * Observe que a árvore de pergunta atualizou para mostrar a dependência.  


