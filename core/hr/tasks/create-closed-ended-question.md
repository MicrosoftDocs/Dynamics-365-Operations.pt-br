--- 
title: Criar uma pergunta fechada
description: "As perguntas fechadas permitem que você forneça opções para que o entrevistado escolha."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 71b2a2da0b705b84f79adcff25672855e7b5253f
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-closed-ended-question"></a>Criar uma pergunta fechada

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


