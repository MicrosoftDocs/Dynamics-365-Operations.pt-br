---
title: "Agendar utilização da carga"
description: "Este tópico explica como configurar e agendar o carregamento para um depósito."
author: MarkusFogelberg
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d52ad452c615a61739582431fcd100a7efa3d93a
ms.openlocfilehash: 350666cee8f2643c53e9eed8ee73299bbea1e757
ms.contentlocale: pt-br
ms.lasthandoff: 04/26/2018

---

# <a name="schedule-load-utilization"></a>Agendar utilização da carga

[!include[banner](../includes/banner.md)]

Você pode agendar a utilização de carga para tipos de localização selecionados e também pode projetar a utilização atual e futura de carga. Você pode projetar a carga para um ou mais sites, para unidades de carga (zona ou depósito) ou para uma combinação de um depósito e uma zona.

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a>Agendar e exibir a carga de um depósito ou site

Ao agendar a carga para sites, depósitos ou zonas, crie uma configuração de utilização de espaço e a associe a um plano mestre.

Na configuração de utilização do espaço, use os tipos de local, como **Localização de massa** e **Local de separação** para especificar como a utilização de espaço deve ser projetada. Você também pode especificar um modo da carga de armazenamento, como **Zona**.

A projeção de utilização futura de espaço é baseada nas informações calculadas no plano mestre associado. Planos mestres preveem o planejamento de recurso para ordens de entrada e de saída para produção e operações. A projeção de espaço disponível é baseada na relação entre a configuração de utilização de espaço e o plano mestre selecionado.

Usando o modo de carga de estoque que você selecionou na configuração de utilização de espaço, você pode especificar se o carregamento deve ser projetado para cada depósito ou zona, ou se as projeções devem incluir informações sobre os depósitos e as zonas. Você também pode especificar se as localizações bloqueadas devem ser excluídas do cálculo da utilização de carga.

Você pode projetar a utilização do espaço gerando o relatório **Utilização de carga do depósito**. Quando você gera esse relatório, você pode especificar se a utilização de carga deve ser projetada para cada site, entre os sites ou para a unidade de carga selecionada, como a zona ou o depósito.

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a>Criar uma configuração de utilização de espaço para um depósito

1. Selecione **Gerenciamento de estoque** \> **Configuração** \> **Monitoramento de depósito** \> **Utilização de espaço**.
2. Selecione **Novo** para criar uma configuração de utilização de espaço. Especifique uma ID e um nome para a nova configuração.
3. No campo **Modo da carga de armazenamento**, selecione se a visão geral da utilização de espaço deve mostrar informações por depósito, zona, ou depósito e zona.
4. Defina a opção **Excluir localizações bloqueadas** como **Sim** para excluir os locais de estoque bloqueados do cálculo de espaço disponível. Você pode bloquear uma localização de estoque para entrada e saída especificando uma causa de bloqueio para a localização no campo **Entrada bloqueada** ou **Saída bloqueada** na Guia Rápida **Outro** na página **Locais de estoque**.
5. Na Guia Rápida **Tipo de local**, selecione os tipos de localização para incluir no cálculo de utilização de espaço. Você deve selecionar pelo menos um tipo de localização para a projeção.

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a>Associe uma configuração de utilização de espaço a um plano mestre

1. Selecione **Gerenciamento de estoque** \> **Tarefas periódicas** \> **Agendar utilização da carga**.
2. No campo **Plano mestre**, selecione um plano mestre.
3. No campo **Número de dias**, especifique o número de dias que serão incluídos na projeção de cargas de trabalho atuais e futuros.
4. No campo **Utilização de espaço**, selecione a configuração de utilização de espaço para ser usada na projeção de cargas de trabalho atuais e futuros.

### <a name="specify-the-load-utilization-projection-and-view-information"></a>Especifique a projeção da utilização de carga e exiba as informações

1. Selecione **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Relatórios de estoque físico** \> **Utilização de custo indireto de depósito**.
2. No campo **Mostrar por**, selecione o nível da projeção de utilização de espaço:

    - **Site** – Projetar a utilização de espaço para cada site. Esta projeção é útil se, por exemplo, você desejar exibir todos os depósitos de um site para que possa equilibrar a utilização de espaço entre os depósitos.
    - **Unidade de carga** – Projetar a utilização de espaço para zonas ou depósitos. O espaço disponível é então projetado de acordo com o valor que você selecionou no campo **Modo da carga de armazenamento** na página **Utilização de espaço** quando criou a configuração de utilização de espaço.

3. Siga uma destas etapas, dependendo do valor selecionado na etapa anterior:

    - Se você selecionou **Site** no campo **Exibir por**, o campo **Site** está disponível. Selecione um ou mais sites para incluir na projeção.
    - Se você selecionou **Carregar unidade** no campo **Exibir por**, o campo **Carregar unidade** está disponível. Selecione a unidade de carga.

4. No campo **Carregar tipo**, selecione **Volume** ou **Peso** para especificar o depósito operando a unidade para a qual você projeta espaço.
5. No campo **Configuração de utilização de espaço**, selecione a configuração de utilização de espaço na qual a projeção deve ser baseada.

