---
title: Módulo de informações sobre retirada
description: Este tópico aborda o módulo de informações sobre retirada e descreve como adicioná-lo às páginas de finalização de compra no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 61b97d72b6a397737c10476cd6c02764e60f10b1
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665339"
---
# <a name="pickup-information-module"></a>Módulo de informações sobre retirada

[!include [banner](includes/banner.md)]

Este tópico aborda o módulo de informações sobre retirada e descreve como adicioná-lo às páginas de finalização de compra no Microsoft Dynamics 365 Commerce.

O módulo de informações sobre retirada pode ser usado em um módulo de finalização de compra para mostrar informações sobre retirada de ordens. Os clientes podem ver as datas de retirada e os intervalos de tempo disponíveis e, em seguida, selecionar um horário adequado para retirar a ordem. Por exemplo, um cliente pode optar por retirar uma ordem às 15h em 21 de março na loja de São Francisco.

Os intervalos de tempo de retirada para as lojas apropriadas devem ser configurados na sede do Commerce. Para obter mais informações, consulte [Criar e atualizar os intervalos de tempo para retirada pelo cliente](dev-itpro/pickup-timeslots.md).

Se um módulo de informações sobre retirada for criado em uma página de finalização de compra, mas nenhum intervalo de tempo for definido para a loja selecionada para retirada, o módulo mostrará informações, mas o usuário não poderá selecionar nenhum intervalo de tempo. Os intervalos de tempo são opcionais e não são necessários para realizar uma ordem.

Se vários itens forem selecionados para retirada em várias lojas, o módulo de informações sobre retirada permitirá que o usuário selecione um intervalo de tempo para cada loja, desde que os intervalos de tempo estejam disponíveis nela.

> [!NOTE]
> O suporte para os intervalos de tempo e o módulo de informações sobre retirada de finalização de compra está disponível no Dynamics 365 Commerce versão 10.0.15 e posteriores.

A ilustração a seguir mostra um exemplo de seleção de intervalo de tempo por meio do módulo de informações sobre retirada em uma página de finalização de compra.

![Exemplo de um módulo de informações sobre retirada em uma página de finalização de compra](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a>Propriedades do módulo

- **Título** – Insira um título para o módulo.

## <a name="show-time-slot-information-after-an-order-is-placed"></a>Mostrar informações do intervalo de tempo após uma ordem ser realizada

Após uma ordem ser realizada, as informações sobre o intervalo de tempo selecionado poderão ser exibidas no [módulo de confirmação da ordem](order-confirmation-module.md) e no [módulo de detalhes da ordem](account-management.md#order-details-page). Esses dois módulos têm uma propriedade **Mostrar informações do intervalo de tempo**. Para que eles possam mostrar o intervalo de tempo selecionado durante o processo da ordem, essa propriedade deve ser definida como **Verdadeiro**.

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a>Adicionar um módulo de informações sobre retirada de finalização de compra a uma página

Para obter instruções sobre como adicionar um módulo de informações sobre retirada a uma página de finalização de compra e definir as propriedades necessárias, consulte [Módulo de finalização de compra](add-checkout-module.md).

A ilustração a seguir mostra um exemplo de uma página de finalização de compra no comércio eletrônico que inclui intervalos de tempo para itens da linha de retirada.

![Exemplo de uma página de finalização de compra no comércio eletrônico que inclui intervalos de tempo para itens da linha de retirada](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a>Recursos adicionais

[Criar e atualizar os intervalos de tempo para retirada pelo cliente](dev-itpro/pickup-timeslots.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de detalhes da ordem](account-management.md)
