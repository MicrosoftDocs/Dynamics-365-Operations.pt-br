---
title: Exemplo de Configuração de processamento de ciclo
description: Este tópico fornece um exemplo como configurar os critérios que determinam que trabalho será gerado para um depósito quando um ciclo for processado, e se os ciclos são processados manual ou automaticamente.
author: Mirzaab
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39c3fecf9250ee89c22003d5dff4ea662c3042e3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572976"
---
# <a name="configure-wave-processing-example"></a>Exemplo de Configuração de processamento de ciclo

[!include [banner](../../includes/banner.md)]

Este tópico fornece um exemplo como configurar os critérios que determinam que trabalho será gerado para um depósito quando um ciclo for processado, e se os ciclos são processados manual ou automaticamente. Você especifica os critérios configurando modelos e consultas de onda que correspondam a uma onda com linhas liberadas em ordens de venda, ordens de produção ou ordens kanban.

## <a name="enable-sample-data"></a>Habilitar dados de exemplo

Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os dados de demonstração padrão estejam instalados. Você também deve selecionar a entidade legal **USMF** antes de começar.

## <a name="example-scenario-configure-wave-processing"></a>Cenário de exemplo: Configurar processamento de ciclo

Este cenário de exemplo percorre várias das diversas configurações que afetam como os ciclos são criados, preenchidos, processados e liberados.

1. Acesse **Painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Ondas > Modelos de onda**.
1. Selecione **Novo**.
1. No campo **Nome de modelo de onda**, digite um valor. Ao configurar um modelo de onda, você especifica a sequência na qual os modelos serão correspondidos às linhas liberadas em ordens de venda, ordens de produção ou kanbans. Quando uma linha é liberada para o depósito ou para a produção, use o primeiro modelo da onda que atende aos critérios. É recomendável que você coloque modelos com os critérios mais específicos na parte superior da lista. Quanto mais amplo os critérios, mais provável será que uma linha atenda a eles, o que poderia levar a linhas sendo atribuídas à onda incorreta.  
1. No campo **Descrição do modelo da onda**, digite um valor.
1. No campo **Local**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar site 2.  
1. No campo **Depósito**, insira ou selecione um valor. Se você estiver usando o USMF, você pode selecionar o depósito 24.  
1. Defina o campo **Automatizar criação da onda** como **Sim**. Selecione esta opção para criar automaticamente uma onda quando uma ordem de venda, uma ordem de produção ou um kanban forem liberados para o depósito.  
1. Defina a opção **Processar onda na liberação para o depósito** como **Sim**. Selecione esta caixa de seleção para processar automaticamente a onda e criar trabalho quando uma linha for liberada para o depósito.  
1. Defina a opção **Liberação da onda de automatização** como **Sim**. Marque esta opção para liberar a onda automaticamente. O trabalho de separação é criado e disponibilizado em dispositivos móveis.  
1. Defina a opção **Atribuir para abrir ondas** como **Sim**. As linhas são atribuídas a ondas com base no filtro da consulta para o modelo de onda.  
1. Defina a opção **Processar onda automaticamente no limite** como **Sim**. Selecione esta opção para processar automaticamente o ciclo quando os valores atingirem os limites de peso, de remessa e de linhas especificados no grupo de campos **Limites de ciclo**. Essa opção está disponível apenas se a **Remessa** for selecionada no campo **Tipo de modelo de ciclo**.  
1. Defina a opção **Automatizar liberação do trabalho de reabastecimento** como **Sim**. Selecione esta opção para criar o trabalho de reabastecimento baseado em demanda e libere-o automaticamente. Você deve adicionar o método de ciclo de reabastecimento ao modelo de ciclo e criar um modelo de reabastecimento do tipo **Demanda do ciclo**.  
1. Use as configurações no grupo do campo **Valores padrão** para atribuir atributos do ciclo. Os atributos da onda atuam como filtros, para restringir o tipo de itens que podem usar a onda. Por exemplo, você pode especificar um grupo de itens.  
1. Expanda a seção **Métodos** e defina as ações executadas pelo modelo do ciclo. Os métodos do modelo da onda permitem que você controle a sequência de atividades que cada onda terá quando tiver processado. Por exemplo, você pode ter um método para reabastecimento da onda. Quando você adicionar um método, ele será automaticamente listado na localização apropriada na sequência de etapas. Se você definiu a opção **Liberação do trabalho de reabastecimento de automatização** como **Sim**, você precisará adicionar aqui o método de reabastecimento.  
1. Selecione **Salvar**.
1. Feche a página.
1. Acesse **Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito**.
1. Expanda a seção **Processamento da onda**.
1. No campo **Grupo de lote de processamento de onda**, insira ou selecione um valor.
1. Defina a opção **Processar ondas em lote** como **Sim**.
1. No campo **Esperar por bloqueio (ms)**, insira um número. Insira o tempo, em milissegundos, que uma etapa de alocação aguardará um recurso do sistema que está bloqueado por outra etapa de alocação. Quando esse tempo é excedido, a onda não é processada e uma mensagem de erro é exibida.  
1. Selecione **Salvar**.
1. Feche a página.
1. Acesse **Painel de navegação > Módulos > Controle de produção > Configuração > Parâmetros de controle de produção**.
1. No campo **Liberar para depósito**, selecione uma opção.

    Para ordens de venda e ordens de kanban, o estoque será reservado antes de a ordem ser liberada para o depósito. Caso contrário, os itens ou as linhas de alocação não poderão ser processadas em uma onda. Para ordens de produção, você também tem a opção de escolher **Permitir reserva parcial**. Por exemplo, isso será útil se você tiver os materiais necessários para iniciar uma produção, e puder aguardar até que o material adicional seja disponibilizado para finalizar o processo. Se você selecionar esta opção, repita manualmente a liberação para o processo de armazém quando o material adicional for disponibilizado.
1. Feche a página.

## <a name="additional-resources"></a>Recursos adicionais

- [Criação e processamento de ciclo](../wave-processing.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
