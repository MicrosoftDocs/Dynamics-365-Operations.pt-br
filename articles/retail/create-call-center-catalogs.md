---
title: "Crie um catálogo de call center"
description: "Este artigo oferece uma visão geral do processo para a criação de um catálogo para um call center."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16212
ms.assetid: c9d1b9df-82e8-4b3a-a13c-166df8b9718e
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 29d005655856fd1eb0f1490c45e07649465539f2
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="create-a-call-center-catalog"></a>Crie um catálogo de call center

[!include [banner](includes/banner.md)]

Este artigo oferece uma visão geral do processo para a criação de um catálogo para um call center. 

Em um call center, você pode usar catálogos de produtos para identificar os produtos que deseja oferecer para os clientes. Os call centers usam normalmente catálogos impressos. O design e a produção de um catálogo impresso são tratados fora do Microsoft Dynamics 365 for Retail. No entanto, você pode criar e armazenar um formulário digital de um catálogo usando os mesmos formulários que você usa para configurar catálogos de varejo online. Antes de criar um catálogo, você deve configurar classificações de produtos e atribuir as classificações a um call center. Então, você pode adicionar produtos ao catálogo selecionando produtos desses sortimentos. Depois que o produtos tiverem sido adicionados ao catálogo, e o catálogo estiver concluído, você deve validar o catálogo para verificar os dados. Em seguida, é necessário enviar o catálogo para revisão e aprovação. Depois que o catálogo for aprovado, ele poderá ser publicado. Quando um catálogo de call center é criado, você pode fazer um instantâneo dos dados do catálogo no momento em que o catálogo é publicado. Essa funcionalidade do instantâneo permite acessar uma versão específica do catálogo, mesmo se ele for alterado e atualizado posteriormente. Catálogos de call center também podem ser configurados para incluir os seguintes recursos opcionais.

-   **Códigos de fonte** – Códigos usados para rastrear a resposta do cliente para endereçamentos específicos de catálogo.
-   **Produtos liberados** – Produtos que estão inclusos em uma ordem do cliente sem encargos adicionais. Esses produtos são adicionados automaticamente à ordem automaticamente quando o código de origem do catálogo é inserido na ordem.
-   **Scripts** – Textos que um trabalhador do call center lê para um cliente quando uma ordem de venda está sendo criada. Os scripts podem incluir cumprimentos ou sugestões de compra.
-   **Itens de venda adicional ou de venda cruzada** - Itens que serão exibidos como uma sugestão quando um produto específico é adicionado à ordem.

Essas opções devem ser definidas antes de o catálogo ser aprovado e publicado.

## <a name="prerequisites"></a>Pré-requisitos
As tarefas a seguir devem ser concluídas antes de você começar:

-   Configurar produtos e sortimentos de produtos.
-   Configurar produtos de varejo.
-   Configurar um sortimento.
-   Criar um call center.
-   Configurar um call center.
-   Adicionar o call center a uma hierarquia de organização.
-   Criar ou modificar uma hierarquia da organização.

## <a name="create-a-catalog"></a>Criar um catálogo
Primeiro, você deve criar um catálogo, adicionar produtos ao catálogo e, em seguida, revisar e atualizar os atributos dos produtos.

## <a name="validate-the-catalog"></a>Validar o catálogo
Depois de concluir a configuração do catálogo, você deve validá-la. O processo de validação verifica se os dados necessários para os atributos de canal e atributos de produto estão completos e válidos, e se o catálogo pode ser publicado.

## <a name="submit-the-catalog-for-review-and-approval"></a>Enviar o catálogo para revisão e aprovação
Depois que um catálogo for validado, você poderá enviá-lo para revisão e aprovação. O catálogo deve ser aprovado antes de ser publicado. Você pode configurar um fluxo de trabalho de modo que os catálogos sejam aprovados automaticamente ou exijam aprovação manual.

## <a name="optional-add-source-codes-free-products-and-scripts"></a>Opcional: adicione códigos fonte, produtos gratuitos e scripts
Você também pode adicionar os seguintes itens a um catálogo do call center. Esses itens são opcionais.

-   **Códigos-fonte** podem ser usados pelas empresas que fornecem catálogo impressos para rastrear a resposta do cliente para catálogos específicos. Os códigos-fonte geralmente são impressos no verso de um catálogo e são inseridos na ordem de venda quando um cliente faz uma compra. Para adicionar um código-fonte ao catálogo, primeiro você deve criar um mercado de destino. O mercado de destino geralmente é mapeado para uma lista de endereçamento própria ou alugada.
-   **Produtos gratuitos** são os itens promocionais que estão incluídos gratuitamente à ordem do cliente quando o catálogo é referenciado.
-   **Scripts** podem ser usados para orientar as interações do trabalhador com clientes no contexto de um catálogo ou de um produto em um catálogo.

## <a name="publish-the-catalog"></a>Publicar o catálogo
Publicando um catálogo para um call center, você finaliza as informações sobre o produto no catálogo. A publicação também indica que o catálogo está pronto para quaisquer ações adicionais que você deseja realizar. Por exemplo, você pode criar um catálogo impresso. Você pode publicar os catálogos manualmente ou usar um processo em lote para publicar de acordo com uma agenda. Antes de publicar um catálogo, ele deve ser validado e aprovado. Para alterar o catálogo depois que é for publicado, você pode retirar o catálogo então republicá-lo.




