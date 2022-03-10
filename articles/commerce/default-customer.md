---
title: Criar um cliente padrão
description: Este tópico descreve como criar um cliente padrão para usar na criação de um canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ff9e5665ffd82982e09f63e34b30ae6937666231855587ad2f27c5231ead8419
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720950"
---
# <a name="create-a-default-customer"></a>Criar um cliente padrão

[!include [banner](includes/banner.md)]

Este tópico descreve como criar um cliente padrão para usar na criação de um canal no Microsoft Dynamics 365 Commerce.

Quando for criar um canal, você precisará fornecer um cliente padrão. É possível criar um cliente padrão facilmente após a criação do grupo de clientes e do catálogo de endereços do cliente.

## <a name="create-a-customer-group"></a>Criar um grupo de clientes

Se ainda não existe nenhum grupo de clientes, você pode criar um. Exemplos podem ser grupos para representar diferentes grupos de clientes, como atacado, varejo, Internet, funcionários etc.

Para criar um grupo de clientes, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Clientes \> Grupos de clientes**.
1. No painel de ação, selecione **Novo**.
1. Na caixa **Grupo de clientes**, insira uma ID de grupo de clientes.
1. Na caixa **Descrição**, insira uma descrição apropriada.
1. Na caixa **Condições de pagamento**, insira um valor apropriado.
1. Na caixa **Tempo entre a data de vencimento da fatura e a data de pagamento**, insira um valor apropriado.
1. Na caixa **Grupo de impostos padrão**, insira um grupo de impostos se aplicável.
1. Marque a caixa de seleção **Preços incluem imposto** se aplicável.
1. Na caixa **Motivo de baixa padrão**, insira um valor apropriado se aplicável.

A imagem a seguir mostra vários grupos de clientes configurados.

![Grupos de clientes.](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a>Criar um catálogo de endereços do cliente

Um cliente precisa estar associado a um catálogo de endereços. Caso um catálogo de endereços ainda não tenha sido criado, você precisará criar um.

Para criar um catálogo de endereços do cliente, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Configuração de canal \> Catálogos de Endereços**.
1. No painel de ação, selecione **Novo**.
1. Na caixa **Nome**, insira um nome.
1. Na caixa **Descrição**, insira uma descrição.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de catálogo de endereços.

![Catálogo de endereços.](media/address-book.png)

## <a name="create-a-default-customer"></a>Criar um cliente padrão

Para criar um cliente padrão, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Clientes \> Todos os clientes**.
1. No painel de ação, selecione **Novo**.
1. Na lista suspensa **Tipo**, selecione "Pessoa".
1. Na lista suspensa **Conta de cliente**, selecione ou insira um número de conta (por exemplo, "100001").
1. Na lista suspensa **Nome**, selecione ou insira um nome (por exemplo, "Padrão").
1. Na lista suspensa **Nome do meio**, selecione ou insira um nome (por exemplo, "Varejo").
1. Na lista suspensa **Sobrenome**, selecione ou insira um nome (por exemplo, "Cliente").
1. Na lista suspensa **Moeda**, selecione ou insira uma moeda (por exemplo, "USD").
1. Na lista suspensa **Moeda**, selecione o grupo de clientes criado anteriormente.
1. Na lista suspensa **Catálogos de endereços**, selecione um catálogo de endereços do cliente existente.
1. Selecione **Salvar** para salvar e voltar à tela de detalhes de cliente do novo cliente.

> [!NOTE]
> Não é necessário adicionar um endereço para um cliente padrão.

A imagem a seguir mostra um exemplo de criação de cliente.

![Criação de cliente padrão.](media/default-customer-creation.png)

A imagem a seguir mostra a configuração de um cliente padrão.

![Configuração de cliente de exemplo.](media/default-customer-configuration1.png)

A maioria dos valores padrão na tela de detalhes do cliente pode permanecer, mas dois valores devem ser alterados.

1. Na tela de detalhes do cliente, expanda **Padrões da ordem de venda**.
1. Na lista suspensa **Site**, selecione ou insira um site pré-configurado.
1. Na lista suspensa **Depósito**, selecione ou insira um depósito pré-configurado.

A imagem a seguir mostra um exemplo de configuração de cliente.

![Exemplo de configuração de cliente.](media/default-customer-configuration2.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
