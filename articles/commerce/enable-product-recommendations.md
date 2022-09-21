---
title: Habilitar recomendações de produtos
description: Este artigo explica como fazer recomendações de produto com base na inteligência artificial-aprendizado de máquina (AI-ML) disponível para clientes do Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fc1b43fa70e6652d38b1141e2d93cf323f70a756
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460012"
---
# <a name="enable-product-recommendations"></a>Habilitar recomendações de produtos

[!include [banner](includes/banner.md)]

Este artigo explica como fazer recomendações de produto com base na inteligência artificial-aprendizado de máquina (AI-ML) disponível para clientes do Microsoft Dynamics 365 Commerce. Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)

## <a name="recommendations-pre-check"></a>Recomendações de pré-verificação

1. Verifique se você tem uma licença de Recomendações válida do Dynamics 365 Commerce.
1. Verifique se o Repositório de entidades está conectado a uma conta do Azure Data Lake Storage Gen2 de propriedade do cliente. Para obter mais informações, consulte [Verificar se o Azure Data Lake Storage foi comprado e verificado com êxito no ambiente](enable-ADLS-environment.md).
1. Confirme se a configuração da entidade Azure AD contém uma entrada para Recomendações. Veja a seguir mais informações sobre como executar essa ação.
1. Verifique se a atualização diária do Repositório de entidades para o Azure Data Lake Storage Gen2 foi agendada. Para obter mais informações, consulte [Garantir se a atualização do armazenamento de entidade foi automatizada](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
1. Habilite as medidas de RetailSale para o Repositório de entidades. Para obter mais informações sobre a configuração deste processo, consulte [Trabalhar com medidas](/dynamics365/ai/customer-insights/pm-measures).
1. Verifique se o seu ambiente configurou as regiões de fornecimento e preparação nas regiões com suporte no momento, da seguinte maneira:

    - **Regiões de preparação com suporte:** UE/EUA/CA/AU.
    - **Regiões de fornecimento com suporte:** UE/EUA/CA/AU. Se a região de servidor não corresponder a uma das regiões com suporte existentes, o serviço de recomendações selecionará a região de serviços mais próxima aceita.

Depois que as etapas acima tiverem sido concluídas, você estará pronto para habilitar as recomendações.

> [!NOTE]
> Há um problema conhecido em que as recomendações não aparecem após a conclusão das etapas a seguir. Esse problema é causado por problemas de fluxo de dados no ambiente. Se o seu ambiente não mostrar resultados de recomendação, configure os dados alternativos para o serviço de recomendações seguindo as etapas em [Configurar um fluxo de informações alternativo para recomendações](set-up-alternate-data-flow.md). Você deve ter permissões de administrador do Azure para concluir estas etapas. Se precisar de ajuda, contate o representante da FastTrack.

## <a name="azure-ad-identity-configuration"></a>Configuração de identidade do Azure AD

Essa etapa só é necessária para clientes que executam uma configuração de infraestrutura como um serviço (IaaS). A configuração de identidade do Azure AD é automática para clientes que executam o Azure Service Fabric, mas recomendamos verificar se a configuração está definida como esperado.

### <a name="setup"></a>Configurar

1. No Commerce headquarters, procure a página **Aplicativos do Azure Active Directory**.
1. Verifique se existe uma entrada para **RecommendationSystemApplication-1**. Se a entrada não existir, crie uma usando as seguintes informações:

    - **ID do Cliente**: d37b07e8-dd1c-4514-835d-8b918e6f9727
    - **Nome**: RecommendationSystemApplication-1
    - **ID do usuário**: RetailServiceAccount

1. Salve e feche a página. 

## <a name="turn-on-recommendations"></a>Ative as recomendações

Para ativar as recomendações de produtos, siga estas etapas.

1. Em Commerce headquarters, procure por **Gerenciamento de Recursos**.
1. Selecione **Tudo** para ver uma lista de recursos disponíveis. 
1. Na caixa de pesquisa, insira **Recomendações**.
1. Selecione o recurso **Recomendações de produtos**.
1. No painel de propriedades **Recomendações de produtos**, selecione **Habilitar agora**.

![Ativando as recomendações.](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> - O procedimento acima inicia o processo de geração de listas recomendação de produto. Pode levar várias horas antes que as listas estejam disponíveis e possam ser vistas no ponto de venda (PDV) ou em Dynamics 365 Commerce.
> - Essa configuração não habilita todos os recursos de recomendações. Os recursos avançados, como as recomendações personalizadas, "comprar itens semelhantes" e "comprar por descrição semelhante", são controlados por entradas de gerenciamento de recursos dedicados. Para obter informações sobre como habilitar esses recursos no Commerce headquarters, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md), [Habilitar recomendações "comprar itens semelhantes"](shop-similar-looks.md) e [Habilitar recomendações "comprar por descrição semelhante"](shop-similar-description.md).

## <a name="configure-recommendation-list-parameters"></a>Configurar parâmetros da lista de recomendação

Por padrão, a lista de recomendação de produtos baseada em AI-ML fornece valores sugeridos. Você pode alterar os valores sugeridos padrão para se adequar ao fluxo de seus negócios. Para saber mais sobre como alterar os parâmetros padrão, acesse [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).

## <a name="include-recommendations-in-e-commerce-experiences"></a>Incluir recomendações em experiências de comércio eletrônico

Depois de habilitar recomendações no Commerce headquarters, os módulos do Commerce usados para exibir os resultados de recomendações para as experiências de comércio eletrônico estão prontos para serem configurados. Para obter mais informações, consulte [Módulos de coleção de produtos](product-collection-module-overview.md).

## <a name="show-recommendations-on-pos-devices"></a>Mostrar recomendações em dispositivos POS

Após habilitar recomendações no Commerce headquarters, o painel de recomendações deverá ser adicionado à tela PDV de controle por meio da ferramenta de layout. Para saber mais sobre esse processo, consulte [Adicionar um controle de recomendações à tela de transações em dispositivos de PDV](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Habilitar recomendações personalizadas

No Dynamics 365 Commerce, os varejistas podem disponibilizar recomendações de produtos personalizados (também conhecidos como personalização). Dessa forma, as recomendações personalizadas podem ser incorporadas na experiência do cliente online e no ponto de venda. Quando a funcionalidade de personalização é ativada, o sistema pode associar as informações de compra e de produto de um usuário para gerar recomendações de produtos individualizadas.

Para saber mais sobre recomendações personalizadas, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações de produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Configurar um fluxo de dados alternativo para recomendações](set-up-alternate-data-flow.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Habilitar recomendações de "comprar itens semelhantes"](shop-similar-looks.md)

[Cancelar recomendações personalizadas](personalization-gdpr.md)

[Adicionar recomendações de produtos no PDV](product.md)

[Adicionar recomendações à tela de transação](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]
