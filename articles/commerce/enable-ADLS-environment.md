---
title: Habilitar o Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce
description: Este tópico explica como habilitar e testar o Azure Data Lake Storage para um ambiente do Dynamics 365 Commerce, que é um pré-requisito para habilitar recomendações de produto.
author: bebeale
ms.date: 04/13/2020
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
ms.openlocfilehash: 61f96dae0643e3383afd91864e4c145f3b5c04c8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792598"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Habilitar o Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico explica como habilitar e testar o Azure Data Lake Storage para um ambiente do Dynamics 365 Commerce, que é um pré-requisito para habilitar recomendações de produto.

Na solução Dynamics 365 Commerce, todas as informações de produto e de transação são rastreadas no Repositório de entidades do ambiente. Para tornar esses dados acessíveis a outros serviços do Dynamics 365, como análises de dados, business intelligence e recomendações personalizadas, é necessário conectar o ambiente a uma solução Azure Data Lake Storage Gen 2 de propriedade do cliente.

Como o Azure Data Lake Storage é configurado em um ambiente, todos os dados necessários são espelhados do Repositório de entidades e estão protegidos e sob controle do cliente.

Se as recomendações de produto ou personalizadas também forem habilitadas no ambiente, a pilha de recomendações de produto receberá acesso à pasta dedicada no Azure Data Lake Storage para recuperar os dados do cliente e computar as recomendações com base nela.

## <a name="prerequisites"></a>Pré-requisitos

Os clientes precisam ter o Azure Data Lake Storage configurado em uma assinatura do Azure de propriedade deles. Este tópico não aborda a compra de uma assinatura do Azure nem a configuração de uma conta de armazenamento habilitada para o Azure Data Lake Storage.

Para obter mais informações sobre o Azure Data Lake Storage, consulte a [documentação oficial do Azure Data Lake Storage Gen2](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Etapas da configuração

Esta seção aborda as etapas de configuração necessárias para habilitar o Azure Data Lake Storage em um ambiente conforme ele se relaciona com recomendações do produto.
Para obter uma visão geral mais detalhada das etapas necessárias para habilitar o Azure Data Lake Storage, consulte [Disponibilizar o repositório de entidades como um Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Habilitar o Azure Data Lake Storage no ambiente

1. Faça logon no portal do back office do ambiente.
1. Procure **Parâmetros do Sistema** e navegue até a guia **Conexões de dados**. 
1. Defina **Habilitar a integração do Data Lake** como **Sim**.
1. Defina **Fluxo para Atualizar Data Lake** como **Sim**.
1. Em seguida, insira as seguintes informações necessárias:
    1. **ID do Aplicativo** // **Segredo do Aplicativo** // **Nome DNS** - necessárias para se conectar ao KeyVault onde o segredo do Azure Data Lake Storage está armazenado.
    1. **Nome do segredo** - o nome do segredo armazenado no KeyVault e usado para autenticação com o Azure Data Lake Storage.
1. Salve as alterações no canto superior esquerdo da página.

A imagem a seguir mostra um exemplo de configuração do Azure Data Lake Storage.

![Exemplo de configuração do Azure Data Lake Storage](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Testar a conexão do Azure Data Lake Storage

1. Teste a conexão com o KeyVault usando o link **Testar Azure Key Vault**.
1. Teste a conexão com o Azure Data Lake Storage usando o link **Testar Armazenamento do Azure**.

> [!NOTE]
> Se os testes falharem, verifique novamente se todas as informações do KeyVault adicionadas acima estão corretas e tente novamente.

Depois que os testes de conexão forem bem-sucedidos, você deverá habilitar a atualização automática para o Repositório de entidades.

Para habilitar a atualização automática para o Repositório de entidades, siga estas etapas.

1. Procure **Repositório de entidades**.
1. Na lista à esquerda, navegue até a entrada **RetailSales** e selecione **Editar**.
1. Certifique-se de que **Atualização Automática Habilitada** esteja definida como **Sim**, selecione **Atualizar** e, em seguida, **Salvar**.

A imagem a seguir mostra um exemplo de Repositório de entidades com atualização automática habilitada.

![Exemplo de Repositório de entidades com atualização automática habilitada](./media/exampleADLSConfig2.png)

O Azure Data Lake Storage agora está configurado para o ambiente. 

Caso ainda não tenha sido concluído, siga as etapas para [habilitar as recomendações e personalização do produto](enable-product-recommendations.md) para o ambiente.

## <a name="additional-resources"></a>Recursos adicionais

[Disponibilizar o Repositório de Entidades como um Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[Visão geral das recomendações dos produtos](product-recommendations.md)

[Habilitar recomendações dos produtos](enable-product-recommendations.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Cancelar recomendações personalizadas](personalization-gdpr.md)

[Habilitar recomendações de "comprar looks semelhantes"](shop-similar-looks.md)

[Adicionar recomendações dos produtos no PDV](product.md)

[Adicionar recomendações à tela de transações](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
