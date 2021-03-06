---
title: Criar uma pergunta fechada
description: As perguntas fechadas permitem que você forneça opções para que o entrevistado escolha.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0316661d8be04cc5912e88bc50b3a1c7a73bbcb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056675"
---
# <a name="create-a-closed-ended-question"></a>Criar uma pergunta fechada

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



As perguntas fechadas permitem que você forneça opções para que o entrevistado escolha. Primeiro, você precisa criar o Grupo de resposta com as respostas, então criar a pergunta que irá utilizar o grupo de resposta. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-an-answer-group"></a>Crie um grupo de reposta
1. Vá para Questionário > Design > Grupos de respostas.
2. Clique em Novo.
3. No campo Grupo de resposta, digite um valor.
4. No campo Descrição, digite um valor.
    * Use a funcionalidade Randomizar para colocar as respostas numa ordem aleatória diferente toda vez que o grupo de repostas for usado para uma questão.  
5. Clique em Resposta.
6. Clique em Novo.
    * Número de sequência controla a ordem em que as respostas são exibidas, a menos que Randomizar seja selecionada para o Grupo de respostas.  
    * Pontos podem ser concedidos pelas respostas para uso na pontuação do questionário.  
7. No campo Pontos, insira um número.
    * A resposta correta pode ser marcada para indicar que a resposta selecionada é a correta. Isso pode ser usado na pontuação do questionário.  
8. No campo Resposta, digite um valor.
    * Continue a criar opções de seleção de resposta para o grupo de respostas.  
9. Clique em Novo.
10. No campo Pontos, insira um número.
11. No campo Resposta, digite um valor.
12. Clique em Novo.
13. No campo Pontos, insira um número.
14. No campo Resposta, digite um valor.
15. Clique em Novo.
16. No campo Pontos, insira um número.
17. No campo Resposta, digite um valor.
18. Clique em Novo.
19. No campo Pontos, insira um número.
20. No campo Resposta, digite um valor.
21. Feche a página.
22. Feche a página.

## <a name="create-the-question"></a>Crie a pergunta
1. Vá para Questionário > Design > Perguntas.
2. Clique em Novo.
3. Use o campo Tipo para agrupar perguntas relacionadas.
    * Você pode usar os tipos de entrada de Caixa de seleção, Botão Alternativo, ou Caixa de combinação para perguntas fechadas.  
4. No campo Tipo de entrada, selecione uma opção.
5. No campo Responder grupo, insira ou selecione um valor.
6. No campo Texto, digite um valor.



[!INCLUDE[footer-include](../includes/footer-banner.md)]