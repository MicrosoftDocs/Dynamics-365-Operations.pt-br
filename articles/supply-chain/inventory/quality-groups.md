---
title: Grupos de qualidade de item
description: Este tópico descreve como usar e criar grupos de qualidade de item a fim de agrupar produtos de forma lógica para que eles possam ser atribuídos a associações de qualidade para a geração automática de ordens de qualidade.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f26aa50e814a7abb8e7ed3e6a943136578208854a9efb3b8e8d38016917681d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781480"
---
# <a name="item-quality-groups"></a>Grupos de qualidade de item

[!include [banner](../includes/banner.md)]

Um grupo de qualidade representa requisitos de teste comuns para itens. Este tópico descreve como usar e criar grupos de qualidade de item a fim de agrupar produtos de forma lógica para que eles possam ser atribuídos a associações de qualidade para a geração automática de ordens de qualidade.

Para configurar, editar e exibir os itens atribuídos a um grupo de qualidade, ou os grupos de qualidade atribuídos a um item, Acesse **Gerenciamento de estoque \> Configuração \> Grupos de qualidade**. Após definir os requisitos de teste da página **Grupos de teste**, você pode definir as regras para gerar automaticamente as ordens de qualidade. Para simplificar o processo, você não define regras para itens individuais. Em vez disso, você pode definir as regras para um grupo de qualidade na página **Associações de qualidade**.

## <a name="example-of-an-item-quality-group"></a>Exemplo de um grupo de qualidade de item

Uma fábrica compra diversas matérias-primas que têm os mesmos requisitos de teste para inspeção de entrada. Portanto, a empresa define um grupo de qualidade e então atribui os números de item associados às matérias-primas a esse grupo. Posteriormente, a empresa compra um novo tipo de matéria-prima que têm os mesmos requisitos de teste. Em vez de configurar novos requisitos de teste para o novo material, a empresa adiciona o número do item para o novo material no grupo de qualidade existente.

A mesma empresa também produz itens com os mesmos requisitos de teste de produção e remete itens com o mesmo requisito de teste antes da remessa. Portanto, a empresa define dois grupos de qualidade adicionais e então atribui os números de item relevantes a cada grupo.

## <a name="create-a-quality-group"></a>Criar um grupo de qualidade

Para criar um grupo de qualidade, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de qualidade**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Grupo de qualidade** – Insira um nome ou uma ID exclusiva para o grupo de qualidade.
    - **Descrição** – Insira uma descrição detalhada do grupo de qualidade.

1. Feche a página.

## <a name="manually-add-items-to-a-quality-group"></a>Adicionar itens manualmente a um grupo de qualidade

Para adicionar itens manualmente a um grupo de qualidade, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de qualidade**.
1. Selecione o grupo de qualidade ao qual você deseja adicionar itens.
1. No Painel de Ações, selecione **Itens**.
1. Na página **Itens em grupos de qualidade**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade. Em seguida, para a nova linha, defina o campo **Número do item** como o número do item que você deseja adicionar.
1. Repita a etapa anterior para cada item adicional que deve ser incluído.
1. Feche as páginas.

## <a name="add-multiple-items-to-a-quality-group"></a>Adicionar vários itens a um grupo de qualidade

Para adicionar vários itens a um grupo de qualidade, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de qualidade**.
1. Crie ou selecione o grupo de qualidade ao qual você deseja adicionar itens.
1. No Painel de Ações, selecione **Adicionar itens**.
1. Na caixa de diálogo **Consulta**, insira os critérios de filtragem dos itens que você deseja adicionar. Por exemplo, você pode filtrar todos os itens em um grupo de itens específico.
1. Selecione **OK**.
1. Na caixa de diálogo **Adicionar itens**, uma grade mostra todos os itens que correspondem à sua consulta. Revise os resultados.

    Se forem necessárias alterações, selecione **Selecionar** para retornar à caixa de diálogo **Consulta** e ajuste a consulta.

1. Quando os resultados incluírem todos os itens que você deseja adicionar, selecione **OK**.
1. Feche a página.

## <a name="manually-associate-an-item-with-a-quality-group"></a>Associar manualmente um item a um grupo de qualidade

Para associar manualmente um item a um grupo de qualidade, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de qualidade de item**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Número do item** – Selecione o número do item a ser adicionado.
    - **Grupo de qualidade** – Selecione o grupo de qualidade a ser atribuído ao item.

1. Repita a etapa anterior para cada combinação adicional de um item e um grupo de qualidade que deve ser incluída.
1. Feche as páginas.

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a>Adicionar manualmente um grupo de qualidade na página Produtos liberados

Para adicionar manualmente um grupo de qualidade na página **Produtos liberados**, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione o produto ao qual deseja atribuir um grupo de qualidade.
1. No Painel de Ações, na guia **Gerenciar estoque**, no grupo **Qualidade**, selecione **Grupos de qualidade de item**.
1. Na página **Itens em grupos de qualidade**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade. Em seguida, para a nova linha, defina o campo **Grupo de qualidade** como o grupo de qualidade que você deseja atribuir ao produto.
1. Repita a etapa anterior para cada grupo de qualidade adicional que você deseja atribuir ao produto.
1. Feche as páginas.

## <a name="additional-resources"></a>Recursos adicionais

- [Instrumentos de teste de gerenciamento de qualidade](quality-test-instruments.md)
- [Testes de gerenciamento de qualidade](quality-tests.md)
- [Grupos de teste de gerenciamento de qualidade](quality-test-groups.md)
- [Variáveis de teste de gerenciamento de qualidade](quality-test-variables.md)
- [Associações de qualidade](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
