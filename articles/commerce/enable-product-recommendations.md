---
title: Habilitar recomendações de produtos
description: Este tópico explica como fazer recomendações de produto com base na inteligência artificial-aprendizado de máquina (AI-ML) disponível para clientes do Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/18/2020
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
ms.openlocfilehash: 873266405638cd277eb748ad7e966ba8a4976b13
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019850"
---
# <a name="enable-product-recommendations"></a>Habilitar recomendações de produtos

[!include [banner](includes/banner.md)]

Este tópico explica como fazer recomendações de produto com base na inteligência artificial-aprendizado de máquina (AI-ML) disponível para clientes do Microsoft Dynamics 365 Commerce. Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)

## <a name="recommendations-pre-check"></a>Recomendações de pré-verificação

Antes de habilitar, observe que as recomendações de produto têm suporte apenas para clientes do Commerce que migraram o armazenamento para usar o Azure Data Lake Storage. 

As configurações a seguir devem ser habilitadas no back office antes da habilitação das recomendações:

1. Verifique se o Azure Data Lake Storage foi comprado e verificado com êxito no ambiente. Para obter mais informações, consulte [Verificar se o Azure Data Lake Storage foi comprado e verificado com êxito no ambiente](enable-ADLS-environment.md).
2. Verifique se a atualização do armazenamento de entidade foi automatizada. Para obter mais informações, consulte [Garantir se a atualização do armazenamento de entidade foi automatizada](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
3. Confirme se a configuração da entidade Azure AD contém uma entrada para Recomendações. Veja a seguir mais informações sobre como executar essa ação.

Adicionalmente, verifique se as medições do RetailSale estão habilitadas. Para saber mais sobre este processo de configuração, consulte [Trabalhar com medidas](/dynamics365/ai/customer-insights/pm-measures).

## <a name="azure-ad-identity-configuration"></a>Configuração de identidade do Azure AD

Essa etapa é necessária para todos os clientes que executam uma configuração de infraestrutura como um serviço (IaaS). Para clientes em execução na Service Fabric (IT), essa etapa deve ser automática e recomendamos verificar se a configuração está definida como esperado.

### <a name="setup"></a>Instalação

1. No back office, procure a página **Aplicativos do Azure Active Directory**.
2. Verifique se existe uma entrada para "RecommendationSystemApplication-1".

Se a entrada não existir, adicione uma nova entrada com as seguintes informações:

- **ID do cliente** - d37b07e8-dd1c-4514-835d-8b918e6f9727
- **Nome** - RecommendationSystemApplication-1
- **ID do usuário** - RetailServiceAccount

Salve e feche a página. 

## <a name="turn-on-recommendations"></a>Ative as recomendações

Para ativar as recomendações de produtos, siga estas etapas.

1. Em Commerce headquarters, procure por **Gerenciamento de Recursos**.
1. Selecione **Tudo** para ver uma lista de recursos disponíveis. 
1. Na caixa de pesquisa, insira **Recomendações**.
1. Selecione o recurso **Recomendações de produtos**.
1. No painel de propriedades **Recomendações de produtos**, selecione **Habilitar agora**.

![Ativando as recomendações](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> Este procedimento inicia o processo de geração de listas recomendação de produto. Pode levar várias horas antes que as listas estejam disponíveis e possam ser vistas no ponto de venda (PDV) ou em Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configurar parâmetros da lista de recomendação

Por padrão, a lista de recomendação de produtos baseada em AI-ML fornece valores sugeridos. Você pode alterar os valores sugeridos padrão para se adequar ao fluxo de seus negócios. Para saber mais sobre como alterar os parâmetros padrão, acesse [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Mostrar recomendações em dispositivos POS

Após habilitar recomendações no back office do Commerce, o painel de recomendações deverá ser adicionado à tela PDV de controle por meio da ferramenta de layout. Para saber mais sobre esse processo, consulte [Adicionar um controle de recomendações à tela de transações em dispositivos de PDV](add-recommendations-control-pos-screen.md). 

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