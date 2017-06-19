---
title: "Use fluxos de trabalho para gerenciar informações de funcionário"
description: "Este tópico explica como você pode usar o recurso de fluxo de trabalho para recursos humanos para gerenciar informações de funcionários. Por exemplo, você pode associar um fluxo de trabalho a uma posição e configurar um fluxo de trabalho de aprovação que é iniciado quando os funcionários alteram seu registro."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Core
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 806860e5df9252c074e04e9e1670f4215fd94ca2
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Use fluxos de trabalho para gerenciar informações de funcionário

[!include[banner](includes/banner.md)]


Este tópico explica como você pode usar o recurso de fluxo de trabalho para recursos humanos para gerenciar informações de funcionários. Por exemplo, você pode associar um fluxo de trabalho a uma posição e configurar um fluxo de trabalho de aprovação que é iniciado quando os funcionários alteram seu registro.

A capacidade de fluxo de trabalho para Recursos Humanos fornece vários fluxos de trabalho para gerenciar atividades de recursos humanos. Além disso, várias opções estão disponíveis para que você possa modificar fluxos de trabalho específicos e associá-los a uma hierarquia de relatórios. Fluxos de trabalho estão disponíveis para ajudar a gerenciar alterações a vários tipos padrão de informações de funcionários. Você pode associar um fluxo de trabalho a uma posição. Em seguida, se os funcionários alterarem o registro do funcionário, será iniciado um fluxo de trabalho que requer aprovação antes que as novas informações sejam salvas. Os fluxos de trabalho são predefinidos para os seguintes tipos de informações para ajudá-lo a gerenciar com eficiência as alterações e manter os dados dos funcionários precisos:

-   Números de identificação
-   Cursos
-   Formação educacional
-   Imagem
-   Itens emprestados
-   Experiência profissional
-   Experiência em projetos
-   Habilidades
-   Posições de confiança
-   Ações de recursos humanos
-   Registro do curso

Quando os funcionários são contratados, transferidos ou encerrados, o fluxo de trabalho pode incluir um processo de revisão. Desta forma, um documento pode ser revisto ou os termos de uma ação podem ser definidos como parte do fluxo de trabalho. Quando o processo de revisão é concluído, o documento ou ação é concluído e o fluxo de trabalho passa para uma etapa de aprovação final.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associar um fluxo de trabalho a uma hierarquia de posições
Você pode associar um fluxo de trabalho com qualquer hierarquia que você configurar. Por exemplo, se uma posição estiver associada a uma hierarquia de relatórios de matriz, você pode configurar um fluxo de trabalho que encaminha despesas para um projeto específico, para a liderança do projeto em vez do gerente do funcionário que está associado a essa posição. Para criar um novo fluxo de trabalho ou modificar um fluxo de trabalho, na página **Fluxo de trabalho de recursos humanos**, clique em **Novo**. Selecione um fluxo de trabalho na lista para iniciar o designer de fluxo de trabalho. Você pode usar o designer para criar um novo fluxo de trabalho ou alterar as etapas em um fluxo de trabalho existente. Quando você altera um fluxo de trabalho existente, suas alterações são salvas como uma nova versão. Portanto, você pode sempre voltar a uma versão anterior, se for necessário.

## <a name="configure-a-human-resources-workflow"></a>Configurar um fluxo de trabalho de recursos humanos
Para configurar um fluxo de trabalho básico que é iniciado quando os funcionários solicitam alterações à sua identificação pessoal, siga estas etapas.

1.  Na página **Fluxos de trabalho de recursos humanos**, clique em **Novo**.
2.  Na lista de fluxos de trabalho disponíveis, selecione **Números de identificação**.
3.  Clique em **Executar** para o designer de fluxo de trabalho, e insira o nome de usuário e senha quando for solicitado.
4.  Arraste o elemento **Aprovar número de identificação** da lista de elementos de fluxo de trabalho para a tela do designer.
5.  Conecte o elemento de aprovação com **Início** e **Término**.
6.  Clique duas vezes em **Aprovar elemento** e, em seguida, clique em **Propriedades**.
7.  Siga essas etapas para adicionar instruções de item de trabalho:
    1.  Selecione **Atribuição** e, em seguida, selecione **Hierarquia** no tipo de atribuição.
    2.  Na seleção de **Hierarquia**, selecione **Hierarquia configurável**.
    3.  Adicione uma condição de parada, e feche a página.

8.  Complete todas as instruções adicionais (não devem existir avisos adicionais).
9.  Clique em **Salvar e fechar**. Ative o novo fluxo de trabalho quando a caixa de diálogo abrir e selecione **Ativar**.
10. Vá para **Recursos humanos** &gt; **Posições** &gt; **Tipos de hierarquia de posição**.
11. Selecione **Matriz**.
12. Adicione o fluxo de trabalho **Número de identificação do trabalhador** à lista.





