---
title: Cancelar recomendações personalizadas
description: Este tópico explica como você pode permitir que os clientes optem por receber recomendações personalizadas no Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: 6a64b45e1326673dd84c3c705491c9c100cdd069
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410161"
---
# <a name="opt-out-of-personalized-recommendations"></a>Cancelar recomendações personalizadas

[!include [banner](includes/banner.md)]

Este tópico explica como você pode permitir que os clientes optem por receber recomendações personalizadas no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Durante a criação da conta, novos clientes são configurados automaticamente para receber recomendações personalizadas. No entanto, o Dynamics 365 Commerce fornece várias maneiras para os varejistas permitirem que os usuários cancelem o recebimento dessas recomendações e restrinjam o processamento de seus dados pessoais. Os usuários autenticados que optarem por receber recomendações personalizadas irão parar imediatamente de ver as listas personalizadas. Além disso, todos os dados pessoais coletados para personalização serão removidos dos modelos de recomendações personalizados.

Para obter mais informações sobre recomendações personalizadas de produtos, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a>Maneiras de os varejistas implementarem uma experiência de recusa

Os varejistas podem implementar uma experiência de recusa de três maneiras.

### <a name="opting-out-on-behalf-of-users"></a>Recusar em nome de usuários

No gerenciamento de contas do back office do Commerce, os varejistas podem recusar em nome de usuários.

1. Na home page de back-office, procure **todos os clientes**.
1. Procure e selecione um cliente e a guia rápida **Retail**.

    ![Guia rápida Retail](./media/Disablepersonalizationpart1.png)

1. Em **Privacidade**, defina a opção **Desabilitar personalização** como **Sim**.

    ![Configurações de privacidade](./media/Disablepersonalizationpart2.png)

1. Selecione **Salvar** e feche a página.

### <a name="module-based-opt-out-experience"></a>Experiência de recusa baseada em módulo

Os varejistas podem permitir que os usuários autenticados cancelem as recomendações personalizadas sozinhos. Para fornecer essa experiência de recusa, adicione o módulo de recusa de usuário às páginas de perfil de conta de cliente.

### <a name="custom-extensions"></a>Extensões personalizadas

Os varejistas podem criar suas próprias extensões para gerenciar a experiência de recusa dos usuários. Para obter mais informações, consulte [Chamar APIs do Retail Server](e-commerce-extensibility/call-retail-server-apis.md) e a [extensibilidade de canal online](e-commerce-extensibility/overview.md).

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a>Obtenha uma cópia digital de dados de recomendações personalizados em nome de um usuário autenticado

Talvez os clientes desejem obter uma cópia digital de dados pessoais e também uma exibição exportada dos resultados de recomendações. Se um cliente solicitar essas informações, o varejista deverá criar uma extensão personalizada que chame a API (interface de programação de aplicativo) do servidor de varejo e consultas para obter os resultados da lista **Seleções para você**, com base na ID de cliente do cliente. Os resultados podem ser exportados no formato de valores separados por vírgulas (CSV) e compartilhados com o cliente.

O exemplo a seguir mostra como um varejista pode realizar essa tarefa.

1. O varejista cria uma extensão personalizada para receber dados de recomendações pessoais em nome do usuário. Para obter informações sobre como criar módulos, clonar módulos existentes, chamar APIs do Retail Server e chamar ações de dados, consulte [Extensibilidade do canal online](e-commerce-extensibility/overview.md).
2. A extensão personalizada faz uma chamada para a ação de dados principais **get-recommendations** e passa as informações necessárias para ela, com base nos requisitos da lista. No caso da lista **Seleções para Você**, a extensão deve passar o nome da lista e a ID do cliente corretos para a ação de dados.

    Uma forma de criar a extensão personalizada é clonar o módulo de coleção de produtos existente usado para devolver resultados de recomendações. Ao clonar este módulo existente, um varejista pode modificar o código existente e adicionar um novo botão que exporte os resultados de recomendações para um arquivo CSV. Para obter mais informações, consulte [Clonar um módulo de biblioteca de módulo](e-commerce-extensibility/clone-starter-module.md) e [módulos de coleção de produtos](product-collection-module-overview.md).

    Para obter uma exibição completa da biblioteca da API do Retail Server, consulte [Cliente do Retail Server e APIs de consumo](dev-itpro/retail-server-customer-consumer-api.md).

3. Depois que a extensão personalizada é criada, o varejista pode exportar um arquivo CSV de todos os resultados de recomendações, com base na ID exclusiva do cliente do usuário autenticado.
4. O varejista pode compartilhar o arquivo CSV exportado que contém a lista completa personalizada de produtos recomendados com o usuário autenticado.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações dos produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações de produtos](enable-product-recommendations.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Habilitar recomendações de "comprar looks semelhantes"](shop-similar-looks.md)

[Adicionar recomendações dos produtos no PDV](product.md)

[Adicionar recomendações à tela de transações](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)
