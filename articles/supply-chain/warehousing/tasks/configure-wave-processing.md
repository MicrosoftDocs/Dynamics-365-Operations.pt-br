---
title: Configurar processamento da onda
description: Este guia descreve como configurar os critérios que determinam que trabalho será gerado para um depósito quando uma onda for processada, e se as ondas são processadas manual ou automaticamente.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 399146d35388a0151abb23e57bc36ec0173be928
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571877"
---
# <a name="configure-wave-processing"></a>Configurar processamento da onda

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia descreve como configurar os critérios que determinam que trabalho será gerado para um depósito quando uma onda for processada, e se as ondas são processadas manual ou automaticamente. Você especifica os critérios configurando modelos e consultas de onda que correspondam a uma onda com linhas liberadas em ordens de venda, ordens de produção ou ordens kanban. O processamento da onda é usado nos depósitos usando a funcionalidade no módulo de gerenciamento de depósito, e não nas que usam a funcionalidade no módulo de gerenciamento de estoque. Você pode executar este procedimento na empresa USMF de dados de demonstração.

1. Vá para Gerenciamento de depósito > Configuração > Ondas > Modelos de ondas.
2. Clique em Novo.
3. No campo Nome de modelo de onda, digite um valor.
    * Ao configurar um modelo de onda, você especifica a sequência na qual os modelos serão correspondidos às linhas liberadas em ordens de venda, ordens de produção ou kanbans. Quando uma linha é liberada para o depósito ou para a produção, use o primeiro modelo da onda que atende aos critérios. É recomendável que você coloque modelos com os critérios mais específicos na parte superior da lista. Quanto mais amplo os critérios, mais provável será que uma linha atenda a eles, o que poderia levar a linhas sendo atribuídas à onda incorreta.  
4. No campo Descrição do modelo da onda, digite um valor.
5. No campo Local, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar site 2.  
6. No campo Depósito, insira ou selecione um valor.
    * Se você estiver usando o USMF, você pode selecionar o depósito 24.  
7. Defina o campo Criação da onda de automatização como Sim.
    * Selecione esta opção para criar automaticamente uma onda quando uma ordem de venda, uma ordem de produção ou um kanban forem liberados para o depósito.  
8. Defina a Onda de processo para liberar a opção de depósito como Sim. 
    * Selecione esta caixa de seleção para processar automaticamente a onda e criar trabalho quando uma linha for liberada para o depósito.  
9. Defina a opção Liberação da onda de automatização como Sim. 
    * Marque esta opção para liberar a onda automaticamente. O trabalho de separação é criado e disponibilizado em dispositivos móveis.  
10. Defina a opção Atribuir para abrir ondas como Sim. 
    * As linhas são atribuídas a ondas com base no filtro da consulta para o modelo de onda.  
11. Defina a Onda de processo automaticamente na opção de limite como Sim. 
    * Selecione esta opção para processar automaticamente a onda quando os valores atingirem os limites de peso, de remessa e de linhas especificados no grupo de campos Limites de onda. Essa opção está disponível apenas se a Remessa estiver selecionada no campo de tipo de Modelo da onda.  
12. Defina a opção Liberação do trabalho de reabastecimento de automatização como Sim. 
    * Selecione esta opção para criar o trabalho de reabastecimento baseado em demanda e libere-o automaticamente. Você deve adicionar o método de onda de reabastecimento ao modelo de onda e criar um modelo de reabastecimento do tipo Demanda da onda.  
13. Expandir a seção Métodos.
    * Os métodos do modelo da onda permitem que você controle a sequência de atividades que cada onda terá quando tiver processado. Por exemplo, você pode ter um método para reabastecimento da onda. Quando você adicionar um método, ele será automaticamente listado na localização apropriada na sequência de etapas. Se você definiu a opção de versão de trabalho de reabastecimento de automatização para Sim, você precisará adicionar aqui o método de reabastecimento.  
    * Os atributos da onda atuam como filtros, para restringir o tipo de itens que podem usar a onda. Por exemplo, você pode especificar um grupo de itens.  
14. Clique em Salvar.
15. Feche a página.
16. Vá para Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito.
17. Expanda a seção Processamento da onda.
18. No campo Processamento da onda no grupo do lote, insira ou selecione um valor.
19. Defina as Ondas de processo na opção de lote como Sim.
20. No campo Esperar por bloqueio (ms), insira um número.
    * Insira o tempo, em milissegundos, que uma etapa de alocação aguardará um recurso do sistema que está bloqueado por outra etapa de alocação. Quando esse tempo é excedido, a onda não é processada e uma mensagem de erro é exibida.  
21. Clique em Salvar.
22. Feche a página.
23. Vá para Controle de produção > Configuração > Parâmetros de controle de produção.
24. No campo Liberar para depósito, selecione uma opção.
    * Para ordens de venda e ordens de kanban, o estoque será reservado antes de a ordem ser liberada para o depósito. Caso contrário, os itens ou as linhas de alocação não poderão ser processadas em uma onda. Para ordens de produção, você também terá a opção de seleção para permitir reserva parcial. Por exemplo, isso será útil se você tiver o material necessário para iniciar uma produção, e puder aguardar até que o material adicional seja disponibilizado para finalizar o processo. Se você selecionar esta opção, repita manualmente a liberação para o processo de armazém quando o material adicional for disponibilizado.  
25. Feche a página.

