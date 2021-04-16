---
title: Proprietários de produto
description: Este tópico fornece informações sobre proprietários de produto. O proprietário de um produto é um grupo de usuários responsáveis por produtos específicos. Somente os membros do grupo podem liberar esses produtos. O proprietário do produto também pode ser usado no fluxo de trabalho de aprovação.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 679712b2397f220e263da3df07ecd03c99bebf3f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842017"
---
# <a name="product-owners"></a>Proprietários de produto

[!include [banner](../includes/banner.md)]

O proprietário de um produto é um grupo de usuários responsáveis por produtos específicos. Quando um grupo de proprietários de produtos é atribuído a um produto, somente os membros desse grupo podem liberar o produto. O proprietário do produto também pode ser usado no fluxo de trabalho de aprovação no gerenciamento de alteração de engenharia.

Os proprietários de produtos são configurações globais. Portanto, estão disponíveis para todas as entidades legais.

## <a name="create-a-product-owner-group"></a>Criar um grupo de proprietários de produtos

Para criar um grupo de proprietários de produtos e adicionar membros a ele, siga estas etapas.

1. Vá para **Gerenciamento de alteração de engenharia \> Configuração \> Proprietários de produto**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **Proprietário de produto**, insira um nome para o grupo.
4. No campo **Nome**, insira uma descrição do grupo.
5. Na Guia rápida **Membros**, adicione os trabalhadores que devem ser membros do grupo.

## <a name="assign-a-product-owner-to-a-product"></a>Atribuir um proprietário de produto a um produto

Para atribuir uma propriedade de produto a um produto, siga estas etapas.

1. Abra a página **Detalhes de produto** para o produto ou produto mestre relevante.
1. Na Guia rápida **Geral**, defina o campo **Proprietário do produto** como o nome do grupo de proprietários de produtos relevante.

Enquanto um proprietário de produto é atribuído a um produto, somente os membros do grupo de proprietários de produtos podem editar a configuração do **Proprietário do produto**.

O proprietário do produto também está visível na página **Produtos liberados**.

## <a name="product-owners-and-product-releases"></a>Proprietários de produtos e liberações de produtos

Somente os usuários do grupo de proprietários de produtos do produto podem liberar esse produto. No entanto, há uma exceção quando o produto é um item filho, e seu pai é liberado pelo proprietário do pai. Em outras palavras, se o produto fizer parte da BOM de outro produto, o sistema não verificará o proprietário do produto de cada item na BOM. Ele verifica somente o proprietário do produto do item pai.

Por exemplo, o produto X é atribuído ao grupo de proprietários de produtos *Projetar gabinetes*. O produto X também faz parte da BOM do produto Y, que é atribuída ao grupo de proprietários de produtos de *Design de alto-falantes*. Se um usuário do grupo de proprietários de produtos *Design de alto-falantes* lançar o produto Y e sua BOM, o produto X será liberado junto com o produto Y.

## <a name="product-owners-and-approvals"></a>Proprietários e aprovações de produtos

Como os proprietários de produtos sabem se as alterações de engenharia específicas se beneficiarão com seus produtos, geralmente faz sentido incluí-las como parte do processo de aprovação no gerenciamento de alterações de engenharia. Você pode implementar essa abordagem configurando os proprietários de produtos como provedores de participantes nos fluxos de trabalho que são usados para o gerenciamento de alterações de engenharia. O sistema atribuirá tarefas de aprovação nos fluxos de trabalho com base nos produtos que estão nas solicitações de alteração de engenharia e nas ordens de alteração de engenharia. Para obter mais informações, consulte [Gerenciar alterações de produtos de engenharia](engineering-change-management.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]