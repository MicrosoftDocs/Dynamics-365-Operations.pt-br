---
title: Fazer uma pergunta dependente da pergunta da questão anterior
description: Perguntas condicionais permitem que você especifique qual será a próxima pergunta a ser apresentada ao entrevistado, com base na resposta dada a pergunta anterior.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67dac872d6dc3a5046f5d554b1f185aa6607d193
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5114995"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Fazer uma pergunta dependente da pergunta da questão anterior



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



[!INCLUDE[footer-include](../includes/footer-banner.md)]