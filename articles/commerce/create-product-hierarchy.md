---
title: Criar uma nova hierarquia de produtos
description: Este tópico descreve como criar uma nova hierarquia de produtos no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: fe1f194868ad04d8b64218186b2eb90cb34988c2
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352365"
---
# <a name="create-a-new-product-hierarchy"></a>Criar uma nova hierarquia de produtos


[!include [banner](includes/banner.md)]

Este tópico descreve como criar uma nova hierarquia de produtos no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O Dynamics 365 Commerce oferece suporte a vários canais de varejo. Esses canais de varejo incluem lojas online, call centers e lojas de varejo (também chamadas de lojas tradicionais). Cada canal de loja de varejo pode ter seus próprios métodos de pagamento, grupos de preços, terminais de pontos de venda (PDV), contas de receita e despesa e equipe. Você deve configurar todos esses elementos para poder criar um canal de loja de varejo. 

Uma hierarquia de produtos de Comércio é usada para definir a hierarquia de produtos geral da sua organização. Você pode usar uma hierarquia de produtos de Comércio para comercialização, preços e promoções, relatórios e planejamento de classificação. Apenas uma hierarquia de produtos de Comércio pode ser atribuída por organização.

## <a name="create-and-configure-a-product-hierarchy"></a>Criar e configurar uma hierarquia de produtos

Para criar e configurar uma hierarquia de produtos de Comércio, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Hierarquia de produtos de comércio**.
1. Se ainda não existir uma hierarquia, no **Painel de ação**, selecione **Novo** para criar a raiz da hierarquia.
1. Em **Geral**:
    1. Na caixa **Nome**, insira um nome.
    1. Na caixa **Descrição**, insira uma descrição.
    1. Na caixa **Nome amigável**, insira um nome amigável.
    1. Defina **Ativo** como **Sim**.

## <a name="add-hierarchy-nodes"></a>Adicionar nós de hierarquia

Para adicionar nós de hierarquia, siga estas etapas.

1. No painel de ação, selecione **Editar hierarquia de categoria**.
1. Selecione o nó pai ao qual você deseja adicionar um novo nó e clique em **Novo nó de categoria**.
1. Na seção **Geral**, forneça **Nome**, **Descrição**, **Nome amigável** e **Palavras-chave**.
1. Em **Geral**:
    1. Na caixa **Nome**, insira um nome.
    1. Na caixa **Descrição**, insira uma descrição.
    1. Na caixa **Nome amigável**, insira um nome amigável.
    1. Na caixa **Palavras-chave**, insira palavras-chave relevantes.
    1. Na caixa **Ordem de exibição**, insira um número para a ordem de exibição (opcional).
1. No painel de ação, selecione **Salvar**.
1. Repita as etapas acima para adicionar mais nós.

A imagem a seguir mostra a criação de um novo nó de hierarquia de produtos.

![Criar hierarquia de produtos.](media/create-product-hierarchy.png)

## <a name="other-settings"></a>Outras configurações

Grupos de atributos de categoria também podem ser atribuídos a cada grupo, conforme necessário.  

## <a name="additional-resources"></a>Recursos adicionais

[hierarquias do Commerce](retail-hierarchies.md)

[Gerenciar produtos e categorias de produtos ](category-management-product-creation.md)

[Alterar a ordem de classificação das entidades de comercialização](custom-order-categories-nav-retail-prod-hierarchy.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]