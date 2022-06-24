---
title: Habilitar recomendações de produtos personalizados
description: Este artigo descreve como disponibilizar recomendações de produtos personalizados para clientes no Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d2be5e59d51e183863da9c82d4ff733e830b8b69
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864855"
---
# <a name="enable-personalized-recommendations"></a>Habilitar recomendações personalizadas

[!include [banner](includes/banner.md)]

Este artigo descreve como disponibilizar recomendações de produtos personalizados para clientes no Microsoft Dynamics 365 Commerce.

No Dynamics 365 Commerce, os varejistas podem disponibilizar recomendações de produtos personalizados (também conhecidos como personalização). Dessa forma, as recomendações personalizadas podem ser incorporadas na experiência do cliente online e no PDV (ponto de venda). Quando a funcionalidade de personalização é ativada, o sistema pode associar as informações de compra e de produto de um usuário para gerar recomendações de produtos individualizadas.

## <a name="personalization-prerequisites"></a>Pré-requisitos de personalização

Antes de disponibilizar as recomendações de produto personalizadas para clientes, observe que há suporte apenas para os usuários comerciais que migraram o armazenamento para o Azure Data Lake Store. Antes que os clientes possam receber recomendações personalizadas sobre o produto, os varejistas devem [ativar as recomendações do produto](enable-product-recommendations.md).

> [!NOTE]
> Ativando as recomendações do produto, você também ativa a personalização. No entanto, se você desativar a personalização, não desativará os outros tipos de recomendações de produto.

Para obter mais informações sobre recomendações de produtos, consulte a [Visão geral das recomendações de produtos](product-recommendations.md)

## <a name="turn-on-personalization"></a>Ativar personalização

Para ativar a personalização, siga estas etapas.

1. Em Commerce headquarters, procure por **Gerenciamento de Recursos**.
1. Selecione **Tudo** para ver uma lista de recursos disponíveis. 
1. Na caixa de pesquisa, insira **Recomendações**.
1. Selecione o recurso **Recomendações personalizadas de produtos**.
1. No painel de propriedades **Recomendações personalizadas de produtos**, selecione **Habilitar agora**.

![Ativar personalização.](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> Quando você ativa a personalização, o processo de geração de listas personalizadas de recomendação de produtos é iniciado. Talvez seja necessário até um dia para que essas listas estejam disponíveis e visíveis online e no PDV.

## <a name="personalized-lists"></a>Listas personalizadas

Além de permitir a personalização de listas existentes geradas por máquina, o serviço de recomendações permite a personalização da experiência de descoberta de produtos online e no PDV.

Depois que a personalização é ativada, os varejistas podem mostrar as listas de clientes personalizados do comprador para as listas "online" ou "recomendável para o cliente" nos terminais de PDV. Além disso, os varejistas podem aplicar a personalização a listas de recomendações de produtos existentes e fornecer experiências de recusa GDPR (regulamentação geral de proteção de dados) para usuários autenticados. Se você desativar a personalização, também desative esses recursos.

### <a name="online-picks-for-you-lists"></a>Listas de "Seleções para você" online

Uma lista de "Seleções para você" é uma lista de aprendizado de máquina de inteligência artificial (AI-ML) que mostra a um usuário autenticado uma lista individualizada de produtos sugeridos. Essa lista se baseia no histórico de compras de omnicanal do usuário. As recomendações personalizadas são atualizadas dinamicamente à medida que o usuário faz mais compras. Esse tipo de lista também oferece suporte à filtragem de categorias, de forma que os varejistas possam mostrar as primeiras seleções, com base nas hierarquias de navegação.

Antes da lista "Seleções para você" aparecer em qualquer página de comércio eletrônico, os seguintes requisitos de usuário devem ser atendidos:

- Os usuários devem estar logados. Os usuários anônimos não verão recomendações personalizadas.
- Os usuários devem ter pelo menos uma compra na conta deles.
- Os usuários devem optar por receber recomendações personalizadas.

A ilustração a seguir mostra um exemplo de uma lista de "Seleções para você" em uma página de armazenamento online.

![Lista Seleções para você online.](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a>Listas "recomendadas para clientes" no PDV

Para aprimorar a experiência dos clientes, os varejistas podem personalizar páginas de detalhes de clientes existentes, adicionando uma lista contextual "Recomendado para o cliente".

A ilustração a seguir mostra um exemplo de uma lista de "Recomendado para o cliente" em um Terminal de PDV.

![Lista Recomendado para o cliente no PDV.](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a>Aplicar personalização a listas de recomendação existentes

Os varejistas podem aplicar a personalização a listas de recomendação existentes, como "Novo", "Tendência", "Mais vendidos", "As pessoas também gostam de" e "Frequentemente comprado junto". Quando a personalização é aplicada a listas existentes, os itens que um usuário conectado comprou anteriormente são removidos dessas listas. Para usuários anônimos e usuários que optaram por receber recomendações personalizadas, as versões padrão das listas existentes são mostradas. Portanto, os varejistas não precisam manter manualmente experiências de página separadas.

Por exemplo, um usuário conectado já comprou o relógio preto e as botas de trabalho marrom que aparecem na lista "Mais populares - padrão" da ilustração a seguir. Portanto, o usuário verá novos produtos em vez desses produtos, conforme mostrado na lista "Mais populares - personalizado".

![Aplicando personalização.](./media/applypersonalization.png)

Para aplicar a personalização a uma lista de recomendação existente no Commerce site builder, siga estas etapas.

1. Abra uma página existente do assistente para criação de sites que contenha um módulo de coleção de produtos.
1. No painel de navegação esquerdo, selecione o módulo de coleta de produtos.
1. No painel de navegação direito, em **Produtos**, selecione a lista.
1. Na caixa de diálogo **Selecionar configuração da lista de produtos**, em **Tipo**, selecione o tipo de lista.
1. Marque caixa de seleção **Aplicar Personalização** e selecione **OK**.

    ![Aplicando personalização a uma lista de tendências.](./media/ApplyPersonalizationToTrending.PNG)

1. Salve a página, termine de editá-la e publique-a. Depois que a página for publicada, os usuários conectados verão listas de tendências personalizadas.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações de produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações de produtos](enable-product-recommendations.md)

[Habilitar recomendações de "comprar looks semelhantes"](shop-similar-looks.md)

[Cancelar recomendações personalizadas](personalization-gdpr.md)

[Adicionar recomendações de produtos no PDV](product.md)

[Adicionar recomendações à tela de transação](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
