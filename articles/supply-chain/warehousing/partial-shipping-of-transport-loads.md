---
title: Remessa parcial de uma carga de transporte
description: Este tópico explica como você pode enviar uma carga parcialmente e adiar o planejamento de capacidade da carga.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: e92a15cf4e2694eba1804184a02a7fd13159799e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215645"
---
# <a name="partial-shipment-of-a-transport-load"></a>Remessa parcial de uma carga de transporte

[!include[banner](../includes/banner.md)]

Configurando a remessa de cargas parcial, você pode administrar as cargas onde a capacidade não pode ser determinada até que todas as linhas de venda sejam adicionadas a uma carga. O processo poderá ser finalizado quando a contagem exata de palete for conhecida. Portanto, você não precisa concluir quais paletes serão atribuídos a qual transporte até o momento em que um transporte está sendo carregado fisicamente para o estoque preparado.

Este recurso fornece uma alternativa para a aplicação de uma estrutura mais rígida, onde você pode determinar que paletes serão atribuídos ao transporte antes do trabalho de separação ou do trabalho de carga ser criado. Em vez disso, os usuários poderão configurar cargas individuais para uma confirmação parcial de remessa. Os processos de carga de transporte para essas em cargas podem ocorrer depois. Portanto, o departamento de planejamento de transporte pode planejar cargas sem ter que considerar a capacidade de transportes individuais.

No momento da carga, os funcionários podem definir uma nova carga de transporte que poderá ser carregada para um palete. Como alternativa, eles podem identificar uma carga de transporte existente. Esses dados pode ser registrados por meio de um dispositivo móvel. Portanto, vários trabalhadores de depósito podem carregar o estoque das mesmas cargas ou de cargas diferentes no mesmo carrinho. As cargas podem ser enviadas totalmente ou parcialmente.

> [!NOTE] 
> Para carregar o estoque de uma carga para uma determinada carga de transporte e enviá-la parcialmente, o trabalho deve ser gerado usando uma classe de carga em um modelo de trabalho. O trabalho ordinário de separação do tipo **Separação** não pode ser carregado para uma carga de transporte, como um carrinho.

## <a name="set-up-transport-loads-for-partial-shipment"></a>Configurar cargas de transporte para remessa parcial

A configuração de remessa parcial de cargas consistem nos dois procedimentos a seguir.

### <a name="set-the-loading-strategy"></a>Configurar a estratégia de carga

É necessário habilitar a carga parcial definindo a estratégia de carga. Você pode definir a estratégia de carga após criar uma carga.

1. Selecione **Gerenciamento de depósito** \> **Cargas** \> **Todas as cargas**.
2. Selecione uma carga e clique em **Cabeçalho**.
3. No campo **Estratégia de carga** , selecione **Remessa de carga parcial permitida**.

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a>Criar um item de menu para cargas de transporte

É necessário criar um novo item de menu que permite que as cargas de transporte sejam carregadas. Uma carga de transporte permite o agrupamento de linhas de trabalho de uma carga ou de várias cargas. Tudo que é adicionado à carga de transporte pode ser enviado por um scanner móvel.

1. Selecione **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel**.
2. Selecione **Novo**e, depois, no campo **Modo** , selecione **Trabalho**.
3. Defina a opção **Usar trabalho existente** para **Sim**.
4. Na guia **Geral**, no campo **Direcionado por**, selecione **Carga de transporte**.
5. Para habilitar a confirmação de remessa em um scanner móvel, no campo **Tipo de confirmação de remessa permitido** , selecione **Carga de transporte**.

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a>Confirmar remessa de uma carga de transporte do cliente

Essa configuração permite confirmar uma carga de transporte que inclua uma carga máxima ou uma carga parcialmente carregada a ser enviada.

1. Selecione **Gerenciamento de depósito** \> **Cargas** \> **Cargas de transporte**.
2. No painel de ação, na guia **Enviar e receber** , no grupo **Confirmar** , selecione **Transporte**.
