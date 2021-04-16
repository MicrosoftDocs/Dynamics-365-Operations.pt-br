---
title: Grupos de gerenciamento de reembolso
description: Este tópico descreve como configurar Grupos de gerenciamento de reembolso. Os grupos de gerenciamento de reembolso podem ser usados durante cálculos de reembolso e podem ser anexados a um registro mestre.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 2d1f8ed9def03afc97c0b4c5ea86430ff089aac6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819223"
---
# <a name="rebate-management-groups"></a>Grupos de gerenciamento de reembolso

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Os cálculos de reembolsos e deduções podem ser orientados por grupos. Os grupos de gerenciamento de reembolso podem ser criados para clientes, fornecedores e itens. Eles podem ser anexados a um registro mestre.

## <a name="rebate-management-customer-groups"></a>Grupos de clientes de gerenciamento de reembolso

O cálculo de um grupo de clientes em geral é criado para uma cadeia de empresas, como uma rede de supermercados ou uma empresa de franquia. Esse tipo de cálculo costuma estar relacionado a um reembolso.

Uma dedução é frequentemente calculada sem considerar a quem a ordem de qualificação foi vendida. Mas existem exceções. Por exemplo, um licenciado pode criar um esquema de dedução em que o grupo de clientes A receberá 4%, mas o grupo de clientes B só receberá 3%.

### <a name="set-up-customer-groups"></a>Configurar grupos de clientes

Para trabalhar com grupos de clientes de Gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de clientes**. Você pode usar os botões no Painel de Ações para adicionar e remover grupos, conforme necessário. Em cada grupo, defina os seguintes campos:

- **Grupo de gerenciamento de reembolso** – insira um nome exclusivo para o grupo.
- **Descrição** – Insira uma descrição do grupo para fornecer mais informações sobre como ela deve ser usada.

### <a name="manage-customer-group-assignments"></a>Gerenciar atribuições de grupos de clientes

Cada cliente pode pertencer a qualquer número de Grupos de gerenciamento de reembolso. Para exibir e atribuir membros do grupo, você pode iniciar na lista de grupos ou na lista de clientes.

Para exibir, adicionar ou remover clientes de um grupo selecionado, siga estas etapas.

1. Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de clientes**.
1. Selecione o grupo a ser gerenciado.
1. No Painel de Ações, selecione **Clientes**. A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de clientes que já são membros do grupo selecionado.
1. Para adicionar um novo cliente ao grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Conta de cliente** – Selecione a ID de conta do cliente.
    - **Nome** – Insira um nome e/ou descrição do cliente.

1. Para remover um cliente do grupo, selecione o cliente e, depois, selecione **Excluir** no Painel de Ações.

Para exibir, adicionar ou remover atribuições de grupo para um cliente selecionado, siga estas etapas.

1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
1. Selecione o cliente com o qual deseja trabalhar.
1. No Painel de Ações, na guia **Cliente**, no grupo **Gerenciamento de reembolso**, selecione **Grupos de gerenciamento de reembolso**. A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de grupos aos quais o cliente selecionado já pertence.
1. Para adicionar o cliente a um novo grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Grupo de gerenciamento de reembolso** – Selecione o grupo ao qual o cliente será adicionado.
    - **Descrição** – Insira uma descrição do grupo (por exemplo, para explicar por que o cliente é membro dele).

1. Para remover um cliente de um grupo, selecione o grupo e, depois, selecione **Excluir** no Painel de Ações.

## <a name="rebate-management-vendor-groups"></a>Grupos de fornecedores de gerenciamento de reembolso

O cálculo de um grupo de fornecedores em geral é criado para um grupo de pontos de entrega. Esse tipo de cálculo costuma estar relacionado a um reembolso.

### <a name="set-up-vendor-groups"></a>Configurar grupos de fornecedor​es

Para trabalhar com grupos de fornecedores de Gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de fornecedores**. Você pode usar os botões no Painel de Ações para adicionar e remover grupos, conforme necessário. Em cada grupo, defina os seguintes campos:

- **Grupo de gerenciamento de reembolso** – insira um nome exclusivo para o grupo.
- **Descrição** – Insira uma descrição do grupo para fornecer mais informações sobre como ela deve ser usada.

### <a name="manage-vendor-group-assignments"></a>Gerenciar atribuições de grupos de fornecedores

Cada fornecedor pode pertencer a qualquer número de Grupos de gerenciamento de reembolso. Para exibir e atribuir membros do grupo, você pode iniciar na lista de grupos ou na lista de fornecedores.

Para exibir, adicionar ou remover fornecedores de um grupo selecionado, siga estas etapas.

1. Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de fornecedores**.
1. Selecione o grupo a ser gerenciado.
1. No Painel de Ações, selecione **Fornecedores**. A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de fornecedores que já são membros do grupo selecionado.
1. Para adicionar um novo fornecedor ao grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Conta de fornecedor** – Selecione a ID de conta do fornecedor.
    - **Nome** – Insira um nome e/ou descrição do fornecedor.

1. Para remover um fornecedor do grupo, selecione o fornecedor e, depois, selecione **Excluir** no Painel de Ações.

Para exibir, adicionar ou remover atribuições de grupo para um fornecedor selecionado, siga estas etapas.

1. Acesse **Contas a pagar \> Fornecedores \> Todos os fornecedores**.
1. Selecione o fornecedor com o qual deseja trabalhar.
1. No Painel de Ações, na guia **Fornecedor**, no grupo **Gerenciamento de reembolso**, selecione **Grupos de gerenciamento de reembolso**. A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de grupos aos quais o fornecedor selecionado já pertence.
1. Para adicionar o fornecedor a um novo grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Grupo de gerenciamento de reembolso** – Selecione o grupo ao qual o fornecedor será adicionado.
    - **Descrição** – Insira uma descrição do grupo (por exemplo, para explicar por que o fornecedor é membro dele).

1. Para remover um fornecedor de um grupo, selecione o grupo e, depois, selecione **Excluir** no Painel de Ações.

## <a name="item-rebate-groups"></a>Grupos de reembolsos de itens

Ao agrupar itens, você tem mais flexibilidade quando reembolsos e deduções são calculadas. Essa abordagem frequentemente é uma maneira mais eficiente de configurar reembolsos e deduções para clientes e fornecedores.

### <a name="set-up-item-groups"></a>Configurar grupos de itens

Para trabalhar com grupos de itens de Gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de itens**. Você pode usar os botões no Painel de Ações para adicionar e remover grupos, conforme necessário. Em cada grupo, defina os seguintes campos:

- **Grupo de gerenciamento de reembolso** – insira um nome exclusivo para o grupo.
- **Descrição** – Insira uma descrição do grupo para fornecer mais informações sobre como ela deve ser usada.

### <a name="manage-item-group-assignments"></a>Gerenciar atribuições de grupos de itens

Cada item pode pertencer a qualquer número de Grupos de gerenciamento de reembolso. Para exibir e atribuir membros do grupo, você pode iniciar na lista de grupos ou na lista de itens. Você também pode adicionar itens com base na sua hierarquia de categoria.

Para exibir, adicionar ou remover itens de um grupo selecionado, siga estas etapas.

1. Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de itens**.
1. Selecione o grupo a ser gerenciado.
1. No Painel de Ações, selecione **Itens**. A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de itens que já são membros do grupo selecionado.
1. Para adicionar um novo item ao grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Conta de item** – Selecione a ID de conta do item.
    - **Nome do produto** – Insira um nome e/ou descrição do item.

1. Para remover um item do grupo, selecione o item e, depois, selecione **Excluir** no Painel de Ações.

Para exibir, adicionar ou remover atribuições de grupo para um item selecionado, siga estas etapas.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione o item com o qual deseja trabalhar.
1. No Painel de Ações, na guia **Produto**, no grupo **Gerenciamento de reembolso**, selecione **Grupos de gerenciamento de reembolso**. A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de grupos aos quais o item selecionado já pertence.
1. Para adicionar o item a um novo grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Grupo de gerenciamento de reembolso** – Selecione o grupo ao qual o item será adicionado.
    - **Descrição** – Insira uma descrição do grupo (por exemplo, para explicar por que o item é membro dele).

1. Para remover um item de um grupo, selecione o grupo e, depois, selecione **Excluir** no Painel de Ações.

Para adicionar itens a um grupo com base na sua hierarquia de categoria, siga estas etapas.

1. Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de itens**.
1. Selecione o grupo a ser gerenciado.
1. No Painel de Ações, selecione **Adicionar itens**.
1. Na caixa de diálogo **Adicionar itens**, no campo **Hierarquia de categoria**, selecione uma categoria de nível superior.
1. A hierarquia de itens é aberta no painel esquerdo. Selecione o nível de hierarquia que você procura. 
1. Os itens da hierarquia e do nível de hierarquia selecionados agora são listados no painel à direita. Siga estas etapas para trabalhar com o painel:

    - Marque a caixa de seleção de cada item a ser adicionado.
    - Marque a caixa de seleção no cabeçalho da grade para selecionar todos os itens listados.
    - Selecione o botão **Mostrar selecionado** para filtrar a grade de forma que ela mostre apenas os itens selecionados até o momento. Selecione novamente o botão para retornar à lista completa.

1. Selecione **OK** para aplicar a seleção de itens ao grupo selecionado.
