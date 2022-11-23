---
title: Suporte ao Inventory Visibility para itens de WMS
description: Este artigo descreve o suporte à Visibilidade de Estoque para itens habilitados para processos de gerenciamento de depósito (itens de WMS).
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: bed402ecf20c19e81b2687efd90dba600460971a
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762730"
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

Recomendamos que você use o recurso de WMS avançado para o Visibilidade de estoque em cenários em que todas as condições a seguir são atendidas:

- Você está sincronizando os dados do Supply Chain Management com a visibilidade de estoque.
- Você está usando WMS no Supply Chain Management.
- Os usuários fazem reservas para itens de WMS em níveis abaixo do nível de depósito (por exemplo, no nível da placa de licença porque você está processando trabalho de depósito).

Em outros cenários, os resultados da consulta de disponibilidade serão os mesmos, independentemente da habilitação do recurso de WMS avançado para a visibilidade de estoque. Além disso, o desempenho será melhor se você não habilitar o recurso nesses cenários, pois há menos cálculos e menor sobrecarga.

## <a name="enable-the-wms-feature-for-inventory-visibility"></a>Habilitar o recurso de WMS avançado para o Visibilidade de estoque

Para habilitar o recurso de WMS avançado para visibilidade de estoque, siga estas etapas.

1. Entre no Supply Chain Management como administrador.
1. Abra o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e habilite os seguintes recursos nesta ordem:

    1. *Integração da Visibilidade de Estoque*
    1. *Habilitar itens de depósito em Visibilidade de Estoque*

1. Acesse **Gerenciamento de Estoque \> Configuração \> Parâmetros de integração de Visibilidade de Estoque**.
1. Na guia **Habilitar itens de WMS**, defina a opção **Habilitar itens de WMS** como *Sim*.
1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
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

## <a name="on-hand-list-view-and-data-entity-for-wms-items"></a>Exibição de lista disponível e entidade de dados para itens WMS

A página **Pré-carregar Resumo da Visibilidade de Estoque** fornece uma exibição da entidade *Resultados Pré-carregados da Consulta de Índice Disponível*. Diferentemente da entidade *Resumo de estoque*, a entidade *Resultados Pré-carregados da Consulta de Índice Disponível* oferece uma lista de estoque disponível para os produtos juntamente com as dimensões selecionadas. A Visibilidade de Estoque sincroniza os dados de resumo pré-carregados a cada 15 minutos.

Se você usar o Visibilidade de estoque com itens WMS e quiser visualizar a lista disponível para itens WMS, recomendamos que você habilite o recurso *Pré-carregar o resumo de visibilidade do inventário* (consulte também [Pré-carregar uma consulta disponível simplificada](inventory-visibility-power-platform.md#preload-streamlined-onhand-query)). Uma entidade de dados correspondente no Dataverse armazena o resultado do pré-carregamento da consulta, que é atualizado a cada 15 minutos. O nome da entidade de dados é `Onhand Index Query Preload Result`.

> [!IMPORTANT]
> A entidade do Dataverse é somente leitura. Você pode visualizar e exportar os dados nas entidades do Visibilidade de estoque, mas **não os modifique**.

São proibidas alterações nas quantidades de itens de WMS armazenadas na fonte de dados do Supply Chain Management (`fno`). Esse comportamento corresponde ao comportamento de outros recursos do Visibilidade de estoque. Essa restrição é aplicada para ajudar a evitar conflitos.

## <a name="wms-item-compatibility-for-other-functions-in-inventory-visibility"></a>Compatibilidade de itens WMS para outras funções no Visibilidade de estoque

Os itens WMS são compatíveis com [reservas flexíveis](inventory-visibility-reservations.md) e [alocação de estoque](inventory-visibility-allocation.md). Você pode incluir medidas físicas relacionadas a WMS em cálculos de reserva flexível e alocação.

## <a name="calculate-available-to-promise-quantities"></a>Calcular quantidades disponíveis para promessa

A solução oferece suporte total à opção [disponível para promessa (ATP)](inventory-visibility-available-to-promise.md) para itens de WMS. Você pode definir cálculos de ATP sem se preocupar com detalhes específicos de WMS.
