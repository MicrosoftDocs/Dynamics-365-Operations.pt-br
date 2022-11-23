---
title: Reservas do Inventory Visibility
description: Este artigo descreve como configurar o recurso de reserva para criar reservas, consumir reservas e/ou cancelar a reserva de quantidades de estoque especificadas usando o Visibilidade de Estoque.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0ae0589f8bac7ebf9b43cf0f3bc02680d324b29b
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762713"
---
# <a name="inventory-visibility-reservations"></a>Reservas do Inventory Visibility

[!include [banner](../includes/banner.md)]

Este artigo descreve um caso de uso típico para reservas flexíveis e explica como configurá-las na Visibilidade do estoque. Ele inclui informações sobre como criar reservas flexíveis, compensá-las no consumo físico e ajustar ou cancelar a reserva de quantidades de estoque especificadas.

## <a name="sample-use-case-for-soft-reservation"></a>Exemplo de caso de uso de reserva flexível

As reservas flexíveis ajudam as organizações a obter uma única fonte de verdade sobre o estoque disponível, especialmente durante o processo de processamento do pedido. Essa funcionalidade é útil para organizações nas quais existem as seguintes condições:

- A organização tem pelo menos dois sistemas diferentes que recebem pedidos de saída diretamente.
- A organização é muito rigorosa e deseja evitar reservas duplas de estoque de produtos, o que pode acontecer se vários sistemas conseguirem reservar em excesso o último item de estoque. Essa situação é evitada quando todos os sistemas de pedidos podem fazer chamadas instantâneas de API de reserva flexível para a Visibilidade de inventário, o que fornece uma única fonte de verdade sobre a disponibilidade de estoque.

[<img src="media/inventory-visibility-soft-reservation.png" alt="Inventory Visibility soft reservation." title="Reserva flexível do Visibilidade de estoque" width="720" />](media/inventory-visibility-soft-reservation.png)

A ilustração anterior mostra como funciona a reserva flexível e destaca as seguintes operações:

- Seu nível de estoque inicial é sincronizado com a Visibilidade de estoque do Microsoft Dynamics 365 Supply Chain Management.
- As reservas flexíveis são postadas de cada um de seus canais ou sistemas de pedidos para o Visibilidade de estoque. A Visibilidade do estoque valida a disponibilidade do estoque e tenta fazer uma reserva flexível. Se a reserva flexível for bem-sucedida, a Visibilidade do estoque adiciona à quantidade dessa reserva, deduz da quantidade disponível para reserva (AFR) e responde com um ID de reserva flexível.
- Neste momento, sua quantidade de estoque físico permanece a mesma.
- Você pode então sincronizar pedidos individuais ou agregados de reserva flexível (linhas de pedido) no Supply Chain Management para fazer reservas definitivas e liberar para o depósito ou atualizar a quantidade final de estoque.
- Você pode definir o sistema como [deslocar reservas flexíveis](#offset-scm) quando o estoque físico for atualizado no Supply Chain Management.

As reservas flexíveis geralmente são criadas, consumidas e canceladas usando chamadas de API para o serviço Visibilidade de Estoque.

> [!NOTE]
> Opcionalmente, você pode configurar o Supply Chain Management (e outros sistemas de terceiros) para compensar automaticamente a quantidade que foi reservada usando o Visibilidade de Estoque. A quantidade compensada é excluída dos registros de reserva no Visibilidade de Estoque.
>
> Por padrão, a função de deslocamento é ativada automaticamente quando você ativa o recurso de reserva flexível.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Ativar e configurar o recurso de reserva

Para ativar o recurso de reserva, siga estas etapas.

1. Entre no Power Apps e abra **Visibilidade do estoque**.
1. Abra a página **Configuração**.
1. Na guia **Gerenciamento de Recursos**, ative o recurso *OnHandReservation*.
1. Entre no ambiente Supply Chain Management.
1. Acesse o espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e habilite o recurso *Integração de Visibilidade de Estoque com compensação de reserva* (exige a versão 10.0.22 ou posterior).
1. Acesse **Gerenciamento de estoque \> Configuração \> Parâmetros de integração de Visibilidade de Estoque**, abra a guia **Compensação de reserva** e defina as seguintes configurações:

    - **Habilitar compensação de reserva** – Defina como *Sim* para habilitar essa funcionalidade.
    - **Modificador de deslocamento de reserva** – Selecione o status da transação de estoque que compensará as reservas feitas em Visibilidade de Estoque. Essa configuração determina a fase de processamento da ordem que dispara compensações. O estágio é rastreado pelo status de transação do estoque da ordem. Selecione um dos seguintes valores:

        - *Em ordem* — Ordens no status *Na transação* enviarão uma solicitação de compensação quando forem criadas. A quantidade de deslocamento será a quantidade da ordem criada (linha).
        - *Reserva* — Ordens no status *Reserva* enviarão uma solicitação de compensação quando forem reservadas por ordem ou reservadas fisicamente. Ao deslocar no status *Reserva*, a ordem enviará uma solicitação de deslocamento em qualquer novo status de estoque que esteja mais próximo da reservada coletada (por exemplo, coleta, guia de remessa postada ou faturada). Esse comportamento ocorre mesmo que você ignore a reserva no Supply Chain Management e prosseguir para outro status de estoque (por exemplo, se você pular da liberação para o depósito para coletar e embalar). A solicitação será acionada apenas uma vez. Se tiver sido acionada na coleta, ela não duplicará o deslocamento quando uma guia de remessa for postada. A quantidade deslocada será a mesma que a quantidade do status da transação de estoque quando o deslocamento foi acionado (em outras palavras, *Reservado pedido*/*Reserva física*, ou um status posterior, na linha de pedido correspondente).

1. Entre novamente no aplicativo Visibilidade de Estoque, vá para a página **Configuration** e, na guia **Reserva flexível**, revise a hierarquia de reserva flexível padrão. Adicione novas dimensões à hierarquia conforme necessário.
1. Na seção **Definir mapeamento de reserva flexível**, visualize as configurações padrão. Por padrão, as quantidades de estoque de reserva flexível serão registradas em relação à medida física `softreservephysical` da fonte de dados `iv`. A medida calculada *Disponível para reserva* é mapeada para `availabletoreserve`. Se você quiser atualizar a medida calculada `availabletoreserve`, vá para a página **Configuração** e, na guia **Medida calculada**, expanda e modifique a medida calculada.

Para obter mais informações, consulte [Configurar Visibilidade de Estoque](inventory-visibility-configuration.md).

> [!NOTE]
> A hierarquia de reservas descreve a sequência de dimensões que deve ser especificada quando as reservas são feitas. Isso funciona da mesma forma que a hierarquia de índice funciona para consultas disponíveis, mas é usado de forma independente para que os usuários possam especificar detalhes de dimensão para fazer reservas mais precisas.
>
> A hierarquia de reserva reversível deve conter `SiteId` e `LocationId` como componentes, pois eles constroem a configuração do Visibilidade de estoque.

Para obter mais informações sobre como configurar reservas, consulte [Configuração de reserva](inventory-visibility-configuration.md#reservation-configuration).

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Usar o recurso de reserva no Visibilidade de Estoque

Quando você chama a API de reserva, o sistema marca a reserva das mercadorias e quantidades especificadas.

Aqui está um cenário de exemplo e um corpo de consulta de API de amostra. A empresa Contoso vende o produto D0002 (Armário) em seu site de comércio eletrônico. Um cliente faz um pedido de venda de um pequeno armário vermelho por meio do site. A Contoso decide processar esse pedido usando as seguintes dimensões:

- ID da organização = usmf
- Site = 1
- Depósito = 11
- Produto = D0002
- Cor = vermelho
- Tamanho = pequeno

A Contoso já configurou uma conexão de API para Visibilidade de inventário de seu próprio sistema de comércio eletrônico. Quando a ordem é recebida, o sistema aciona instantaneamente uma chamada de API para fazer uma reserva flexível para o armário no Visibilidade de estoque.

### <a name="create-soft-reservations-using-the-reservation-api"></a>Criar reservas flexíveis usando a API de reserva

As reservas são feitas no serviço de Visibilidade de Estoque enviando uma solicitação POST para a URL do serviço, como `/api/environment/{environmentId}/onhand/reserve`.

Para uma reserva, o corpo da solicitação deve conter uma ID da organização, uma ID do produto, quantidades reservadas e dimensões.

Ao chamar a API de reserva, você pode controlar a validação da reserva especificando o parâmetro booliano `ifCheckAvailForReserv` no corpo da solicitação. Um valor `True` significa que a validação é necessária, enquanto um valor `False` significa que a validação não é necessária. O valor padrão é `True`.

Se você deseja cancelar uma reserva ou cancelar a reserva de quantidades de estoque especificadas, defina a quantidade como um valor negativo e defina o parâmetro `ifCheckAvailForReserv` como `False` para ignorar a validação.

Aqui está um exemplo do corpo da solicitação que faz referência ao pedido de venda no contexto anterior.

```json
# Url

#Replace {endpoint} with your system endpoint.
    {endpoint}/api/environment/{environmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "Testrequest-0005",
    "organizationId": "usmf",
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "softreservphysical",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

Uma solicitação de reserva flexível bem-sucedida retorna um *ID de reserva flexível* para cada registro de reserva. O ID de reserva flexível não é um identificador exclusivo para um registro de reserva flexível individual, mas uma combinação do ID do produto e dos valores de dimensão associados à solicitação de reserva flexível. Você pode registrar o ID de reserva flexível na linha do pedido ao sincronizar os pedidos reservados com sucesso para o Supply Chain Management ou outro sistema ERP para deslocamento.

### <a name="offset-soft-reservations-in-supply-chain-management"></a><a name="offset-scm"></a>Deslocar reservas flexíveis no Supply Chain Management

Você pode deslocar uma quantidade de reserva flexível após a quantidade em um pedido ser deduzida fisicamente no Supply Chain Management ou em outro sistema ERP. A Visibilidade de estoque oferece integração de deslocamento de reserva flexível pronta para uso com o Supply Chain Management.

Siga estas etapas para deslocar uma reserva flexível.

1. Entre no Supply Chain Management.
1. Vá para **Vendas e marketing \> Pedidos de venda \> Todos os pedidos de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Recrie o pedido de venda externo e adicione uma linha de vendas que use exatamente os mesmos valores de ID do produto, organização, local, depósito e dimensões.
1. Na guia rápida **Linhas de pedido de vendas**, selecione a linha de vendas que você acabou de inserir e, na barra de ferramentas, selecione **Estoque \> ID da reserva**.
1. Siga uma destas etapas:

    - Copie o ID da reserva flexível em sua resposta de solicitação de reserva flexível e cole-o no campo **ID da reserva**.
    - Deixe o campo **ID da reserva** em branco, mas marque a caixa de seleção **Compensação automática do serviço de estoque**. O sistema determinará automaticamente qual produto e as dimensões do produto deslocar, com base no ID do item e nos valores de dimensão inseridos na linha selecionada.

1. Selecione **OK**.
1. Enquanto a mesma linha de vendas ainda estiver selecionada, reserve fisicamente a quantidade pedida selecionando **Estoque \> Reserva** na barra de ferramentas da guia rápida **Linhas de pedido de vendas**.
1. Se você definiu anteriormente o campo **Modificador de deslocamento de reserva** como *Reservado*, o deslocamento será acionado quando a linha da ordem tiver o status *Reserva física* ou *Reserva solicitada*. Um trabalho em lote é executado uma vez por minuto para sincronizar as solicitações de deslocamento do Supply Chain Management para a Visibilidade de estoque.

> [!NOTE]
> Para status de transação que incluem um modificador de compensação de reserva especificado, a atualização da transação compensará o registro de reserva correspondente quando todas as seguintes condições forem atendidas:
>
> - A ID de reserva na transação de estoque corresponde à ID de reserva do registro de reserva no Visibilidade de Estoque.
> - As dimensões da transação de estoque correspondem às dimensões do registro de reserva no Visibilidade de Estoque.
> - Alterações no status da transação de estoque disparam compensações para reservas quando o status da transação de estoque reflete o fato de que um processo de ordem foi concluído ou ignorado.

As quantidades deslocadas seguem as quantidades de estoque especificadas nas transações de estoque relevantes. Um deslocamento terá efeito somente se a quantidade reservada permanecer na Visibilidade do Estoque.

### <a name="cancel-or-revert-a-soft-reservation"></a>Cancelar ou reverter uma reserva flexível

Se uma linha de ordem original for cancelada ou excluída e você precisar reverter a reserva flexível correspondente, publique uma quantidade negativa que tenha exatamente as mesmas informações no corpo da consulta da API.
