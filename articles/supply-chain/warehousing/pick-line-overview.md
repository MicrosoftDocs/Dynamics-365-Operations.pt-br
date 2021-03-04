---
title: Configurar um item de menu do dispositivo móvel para fornecer uma visão geral da linha de separação
description: Este tópico explica como definir quando uma lista de todas as linhas de trabalho será mostrada aos funcionários do depósito que estão processando o trabalho do depósito em um dispositivo móvel. Esse recurso pode ser útil para funcionários de depósito que geralmente precisam de uma visão geral das linhas de separação em uma ordem de serviço para que possam otimizar sua sequência de separação.
author: MarkusFogelberg
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 3a2c8a69a2c64214a38a654042ea2f62575e7f52
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422064"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a>Configurar um item de menu do dispositivo móvel para fornecer uma visão geral da linha de separação

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica como configurar opções relacionadas à visão geral da linha de separação para itens de menu do dispositivo móvel que são usados para processar o trabalho de separação. A visão geral da linha de separação permite que os funcionários do depósito exibam e selecionem em uma lista de todas as linhas de trabalho relacionadas à tarefa atual. Esse recurso pode ajudar os trabalhadores a otimizar sua sequência de separação. O recurso oferece opções que substituem o botão **Ignorar** padrão que permite que os trabalhadores percorram as linhas um de cada vez, em uma ordem fixa. (No entanto, a opção de usar esse botão ainda está disponível.)

Os administradores podem configurar cada item de menu individualmente para controlar como, quando e onde o aplicativo do depósito apresenta a visão geral da linha de separação.

## <a name="turn-on-the-work-pick-line-overview-feature"></a>Ativar o recurso Visão geral da linha de separação de trabalho

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** _Gerenciamento de Depósito_
- **Nome do recurso:** _Visão geral da linha de separação de trabalho_

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a>Configurar os itens de menu para mostrar uma lista de todas as linhas de trabalho

Para configurar um item de menu do dispositivo móvel para fornecer uma visão geral da linha de separação, siga as etapas a seguir.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Selecione ou crie um item de menu relacionado ao trabalho de seleção e defina os seguintes valores:

    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Sim*
    - **Direcionado por:** *Usuário direcionado* ou *Sistema direcionado*

    Para obter mais informações sobre como criar itens de menu e usar as várias configurações que estão disponíveis na página **Itens de menu do dispositivo móvel**, consulte [Configurar dispositivos móveis para trabalho de depósito](configure-mobile-devices-warehouse.md).

1. Na Guia Rápida **Geral**, configure o recurso definindo o campo **Mostrar lista de linhas de trabalho** para um dos seguintes valores:

    - **Mostrar somente sob solicitação** – Os trabalhadores podem optar por exibir a lista de linha de separação selecionando o botão **Pular para** no aplicativo do depósito.
    - **Mostrar no início de cada separação** – Os trabalhadores verão a lista sempre que iniciam ou terminam uma linha de separação. Eles também podem exibir a lista novamente selecionando o botão **Pular para** no aplicativo do depósito.
    - **Mostrar apenas no início da primeira separação** – Os trabalhadores verão a lista toda vez que iniciarem um novo trabalho de separação, mas não após cada linha. Eles também podem exibir a lista novamente selecionando o botão **Pular para** no aplicativo do depósito.
    - **Nunca mostrar** – O botão **Ignorar** padrão aparece no aplicativo de depósito e a exibição da lista de linhas de trabalho é desativada. O botão **Ignorar** permite que os trabalhadores percorram as linhas uma por vez, em uma ordem fixa. Eles também podem percorrer a lista quantas vezes forem necessárias, até que todas as linhas tenham sido processadas.

1. No Painel de ações, selecione **Salvar**.

    Se você definir o campo **Mostrar lista de linhas de trabalho** para qualquer valor, exceto *Nunca mostrar*, o botão **Lista de campos** no Painel de Ações ficará disponível.

1. No Painel de Ação, selecione **Lista de campos**.
1. Na página **Lista de campos**, configure as informações que o aplicativo de depósito mostra para cada linha na lista.

    - O campo **Controle primário** é sempre definido como *LineNum*. Portanto, cada linha da lista começa com um número de linha.
    - Use os campos **Campo de exibição** restantes para adicionar até sete campos de exibição adicionais, conforme necessário. Em cada campo **Campo de exibição**, selecione o nome de um campo de linha de trabalho. Cada linha mostrará um valor para esse campo. Os valores serão mostrados na ordem que você selecionar aqui. É possível deixar alguns dos campos **Campo de exibição** em branco se não exigir todos os sete valores.

1. No Painel de Ações, selecione **Salvar** e feche a página **Lista de campos**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]