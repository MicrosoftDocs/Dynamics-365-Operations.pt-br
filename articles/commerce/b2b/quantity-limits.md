---
title: Definir limites de quantidade de produtos para sites de comércio eletrônico entre empresas
description: Este artigo descreve como definir os limites da quantidade de produtos para sites de comércio eletrônico B2B.
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: 76a7ad2c3095d1402ff214dbfee26b344b492681
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275668"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a>Definir limites de quantidade de produtos para sites de comércio eletrônico entre empresas

[!include [banner](../../includes/banner.md)]

Este artigo descreve como definir os limites da quantidade de produtos para sites de comércio eletrônico B2B.

A maioria dos produtos tem uma unidade de medida que define seu agrupamento. O agrupamento afeta a forma como os produtos podem ser vendidos. Alguns produtos podem ter um agrupamento adicional para quantidades. Esse agrupamento determina se os produtos podem ser vendidos como unidades individuais ou múltiplos e se há um limite mínimo ou máximo de quantidade de ordens que deve ser seguido.

O recurso de limitação de quantidade garante que as quantidades mínimas, máximas, múltiplas e padrão que são configuradas no Microsoft Dynamics 365 Commerce (nas configurações de ordem padrão ou configurações do site criador do Commerce) sejam aplicadas às ordens de cliente realizadas em um site de comércio eletrônico. No momento, não há suporte para os limites de quantidade do produto para o ponto de venda (POS) e call centers.

Muitos revendedores fornecem a opção de ordens de cliente (também conhecidas como ordens especiais) para atender a vários requisitos de produto e atendimento. Estes são alguns dos cenários típicos:

- Um cliente quer que produtos de variantes específicas sejam vendidos em grupos de poucas unidades.
- Um cliente deseja retirar produtos de uma loja ou local que é diferente da loja ou local no qual ele comprou esses produtos. No entanto, os padrões de embalagem para os armazenamentos são diferentes dos padrões de embalagem para distribuição de vendas online.
- Um cliente quer comprar um produto de edição limitada que tem uma quantidade máxima de itens que podem ser comprados.

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a>Ativar o recurso de configurações de ordem padrão no Commerce headquarters

Para poder definir limites de quantidade do produto, o recurso de configurações de ordem padrão deve ser ativado no Commerce headquarters.

Siga estas etapas para ativar o recurso de configurações de ordem padrão.

1. Acesse **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.
1. Localize e selecione o recurso **Suporte às configurações de ordem do site e padrão na ordem de cliente**.
1. Na parte inferior do painel à direita, selecione **Ativar agora**. 

## <a name="define-quantity-settings"></a>Definir configurações de quantidade 

Você pode definir as configurações de quantidade na página **Configurações de ordem padrão**.

Para definir as configurações de ordem, siga estas etapas. 

1. Acesse Produto **Retail e Commerce \> Produtos e categorias \> Produtos liberados por categoria**.
1. Selecione um produto liberado.
1. No Painel de ações da guia **Gerenciar estoque**, no grupo **Configurações da ordem**, selecione **Configurações padrão da ordem**. 
1. Na página **Configurações de ordem padrão**, na guia rápida **Ordem de venda**, na seção **Quantidade de venda**, defina as quantidades de vendas do produto:

    - **Múltiplos** – A quantidade em que o produto pode ser comprado em múltiplos.
    - **Quantidade mínima da ordem** – O número mínimo de produtos que devem ser comprados.
    - **Quantidade máximo da ordem** – O número máximo de produtos que podem ser comprados.
    - **Quantidade de ordem padrão** – A quantidade padrão que é inserida automaticamente quando o produto é selecionado.

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a>Ativar o recurso de limites de quantidade da ordem B2B no criador de sites do Commerce

Para ativar o recurso de limites de quantidade da ordem B2B no criador de sites do Commerce, siga estas etapas.

1. Acesse **Configurações do site \> Extensões**
1. Em **Habilitar limites de quantidade da ordem**, selecione **Habilitado para clientes B2B** no menu suspenso. 

> [!NOTE] 
> As configurações atualizadas do construtor de sites terão efeito somente depois que o arquivo app.settings.json for atualizado. Para obter mais informações, consulte [SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um site de comércio eletrônico B2B](set-up-b2b-site.md)

[Gerenciar parceiros de negócios B2B usando hierarquias do cliente](partners-customer-hierarchies.md)

[Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B](manage-b2b-users.md)

[Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
