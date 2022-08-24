---
title: Versão do lote de ordens de transferência parcialmente reservadas
description: Este artigo descreve como configurar e aplicar liberação de lote das ordens de transferência reservadas parcialmente de um dispositivo móvel.
author: perlynne
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 741377a43e2bfe702b213647cc6460a3d6ad93fb
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218672"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>Versão do lote de ordens de transferência parcialmente reservadas

[!include [banner](../includes/banner.md)]

A funcionalidade de liberação de lote de ordens de transferência reservada parcialmente permite que você libere as ordens se transferência parcialmente para um depósito usando um trabalho de lote.
Como você tem a opção de liberar uma quantidade parcial, você não terá que esperar a quantidade total da ordem ficar disponível no depósito antes de liberar uma ordem.

A liberação de ordens para um depósito é um processo de gerenciamento de depósito (WMS) avançado. Este processo envolve atividades como separação, embalagem e entrega que um trabalhador do depósito pode executar usando um dispositivo móvel.

## <a name="where-it-applies"></a>Aplica-se a

Para esta funcionalidade, as ordens de transferência são liberadas para um depósito usando um trabalho de lote. Essa funcionalidade será útil quando não houver estoque suficiente no depósito, mas você ainda queira transferir itens de um depósito para outro.

## <a name="how-it-is-set-up"></a>Como é configurada

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>Especificar critérios de atendimento para ordens de venda e ordens de transferência

Antes que uma ordem possa ser liberada parcialmente para um depósito em um lote, os critérios de atendimento devem ser atendidos. Esses critérios de atendimento são determinados pela política de atendimento.

As políticas de atendimento para ordens de venda e ordens de transferência são especificadas na empresa. Dependendo da instalação da política de atendimento, a liberação de ordens em um lote será aceita ou rejeitada. As ordens serão processados apropriadamente.

- Para criar políticas de atendimento para ordens de transferência e ordens de venda, vá para **Gerenciamento de depósito \> Configuração \> Liberar para o depósito \> Políticas de atendimento** e, depois, crie uma política de atendimento inserindo um nome e uma descrição.
- Para especificar uma taxa de atendimento, um tipo de valor e a mensagem que é mostrada, se a política de atendimento for violada, vá para **Gerenciamento de depósito \> Configuração \> Liberar para o depósito \> Políticas de atendimento** e, depois, defina os campos **Taxa de atendimento**, **Tipo de valor** e **Mensagem de violação de atendimento**.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>Defina as políticas de atendimento para ordens de venda e ordens de transferência

- Para definir as políticas de atendimento para ordens de transferência, vá para **Gerenciamento de estoque \> Configuração \> Parâmetros de gerenciamento de depósito e estoque**. Depois, na guia **Ordens de transferência** na seção **Gerenciamento de depósito**, selecione uma política de atendimento da ordem de transferência.
- Para definir as políticas de atendimento das ordens de venda, vá para **Contas a receber \> Configuração \> Parâmetros de contas a receber**. Depois, na guia **Gerenciamento de depósito**, selecione uma política de atendimento da ordem de venda.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-released-in-a-batch"></a>Permitir a liberação em um lote e especificar a quantidade que deve ser liberada em um lote

Um trabalho em lotes é usado para liberar ordens para um depósito em um lote. Os parâmetros que distinguem ordens que devem ser executadas em um trabalho em lotes são definidos no próprio trabalho em lotes.

O parâmetro **Quantidade** especifica se toda a quantidade ou a quantidade fisicamente reservada deve ser liberada em lote. O parâmetro **Permitir a liberação de ordens parcialmente liberadas** determina se as ordens em lote devem ser aceitas ou rejeitada, caso tenham sido liberadas parcialmente anteriormente.

- Para definir os parâmetros **Quantidade** e **Permitir a liberação de ordens parcialmente liberadas** para ordens de transferência, vá para **Gerenciamento de depósito \> Liberar para o depósito \> Liberação automática de ordens de transferência**.
- Para definir os parâmetros **Quantidade** e **Permitir a liberação de ordens parcialmente liberadas** para ordens de venda, vá para **Gerenciamento de depósito \> Liberar para o depósito \> Liberação automática de ordens de venda**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
