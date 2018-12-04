--- 
title: "Definir contagem cíclica "
description: "A contagem cíclica é um processo de depósito que você pode usar para auditar itens de estoque disponíveis."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f9cdb0a7de0199363279c53e817c98085b31fe6b
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="define-cycle-counting"></a>Definir contagem cíclica  

[!include [task guide banner](../../includes/task-guide-banner.md)]

A contagem cíclica é um processo de depósito que você pode usar para auditar itens de estoque disponíveis. Essa gravação de tarefa mostra como: definir a prioridade de trabalho de contagem padrão; habilitar um item de menu de dispositivo móvel para processar operações de separação e contagem; habilitar um gatilho de limite de contagem quando um local ficar vazio e habilitar um plano de contagem cíclica de um item específico em um depósito específico. Geralmente, essas tarefas são realizadas por um gerente de depósito. Você pode ver todo esse procedimento na empresa de dados de demonstração USMF ou em seus próprios dados.


## <a name="set-the-priority-of-counting-work"></a>Definir a prioridade do trabalho de contagem
1. Vá para Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito.
2. Clique na guia Contagem cíclica.
3. No campo Prioridade de trabalho de contagem cíclica padrão, insira um número.
    * Esta etapa altera a prioridade de trabalho da contagem cíclica comparada a outros tipos de trabalho no depósito. Inserindo um número menor que o número de outros tipos de trabalho você aumenta a prioridade do trabalho de contagem cíclica.  
4. Clique em Salvar.
5. Feche a página.

## <a name="enable-the-mobile-device"></a>Habilitar o dispositivo móvel
1. Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu de dispositivo móvel.
2. Clique em Novo.
3. No campo Item de menu, digite um valor.
4. No campo Título, digite um valor.
5. No campo Modo, selecione 'Trabalho'.
6. Defina a opção Usar trabalho existente como Sim.
    * Ao definir esta opção como Sim, o sistema procurará um trabalho existente quando o item de menu de dispositivo móvel for usado.  
7. No campo Direcionado por, selecione 'Direcionada pelo sistema'.
    * Quando "Sistema direcionado" for selecionado, o trabalhador de depósito será direcionado para abrir os trabalhos que estão em classes de trabalho definidas. (Criaremos essas classes de trabalho em seguida.)  
8. Expandir ou recolher a seção Classes de trabalho.
    * Em seguida, vamos criar duas classes de trabalho que serão usadas com esse item de menu de dispositivo móvel. Quando o item de menu for usado, essas classes de trabalho serão consultadas, o trabalho que tiver a prioridade maior será mostrado ao usuário.  
9. Clique em Novo.
10. No campo ID de classe de trabalho, selecione um valor.
11. Clique em Novo.
12. No campo ID de classe de trabalho, selecione um valor.
13. Clique em Salvar.
14. Feche a página.
15. Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Menu de dispositivo móvel.
16. Na lista, localize e selecione o PDV desejado.
17. Na árvore, selecione o item de menu que você acabou de criar.
18. Clique em Editar.
19. Clique na seta para adicionar o item de menu ao menu.
20. Clique em Salvar.

## <a name="create-a-counting-threshold"></a>Criar um limite de contagem
1. Vá para Gerenciamento de depósito > Configuração > Contagem cíclica > Limites de contagem cíclica.
2. Clique em Novo.
3. No campo ID do limite de contagem cíclica, digite um valor.
4. Defina a opção Processar contagem cíclica imediatamente como Sim.
5. No campo Descrição, digite um valor.
6. Clique em Salvar.
7. Clique em Selecionar localizações.
8. Na lista, marque a linha selecionada.
9. No campo Critérios, selecione um valor.
10. Clique em OK.
11. Feche a página.

## <a name="create-a-cycle-count-plan"></a>Criar um plano de contagem cíclica
1. Vá para Gerenciamento de depósito > Configuração > Contagem cíclica > Planos de contagem cíclica.
2. Clique em Novo.
3. No campo ID do plano de contagem cíclica, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Número máximo de contagens cíclicas, insira um número.
6. Clique em Salvar.
7. Clique em Selecionar localizações.
8. Na lista, marque a linha selecionada.
9. No campo Critérios, selecione um valor.
10. Clique em OK.
11. No campo Dias entre a contagem cíclica, insira um número.
    * Por exemplo, se o campo Dias entre a contagem cíclica for 5, o trabalho de contagem cíclica será criado a cada cinco dias. No entanto, se o trabalho de contagem cíclica for processado no dia três, o próximo trabalho de contagem cíclica será criado cinco dias após a última contagem cíclica ter sido processada, no dia oito.  
12. Clique em Salvar.
13. Clique em Novo.
14. No campo de número de sequência, insira um número.
    * A ordem de classificação é do número menor para o número maior. O valor deve ser maior que 0 (zero).  
15. Na lista, marque a linha selecionada.
16. No campo Descrição, digite um valor.
17. Clique em Salvar.
18. Clique em Definir consulta de produto.
19. Na lista, marque a linha selecionada.
20. No campo Critérios, insira ou selecione um valor.
21. Clique em OK.
22. Feche a página.


