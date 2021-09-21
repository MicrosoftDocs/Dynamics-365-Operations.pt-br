---
title: Habilitar recomendações de produtos
description: Este tópico explica como fazer recomendações de produto com base na inteligência artificial-aprendizado de máquina (AI-ML) disponível para clientes do Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/31/2021
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
ms.openlocfilehash: 4a7be82b3a40aba621693f080ff41767fdaea474
ms.sourcegitcommit: 98061a5d096ff4b9078d1849e2ce6dd7116408d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466307"
---
# <a name="enable-product-recommendations"></a>Habilitar recomendações de produtos

[!include [banner](includes/banner.md)]

Este tópico explica como fazer recomendações de produto com base na inteligência artificial-aprendizado de máquina (AI-ML) disponível para clientes do Microsoft Dynamics 365 Commerce. Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)

## <a name="recommendations-pre-check"></a>Recomendações de pré-verificação

1. Verifique se você tem uma licença de Recomendações válida do Dynamics 365 Commerce.
1. Verifique se o Repositório de entidades está conectado a uma conta do Azure Data Lake Storage Gen2 de propriedade do cliente. Para obter mais informações, consulte [Verificar se o Azure Data Lake Storage foi comprado e verificado com êxito no ambiente](enable-ADLS-environment.md).
1. Confirme se a configuração da entidade Azure AD contém uma entrada para Recomendações. Veja a seguir mais informações sobre como executar essa ação.
1. Verifique se a atualização diária do Repositório de entidades para o Azure Data Lake Storage Gen2 foi agendada. Para obter mais informações, consulte [Garantir se a atualização do armazenamento de entidade foi automatizada](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
1. Habilite as medidas de RetailSale para o Repositório de entidades. Para obter mais informações sobre a configuração deste processo, consulte [Trabalhar com medidas](/dynamics365/ai/customer-insights/pm-measures).

Depois que as etapas acima tiverem sido concluídas, você estará pronto para habilitar as recomendações.

## <a name="azure-ad-identity-configuration"></a>Configuração de identidade do Azure AD

Essa etapa é necessária apenas para clientes que executam uma configuração de infraestrutura como um serviço (IaaS). A configuração de identidade do Azure AD é automática para clientes que executam o Azure Service Fabric, mas é recomendável verificar se a configuração está definida como esperado.

### <a name="setup"></a>Configurar

1. Na matriz do Commerce, procure a página **Aplicativos do Azure Active Directory**.
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
> - Essa configuração não habilita todos os recursos de recomendações. Os recursos avançados, como as recomendações personalizadas, "comprar itens semelhantes" e "comprar por descrição semelhante", são controlados por entradas de gerenciamento de recursos dedicados. Para obter informações sobre como habilitar esses recursos na matriz do Commerce, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md), [Habilitar recomendações "comprar itens semelhantes"](shop-similar-looks.md) e [Habilitar recomendações "comprar por descrição semelhante"](shop-similar-description.md).

## <a name="configure-recommendation-list-parameters"></a>Configurar parâmetros da lista de recomendação

Por padrão, a lista de recomendação de produtos baseada em AI-ML fornece valores sugeridos. Você pode alterar os valores sugeridos padrão para se adequar ao fluxo de seus negócios. Para saber mais sobre como alterar os parâmetros padrão, acesse [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).

## <a name="include-recommendations-in-e-commerce-experiences"></a>Incluir recomendações em experiências de comércio eletrônico

Depois de habilitar recomendações na matriz do Commerce, os módulos do Commerce usados para exibir os resultados de recomendações para as experiências de comércio eletrônico estão prontos para serem configurados. Para obter mais informações, consulte [Módulos de coleção de produtos](product-collection-module-overview.md).

## <a name="show-recommendations-on-pos-devices"></a>Mostrar recomendações em dispositivos POS

Após habilitar recomendações na matriz do Commerce, o painel de recomendações deverá ser adicionado à tela PDV de controle por meio da ferramenta de layout. Para saber mais sobre esse processo, consulte [Adicionar um controle de recomendações à tela de transações em dispositivos de PDV](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Habilitar recomendações personalizadas

No Dynamics 365 Commerce, os varejistas podem disponibilizar recomendações de produtos personalizados (também conhecidos como personalização). Dessa forma, as recomendações personalizadas podem ser incorporadas na experiência do cliente online e no ponto de venda. Quando a funcionalidade de personalização é ativada, o sistema pode associar as informações de compra e de produto de um usuário para gerar recomendações de produtos individualizadas.

Para saber mais sobre recomendações personalizadas, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações dos produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Habilitar recomendações de "comprar looks semelhantes"](shop-similar-looks.md)

[Cancelar recomendações personalizadas](personalization-gdpr.md)

[Adicionar recomendações de produtos no PDV](product.md)

[Adicionar recomendações à tela de transação](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
