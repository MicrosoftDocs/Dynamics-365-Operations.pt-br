---
title: Reservas de Visibilidade de Estoque
description: Este tópico descreve como configurar o recurso de reserva para criar reservas, consumir reservas e/ou cancelar a reserva de quantidades de estoque especificadas usando o Visibilidade de Estoque.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6c87018cbfbe22fbbc441a1a23aee0ac44af9ddc
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345140"
---
# <a name="inventory-visibility-reservations"></a>Reservas de Visibilidade de Estoque

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tópico descreve como configurar o recurso de reserva para criar reservas, consumir reservas e/ou cancelar a reserva de quantidades de estoque especificadas usando o Visibilidade de Estoque.

As reservas marcam uma quantidade de estoque que será usada no futuro. Quando você cria uma reserva, o sistema evita que outros solicitações reservem ou consumam os bens reservados até que a reserva seja consumida ou cancelada. As reservas são criadas, consumidas e canceladas usando chamadas de API para o serviço Visibilidade de Estoque.

Opcionalmente, você pode configurar o Microsoft Dynamics 365 Supply Chain Management (e outros sistemas de terceiros) para compensar automaticamente a quantidade que foi reservada usando o Visibilidade de Estoque. A quantidade compensada é excluída dos registros de reserva no Visibilidade de Estoque.

Quando você ativa o recurso de reserva, o Supply Chain Management fica automaticamente pronto para compensar as reservas feitas usando o Visibilidade de Estoque.

> [!NOTE]
> A funcionalidade de compensação requer o Supply Chain Management versão 10.0.22 ou posterior. Se você deseja usar reservas do Visibilidade de Estoque, recomendamos que espere até ter atualizado o Supply Chain Management para a versão 10.0.22 ou posterior.

## <a name="turn-on-the-reservation-feature"></a>Ativar o recurso de reserva

Para ativar o recurso de reserva, siga estas etapas.

1. No Power Apps, abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Gerenciamento de Recursos**, ative o recurso *OnHandReservation*.
1. Entre no Supply Chain Management.
1. Acesse **Gerenciamento de Estoque \> Configuração \> Parâmetros de integração de Visibilidade de Estoque**.
1. Em **Em Compensação de reserva**, defina a opção **Habilitar compensação de reserva** como *Sim*.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Usar o recurso de reserva no Visibilidade de Estoque

Quando você chama a API de reserva, o sistema marca a reserva das mercadorias e quantidades especificadas. Você deve definir uma hierarquia de reserva e postar solicitações que correspondam a essa hierarquia de reserva. As reservas podem ser feitas chamando as APIs de reserva diretamente.

### <a name="configure-the-reservation-hierarchy"></a>Configurar a hierarquia de reserva

A hierarquia de reservas descreve a sequência de dimensões que deve ser especificada quando as reservas são feitas. Funciona da mesma forma que a hierarquia do índice funciona para consultas disponíveis.

A hierarquia de reserva pode ser diferente da hierarquia de índice. Essa independência permite implementar o gerenciamento de categorias, no qual os usuários podem dividir as dimensões em detalhes para especificar os requisitos para fazer reservas mais precisas.

Para configurar uma hierarquia de reserva flexível no Power Apps, abra a página **Configuração** e, na guia **Mapeamento de reserva flexível**, configure a hierarquia de reserva adicionando e/ou modificando dimensões e seus níveis de hierarquia.

### <a name="call-the-reservation-api"></a>Chamar a API de reserva

As reservas são feitas no serviço de Visibilidade de Estoque enviando uma solicitação POST para a URL do serviço, como `/api/environment/{environment-ID}/onhand/reserve`.

Para uma reserva, o corpo da solicitação deve conter uma ID da organização, uma ID do produto, quantidades reservadas e dimensões. A solicitação gera uma ID de reserva exclusiva para cada registro de reserva. O registro de reserva contém a combinação única de ID do produto e dimensões.

Aqui está um exemplo do corpo da solicitação, para referência.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "SoftReservOrdered",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

## <a name="offset-reservations-in-supply-chain-management"></a>Reservas de compensação no Supply Chain Management

Para status de transação de estoque que incluir um modificador de compensação de reserva especificado, a atualização da transação compensará o registro de reserva correspondente quando todas as seguintes condições forem atendidas:

- A ID de reserva na transação de estoque corresponde à ID de reserva do registro de reserva no serviço do Visibilidade de Estoque.
- As dimensões da transação de estoque são idênticas às dimensões do registro de reserva no serviço Visibilidade de Estoque.
- Alterações no status da transação de estoque disparam compensações para reservas quando o status da transação de estoque reflete o fato de que um processo de ordem foi concluído ou ignorado.

A quantidade de compensação segue a quantidade de estoque que é especificada nas transações de estoque. A compensação não terá efeito se nenhuma quantidade reservada permanecer no serviço Visibilidade de Estoque.

> [!NOTE]
> A funcionalidade de compensação está disponível a partir da versão 10.0.

### <a name="set-up-the-reserve-offset-modifier"></a>Configurar o modificador de compensação de reserva

O modificador de compensação de reserva determina o estágio de processamento de ordem que dispara as compensações. O estágio é rastreado pelo status de transação do estoque da ordem. Para configurar o modificador de compensação de reserva, siga estas etapas.

1. Acesse **Gerenciamento de Estoquet \> Configuração \> Parâmetros de integração de Visibilidade de Estoque \> Compensação de reserva**.
1. Defina o campo **Modificador de compensação de reserva** com um dos seguintes valores:

    - *Em ordem* — para o status *Na transação*, uma ordem enviará uma solicitação de compensação quando for criada.
    - *Reserva* — para o status de *Transação com solicitação de reserva*, uma ordem enviará uma solicitação de compensação quando for reservada, retirada, quando a guia de remessa for postada ou quando for faturada. A solicitação será disparada apenas uma vez, para a primeira etapa quando ocorrer o referido processo.

### <a name="set-up-reservation-ids"></a>Configurar IDs de reserva

A ID de reserva marca exclusivamente um registro de reserva no Visibilidade de Estoque. No Supply Chain Management, os usuários colocam reservas nas linhas de ordem para marcar a compensação para o registro de reserva correspondente.

Para configurar IDs de reserva no Supply Chain Management, siga estas etapas.

1. Abra uma ordem de venda (por exemplo, na página **Todas as ordens de venda**).
1. Na Guia Rápida **Linhas de ordem de venda**, selecione uma linha de ordem.
1. Na Guia Rápida **Linhas de ordem de venda**, na barra de ferramentas, selecione **Atualizar linha \> Estoque \> Integração de Visibilidade de Estoque**.
1. Insira as IDs de reserva relevantes.

A alteração do status do estoque corresponde à configuração do modificador de compensação.
