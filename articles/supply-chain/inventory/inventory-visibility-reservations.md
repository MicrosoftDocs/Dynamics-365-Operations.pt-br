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
ms.openlocfilehash: 4a85520c0911bb7eed5842b3fd5bd706009351e5
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500346"
---
# <a name="inventory-visibility-reservations"></a>Reservas de Visibilidade de Estoque

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tópico descreve como configurar o recurso de reserva para criar reservas, consumir reservas e/ou cancelar a reserva de quantidades de estoque especificadas usando o Visibilidade de Estoque.

As reservas marcam uma quantidade de estoque que será usada no futuro. Quando você cria uma reserva, o sistema evita que outros solicitações reservem ou consumam os bens reservados até que a reserva seja consumida ou cancelada. As reservas são criadas, consumidas e canceladas usando chamadas de API para o serviço Visibilidade de Estoque.

Opcionalmente, você pode configurar o Microsoft Dynamics 365 Supply Chain Management (e outros sistemas de terceiros) para compensar automaticamente a quantidade que foi reservada usando o Visibilidade de Estoque. A quantidade compensada é excluída dos registros de reserva no Visibilidade de Estoque.

Quando você ativa o recurso de reserva, o Supply Chain Management fica automaticamente pronto para compensar as reservas feitas usando o Visibilidade de Estoque.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Ativar e configurar o recurso de reserva

Para ativar o recurso de reserva, siga estas etapas.

1. Entre no Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Gerenciamento de Recursos**, ative o recurso *OnHandReservation*.
1. Entre no Supply Chain Management.
1. Acesse o espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e habilite o recurso *Integração de Visibilidade de Estoque com compensação de reserva* (exige a versão 10.0.22 ou posterior).
1. Acesse **Gerenciamento de estoque \> Configuração \> Parâmetros de integração de Visibilidade de Estoque**, abra a guia **Compensação de reserva** e defina as seguintes configurações:
    - **Habilitar compensação de reserva** – Defina como *Sim* para habilitar essa funcionalidade.
    - **Modificador de compensação de reserva** – Selecione o status da transação de estoque que compensará as reservas feitas em Visibilidade de Estoque. Essa configuração determina a fase de processamento da ordem que dispara compensações. O estágio é rastreado pelo status de transação do estoque da ordem. Selecione uma das seguintes opções:
        - *Em ordem* — para o status *Na transação*, uma ordem enviará uma solicitação de compensação quando for criada. A quantidade de compensação será a quantidade da ordem criada.
        - *Reserva* — para o status de *Transação com solicitação de reserva*, uma ordem enviará uma solicitação de compensação quando for reservada, retirada, quando a guia de remessa for postada ou quando for faturada. A solicitação será disparada apenas uma vez, para a primeira etapa quando ocorrer o referido processo. A quantidade de compensação será a quantidade na qual o status da transação de estoque é alterado de *Em ordem* para *Qtd. encomendada* (ou status posterior) na linha da ordem correspondente.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Usar o recurso de reserva no Visibilidade de Estoque

Quando você chama a API de reserva, o sistema marca a reserva das mercadorias e quantidades especificadas. Você deve definir uma hierarquia de reserva e postar solicitações que correspondam a essa hierarquia de reserva. As reservas podem ser feitas chamando as APIs de reserva diretamente.

### <a name="configure-the-reservation-hierarchy"></a>Configurar a hierarquia de reserva

A hierarquia de reservas descreve a sequência de dimensões que deve ser especificada quando as reservas são feitas. Funciona da mesma forma que a hierarquia do índice funciona para consultas disponíveis.

A hierarquia de reserva pode ser diferente da hierarquia de índice. Essa independência permite implementar o gerenciamento de categorias, no qual os usuários podem dividir as dimensões em detalhes para especificar os requisitos para fazer reservas mais precisas.

Para configurar uma hierarquia de reserva flexível no Power Apps, abra a página **Configuração** e, na guia **Hierarquia de reserva flexível**, configure a hierarquia de reserva adicionando e/ou modificando dimensões e seus níveis de hierarquia.

A hierarquia de reserva reversível deve conter `SiteId` e `LocationId` como componentes, pois eles constroem a configuração da partição.

Para obter mais informações sobre como configurar reservas, consulte [Configuração de reserva](inventory-visibility-configuration.md#reservation-configuration).

### <a name="call-the-reservation-api"></a>Chamar a API de reserva

As reservas são feitas no serviço de Visibilidade de Estoque enviando uma solicitação POST para a URL do serviço, como `/api/environment/{environment-ID}/onhand/reserve`.

Para uma reserva, o corpo da solicitação deve conter uma ID da organização, uma ID do produto, quantidades reservadas e dimensões. A solicitação gera uma ID de reserva exclusiva para cada registro de reserva. O registro de reserva contém a combinação única de ID do produto e dimensões.

Ao chamar a API de reserva, você pode controlar a validação da reserva especificando o parâmetro booliano `ifCheckAvailForReserv` no corpo da solicitação. Um valor `True` significa que a validação é necessária, enquanto um valor `False` significa que a validação não é necessária. O valor padrão é `True`.

Se você deseja cancelar uma reserva ou cancelar a reserva de quantidades de estoque especificadas, defina a quantidade como um valor negativo e defina o parâmetro `ifCheckAvailForReserv` como `False` para ignorar a validação.

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

### <a name="set-up-the-reservation-offset-modifier"></a>Configurar o modificador de compensação de reserva

Se ainda não fez isso, configure o modificador de reserva conforme descrito em [Ativar e configurar o recurso de reserva](#turn-on).

### <a name="set-up-reservation-ids"></a>Configurar IDs de reserva

A ID de reserva marca exclusivamente um registro de reserva no Visibilidade de Estoque. No Supply Chain Management, os usuários colocam reservas nas linhas de ordem para marcar a compensação para o registro de reserva correspondente.

Para configurar IDs de reserva no Supply Chain Management, siga estas etapas.

1. Abra uma ordem de venda (por exemplo, na página **Todas as ordens de venda**).
1. Na Guia Rápida **Linhas de ordem de venda**, selecione uma linha de ordem.
1. Na Guia Rápida **Linhas de ordem de venda**, na barra de ferramentas, selecione **Atualizar linha \> Estoque \> Integração de Visibilidade de Estoque**.
1. Insira as IDs de reserva relevantes.

A alteração do status do estoque corresponde à configuração do modificador de compensação.
