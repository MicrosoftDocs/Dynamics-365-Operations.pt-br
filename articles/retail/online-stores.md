---
title: "Visão geral da loja online"
description: "Este artigo oferece informações sobre lojas online de Varejo e como configurá-las no Microsoft Dynamics 365 for Retail."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16161
ms.assetid: 646d560c-f856-4701-b4ca-44e357ef09b8
ms.search.region: Global
ms.search.industry: Retail
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 13d7f99766dabf35b80e7100a3017308033e3da6
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="online-store-overview"></a>Visão geral de loja online

[!include[banner](includes/banner.md)]


Este artigo oferece informações sobre lojas online de Varejo e como configurá-las no Microsoft Dynamics 365 for Retail.

O Dynamics 365 for Retail dá suporte a vários canais de varejo. Esses canais de varejo incluem lojas online, call centers e lojas de varejo (também chamadas de lojas tradicionais). As lojas online oferecem ao varejista uma presença online, de modo que os clientes possam comprar produtos na loja online do varejista, bem como nas suas lojas físicas. Se os clientes comprarem produtos da loja online, esses produtos podem ser enviados para eles ou os clientes podem retirar os produtos em uma loja de varejo local. Crie uma loja online no cliente do Dynamics 365 for Retail. Esta loja online é publicada em uma loja online de terceiros que é integrada ao Dynamics 365 for Retail. A loja online de terceiros serve como uma vitrine (interface do usuário) da loja online e fornece uma opção do sistema de gerenciamento do cliente (CMS) e recursos da interface do usuário. Várias integrações deste tipo estão disponíveis no Dynamics 365 for Retail. As propriedades definidas para a loja online controlam o comportamento da loja online. Por exemplo, você define a hierarquia de categoria de navegação no Dynamics 365 for Retail e a atribui para a loja online. Quando você publica a loja online em uma loja online de terceiros, a hierarquia da categoria de navegação aparece na versão online da loja. Os clientes usam a hierarquia de categoria de navegação para pesquisar a loja online e para procurar produtos. Para criar uma loja online, você deve configurar os componentes que permitem que as transações sejam processadas para a loja. Por exemplo, você deve adicionar classificações, aplicar atributos e configurar métodos de pagamento e métodos de remessa. Você também pode definir preços, promoções, descontos, contratos comerciais e condições de remessa específicos da loja online. Depois que publicar a loja online na loja online de terceiros, você poderá criar catálogos de produtos de varejo para a loja online. Os produtos do catálogo se transformam em listagens de produtos na loja online. Quando um cliente compra produtos da loja online, o estoque disponível é atualizado e sincronizado no cliente. Além de isso, as ordens de venda são geradas para as compras e enviadas ao cliente para preenchimento e processamento.

## <a name="set-up-an-online-store"></a>Configurar uma loja online
Para configurar uma loja online, você deve concluir as seguintes tarefas.

1.  Crie a loja online.
2.  Adicione a loja online às hierarquias apropriadas da organização.
3.  Adicione classificações que incluem os produtos disponíveis na loja online.
4.  Atribua ou crie grupos de preços para a loja online.
5.  Configure os modos de entrega disponíveis para a loja online.
6.  Atribua os métodos de pagamento aceitos pela loja online.
7.  Se você permite que os compradores façam pedidos de produtos online e os retirem em uma loja local, atribua grupos de localizadores de loja à loja online.
8.  Atribua atributos de canais, produtos e ordens de venda à loja online. Os atributos do canal se aplicam a toda a loja online, os atributos de produtos se aplicam aos produtos oferecidos na loja online e os atributos da ordem de venda se aplicam às ordens de venda geradas na loja online.
9.  Mapeie atributos para definir as propriedades que determinam como esses atributos se comportam na loja online. Por exemplo, os atributos podem ser definidos como obrigatórios ou pesquisáveis.
10. Publique a loja online para gerar a estrutura da loja na opção de loja online de terceiros. **Importante:** Antes de publicar na loja online você deve configurar uma localização de distribuição para ela.

## <a name="retail-channel-navigation-hierarchies"></a>Hierarquias de navegação de canal de varejo
Antes de criar uma loja online, você deve definir a hierarquia de navegação de canal de varejo que deseja usar para ela. A hierarquia de navegação de canal de varejo representa a hierarquia de categoria exibida na loja online depois que ela é publicada. Quando você publica catálogos de produtos de varejo na loja online, os produtos do catálogo são mapeados para as categorias na hierarquia de navegação de canal de varejo. Os clientes então usam a hierarquia para navegar na loja online.

## <a name="organization-hierarchies"></a>Hierarquias da organização
As hierarquias da organização são usadas para estruturar canais de varejo. As hierarquias da organização representam os relacionamentos entre as organizações que compõem sua empresa. Ao configurar lojas online, você pode adicioná-las a uma hierarquia da organização. Então, as lojas compartilham os dados usados para classificações, reabastecimento e relatórios. Ao criar uma hierarquia da organização, você atribui uma finalidade a ela. A finalidade indica como a hierarquia é usada na estrutura de negócios. Você pode criar uma hierarquia da organização para as operações da sua loja, e usar essa hierarquia para classificações, reabastecimento e relatórios. Como alternativa, você pode criar uma hierarquia da organização separada para cada finalidade. Você também pode criar várias hierarquias com a mesma finalidade e atribuir um canal separado a cada uma delas. Se você pretende publicar catálogos de produtos de varejo na loja online, deve, no mínimo, adicionar a loja online a uma hierarquia da organização para classificações. Os produtos de um catálogo são selecionados das classificações atribuídas à loja online. Quando o catálogo é publicado, o processo de publicação compara as datas efetivas da classificação atribuída à loja online com os produtos incluídos no catálogo para determinar quais produtos devem ser disponibilizados na loja online.




