---
title: Suporte ao Inventory Visibility para itens de WMS
description: Este artigo descreve o suporte à Visibilidade de Estoque para itens habilitados para processos de gerenciamento de depósito (itens de WMS).
author: yufeihuang
ms.date: 03/10/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 54ce637d2d7b590988f7590eae5248276bcc4b96
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066600"
---
# <a name="inventory-visibility-support-for-wms-items"></a>Suporte ao Inventory Visibility para itens de WMS

[!include [banner](../includes/banner.md)]

Este artigo descreve o suporte à Visibilidade de Estoque para itens habilitados para processos de gerenciamento de depósito (WMS). O recurso que adiciona essa capacidade à visibilidade de estoque é denominado *WMS Avançado*.

## <a name="wms-items"></a>Itens de WMS

Um item de WMS é um item habilitado para WMS e processado em um depósito que também é habilitado para WMS.

Para obter mais informações sobre o WMS e o módulo **Warehouse Management** no Microsoft Dynamics 365 Supply Chain Management, consulte [Visão geral do Warehouse Management](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Escopo do recurso

O recurso de WMS avançado para visibilidade de estoque se concentra em cálculos de quantidade disponível baseados em consultas de disponibilidade. O recurso não se destina a permitir que você use a visibilidade de estoque para gerenciar atividades de processamento de depósito em geral. A visibilidade do estoque não expõe conceitos específicos de depósito a seus usuários. Veja a seguir alguns exemplos desses conceitos:

- Hierarquia de reservas
- Se um item ou um depósito está habilitado para WMS
- ID do grupo de sequências de unidade
- Processos específicos de depósito, como remessas, cargas, ondas e trabalho

A visibilidade de estoque infere essas informações com base nos dados enviados do Supply Chain Management. Os dados específicos de WMS (ou seja, dados da tabela `WHSInventReserve`) não são visíveis para os usuários.

Ao usar o recurso de WMS avançado para a visibilidade de estoque, todos os resultados da consulta serão idênticos aos resultados das consultas feitas diretamente no Supply Chain Management. No entanto, não serão idênticos aos resultados de consultas feitas usando o aplicativo móvel Warehouse Management, porque o aplicativo móvel usa uma lógica de cálculo ligeiramente diferente.

## <a name="when-to-use-the-feature"></a>Quando usar o recurso

Recomendamos que você use o recurso de WMS avançado para a visibilidade de estoque em cenários em que todas as condições a seguir são atendidas:

- Você está sincronizando os dados do Supply Chain Management com a visibilidade de estoque.
- Você está usando WMS no Supply Chain Management.
- Os usuários fazem reservas para itens de WMS em níveis diferentes do nível de depósito (por exemplo, porque você está usando trabalho de depósito).

Em outros cenários, os resultados da consulta de disponibilidade serão os mesmos, independentemente da habilitação do recurso de WMS avançado para a visibilidade de estoque. Além disso, o desempenho será melhor se você não habilitar o recurso nesses cenários, pois há menos cálculos e menor sobrecarga.

## <a name="enable-the-advanced-wms-feature-for-inventory-visibility"></a>Habilitar o recurso de WMS avançado para a visibilidade de estoque

Para habilitar o recurso de WMS avançado para visibilidade de estoque, siga estas etapas.

1. Entre no Supply Chain Management como administrador.
1. Abra o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e habilite os seguintes recursos nesta ordem:

    1. *Integração da Visibilidade de Estoque*
    1. *Habilitar itens de depósito em Visibilidade de Estoque*

1. Acesse **Gerenciamento de Estoque \> Configuração \> Parâmetros de integração de Visibilidade de Estoque**.
1. Na guia **Habilitar itens de WMS**, defina a opção **Habilitar itens de WMS** como *Sim*.
1. Entre no Power Apps.
1. Abra a página **Configuração** e, em seguida, na guia **Gerenciamento de Recursos**, ative o recurso *AdvancedWHS*.
1. No Supply Chain Management, acesse **Gerenciamento de Estoque \> Tarefas Periódicas \> Integração de Visibilidade de Estoque**.
1. No painel de ações, selecione **Desabilitar** para desabilitar temporariamente a visibilidade de estoque.
1. No Painel de Ações, selecione **Habilitar** para reabilitar a visibilidade de estoque. O suplemento é recarregado, e o novo recurso agora está habilitado. Os dados relacionados a WMS começam a ser sincronizados com a visibilidade de estoque.

## <a name="query-on-hand-quantities-of-wms-items"></a>Consultar quantidades disponíveis de itens de WMS

Para consultar itens de WMS, use a mesma [sintaxe de interface de programação de aplicativo (API) e de mensagens](inventory-visibility-api.md) que você usa para itens que não são de WMS. Não é necessário especificar se um item é um item de WMS ou um item que não é de WMS. A visibilidade de estoque distingue automaticamente os itens, com base nos dados armazenados.

Os resultados de consultas para itens de WMS são essencialmente os mesmos que os resultados de itens que não são de WMS. A única diferença é que as seguintes medidas físicas da fonte de dados `fno` são calculadas com base na lógica de WMS no Supply Chain Management:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Todas as outras medidas físicas são calculadas da mesma forma quando o recurso de WMS avançado para visibilidade de estoque está desabilitado.

Para obter informações detalhadas sobre como os cálculos disponíveis para itens de WMS funcionam, consulte o white paper [Reservas no Warehouse Management](https://www.microsoft.com/download/details.aspx?id=43284).

As entidades de dados que são exportadas para o Dataverse ainda não podem atualizar as quantidades para itens de WMS. As quantidades mostradas nas entidades de dados estão corretas para itens que não são de WMS e para quantidades que não são afetadas pela lógica de WMS (isto é, medidas exceto `AvailPhysical`, `AvailOrdered`, `ReservPhysical` e `ReservOrdered` na fonte de dados `fno`).

São proibidas alterações nas quantidades de itens de WMS armazenadas na fonte de dados do Supply Chain Management. Como no caso de outros recursos da visibilidade de inventário, essa restrição é aplicada para ajudar a evitar conflitos.

## <a name="soft-reservations-on-wms-items-in-inventory-visibility"></a>Reservas flexíveis em itens de WMS na visibilidade de estoque

Em geral, as [reservas flexíveis](inventory-visibility-reservations.md) são compatíveis em itens de WMS. Você pode incluir medidas físicas relacionadas a WMS em cálculos de reserva flexível. 

Em uma limitação conhecida, o cálculo *disponível para reserva* não é compatível com itens de WMS atualmente. Portanto, se houver reserva acima das dimensões atuais nas quais uma reserva flexível está ocorrendo, o cálculo *disponível para reserva* estará incorreto. As reservas flexíveis não serão afetadas quando a opção **ifCheckAvailForReserv** estiver desabilitada na [API de reserva flexível](inventory-visibility-api.md#create-one-reservation-event).

Esta restrição também se aplica a recursos e personalizações com base em reservas flexíveis (como alocação).

## <a name="calculate-available-to-promise-quantities"></a>Calcular quantidades disponíveis para promessa

A solução oferece suporte total à opção [disponível para promessa (ATP)](inventory-visibility-available-to-promise.md) para itens de WMS. Você pode definir cálculos de ATP sem se preocupar com detalhes específicos de WMS.
