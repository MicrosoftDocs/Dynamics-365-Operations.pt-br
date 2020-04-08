---
title: Habilitar ADLS em um ambiente do Dynamics 365 Commerce
description: Este tópico explica como habilitar e testar o Azure Data Lake Storage (ADLS) para um ambiente do Dynamics 365 Commerce, que é um pré-requisito para habilitar recomendações de produto.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c037f5603af5af84917084eefa1edd508891c0d
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154427"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a>Habilitar ADLS em um ambiente do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico explica como habilitar e testar o Azure Data Lake Storage (ADLS) para um ambiente do Dynamics 365 Commerce, que é um pré-requisito para habilitar recomendações de produto.

## <a name="overview"></a>Visão geral

Na solução Dynamics 365 Commerce, todas as informações de produto e de transação são rastreadas no Repositório de entidades do ambiente. Para tornar esses dados acessíveis a outros serviços do Dynamics 365, como análises de dados, Business Intelligence e recomendações personalizadas, é necessário conectar o ambiente a uma solução Azure Data Lake Storage Gen 2 (ADLS) de propriedade do cliente.

Como a ADLS é configurado em um ambiente, todos os dados necessários são espelhados do Repositório de entidades enquanto ainda estão sendo protegidos e sob controle do cliente.

Se as recomendações de produto ou personalizadas também forem habilitadas no ambiente, a pilha de recomendações de produto receberá acesso à pasta dedicada no ADLS para recuperar os dados do cliente e computar as recomendações com base nela.

## <a name="prerequisites"></a>Pré-requisitos

Os clientes precisam ter o ADLS configurado em uma assinatura do Azure que eles possuem. Este tópico não aborda a compra de uma assinatura do Azure nem a configuração de uma conta de armazenamento habilitada para o ADLS.

Para obter mais informações sobre o ADLS, consulte a [documentação oficial do ADLS](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Etapas da configuração

Esta seção aborda as etapas de configuração necessárias para habilitar o ADLS em um ambiente.

### <a name="enable-adls-in-the-environment"></a>Habilitar o ADLS no ambiente

1. Faça logon no portal do back office do ambiente.
1. Procure **Parâmetros do Sistema** e navegue até a guia **Conexões de dados**. 
1. Defina **Habilitar a integração do Data Lake** como **Sim**.
1. Defina **Fluxo para Atualizar Data Lake** como **Sim**.
1. Em seguida, insira as seguintes informações necessárias:
    1. **ID do Aplicativo** // **Segredo do Aplicativo** // **Nome DNS** - necessárias para se conectar ao KeyVault onde o segredo do ADLS está armazenado.
    1. **Nome do segredo** - o nome do segredo armazenado no KeyVault e usado para autenticação com o ADLS.
1. Salve as alterações no canto superior esquerdo da página.

A imagem a seguir mostra um exemplo de configuração do ADLS.

![Exemplo de configuração do ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a>Testar a conexão do ADLS

1. Teste a conexão com o KeyVault usando o link **Testar Azure Key Vault**.
1. Teste a conexão com o ADLS usando o link **Testar Armazenamento do Azure**.

> [!NOTE]
> Se os testes falharem, verifique novamente se todas as informações do KeyVault adicionadas acima estão corretas e tente novamente.

Depois que os testes de conexão forem bem-sucedidos, você deverá habilitar a atualização automática para o Repositório de entidades.

Para habilitar a atualização automática para o Repositório de entidades, siga estas etapas.

1. Procure **Repositório de entidades**.
1. Na lista à esquerda, navegue até a entrada **RetailSales** e selecione **Editar**.
1. Certifique-se de que **Atualização Automática Habilitada** esteja definida como **Sim**, selecione **Atualizar** e, em seguida, **Salvar**.

A imagem a seguir mostra um exemplo de Repositório de entidades com atualização automática habilitada.

![Exemplo de Repositório de entidades com atualização automática habilitada](./media/exampleADLSConfig2.png)

O ADLS agora está configurado para o ambiente. 

Caso ainda não tenha sido concluído, siga as etapas para [habilitar as recomendações e personalização do produto](enable-product-recommendations.md) para o ambiente.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de recomendações de produtos](product-recommendations.md)

[Habilitar recomendações de produtos](enable-product-recommendations.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Cancelar recomendações personalizados](personalization-gdpr.md)

[Adicionar recomendações de produtos no PDV](product.md)

[Adicionar recomendações à tela de transação](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)


