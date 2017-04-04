---
title: "Use fluxos de trabalho para gerenciar informações de funcionário"
description: "Este tópico explica como você pode usar o recurso de fluxo de trabalho para os recursos humanos gerenciar informações de funcionário. Por exemplo, você pode associar um fluxo de trabalho a uma posição e configurar um fluxo de trabalho de aprovação que é iniciado quando funcionários modificar o registro."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: f286436aa4833babaeb3de875ee393d18e5f8eea
ms.lasthandoff: 03/31/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Use fluxos de trabalho para gerenciar informações de funcionário

Este tópico explica como você pode usar o recurso de fluxo de trabalho para os recursos humanos gerenciar informações de funcionário. Por exemplo, você pode associar um fluxo de trabalho a uma posição e configurar um fluxo de trabalho de aprovação que é iniciado quando funcionários modificar o registro.

O recurso de fluxo de trabalho para recursos humanos fornece fluxos de trabalho para gerenciar atividades vários recursos humanos. Além disso, as opções disponíveis de muitas para que você possa alterar fluxos de trabalho específicos e os associe com uma hierarquia organizacional. Os fluxos de trabalho estão disponíveis para ajudar a gerenciar as alterações a diversos tipos padrão de informações de funcionários. Você pode associar um fluxo de trabalho a uma posição. Em seguida, se os funcionários cujas o registro de funcionário, um fluxo de trabalho for iniciada que exijam aprovação antes novas informações será salva. Os fluxos de trabalho são predefinidos para os tipos de informações para ajudá-lo eficientemente a gerenciar alterações e manter dados precisos de seus funcionários:

-   Números de identificação
-   Cursos
-   Formação educacional
-   Imagem
-   Itens emprestados
-   Experiência profissional
-   Experiência em projetos
-   Habilidades
-   Posições de confiança
-   Ações recursos humanos
-   Registro em curso

Quando os funcionários são transferidos, contratadas ou dispensadas, fluxo de trabalho poderá incluir um processo de revisão. Assim, um documento pode ser revisado ou condições de uma ação podem ser definidos como parte do fluxo de trabalho. Quando o processo de revisão é concluída, o documento ou a ação é concluído, e o fluxo de trabalho a uma etapa de aprovação final.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associar um fluxo de trabalho com uma hierarquia de posição
Você pode associar um fluxo de trabalho com qualquer hierarquia que você definir. Por exemplo, se uma posição foi associada a uma hierarquia organizacional de matriz, você pode configurar um fluxo de trabalho que roteasse despesas para um projeto específico à perspectiva de projeto em vez do gerente do funcionário associado à posição. Para criar um novo fluxo de trabalho ou modificar um fluxo de trabalho existente, ** fluxo dos recursos humanos ** na página, clique em novo. ** ** Selecione um fluxo de trabalho na lista para o designer de fluxo de trabalho. Você pode usar o designer para criar um novo fluxo de trabalho ou modificar as etapas de um fluxo de trabalho existente. Quando você altera um fluxo de trabalho existente, as alterações são salvas como uma nova versão. Portanto, você sempre pode voltar a uma versão anterior se precisar.

## <a name="configure-a-human-resources-workflow"></a>Configurar um fluxo de trabalho de recursos humanos
Para configurar um fluxo de trabalho básica que é iniciado quando a solicitação do funcionário mudar a identificação pessoal, rastrear essas etapas.

1.  ** Fluxos dos recursos humanos ** na página, clique em novo. ** **
2.  Na lista de fluxos de trabalho disponíveis, marque ** ID numbers **.
3.  Clique ** execução ** para o designer de fluxo de trabalho, e insira com o nome de usuário e senha quando for solicitado.
4.  Arrastar ** aprove o número de identificação ** o elemento da lista de elementos de fluxo de trabalho a lona designer.
5.  Conectar o elemento de aprovação ** Início e término ** ** **.
6.  Clicar duas vezes ** ** elemento de aprovação, clique com o botão direito em, selecione propriedades ** **.
7.  Rastrear essas etapas para adicionar instruções do item de trabalho:
    1.  Selecione ** atribuição **, e marque ** hierarquia ** em tipo atribuição.
    2.  ** Em hierarquia ** a seleção, selecione ** hierarquia ** configurável.
    3.  Adicionar uma condição de parada, e feche a página.

8.  Conclua todas as instruções adicionais (nenhum aviso adicional deve existir).
9.  Clique em **Salvar e fechar**. Ativar o novo fluxo de trabalho quando a caixa de diálogo abrir, e selecione ** faça ** ativo.
10. Ir ** recursos humanos ** &gt; ** posições ** &gt; ** tipos hierárquica ** de posição.
11. Selecione ** ** matriz.
12. ** Adicionar número de identificação de trabalho ** o fluxo de trabalho a lista.



