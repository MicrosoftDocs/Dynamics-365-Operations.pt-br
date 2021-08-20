---
title: Configurar filtros de produto para transações de depósito
description: Este tópico descreve como configurar filtros de produto e códigos de filtros para categorizar itens de estoque em um depósito. Também é possível usar filtros para especificar quais clientes podem solicitar um item específico e quais itens podem ser comprados de um fornecedor específico.
author: Mirzaab
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSFilters,WHSFilterGroupTable,EcoResProductDetailsExtended,WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 6302d596245e058ae0c25fbd91333dbf050e21db5b48f6893131ec1a561e046d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768537"
---
# <a name="configure-product-filters-for-warehouse-transactions"></a>Configurar filtros de produto para transações de depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve como configurar filtros de produto e códigos de filtros para categorizar itens de estoque em um depósito. Também é possível usar filtros para especificar quais clientes podem solicitar um item específico e quais itens podem ser comprados de um fornecedor específico.

Além disso, é possível configurar e usar filtros de produto para organizar automaticamente os itens de estoque em um depósito e combinar itens filtrados em grupos de filtros. Os filtros podem ser usados para colocar itens em categorias para processos de manuseio, compra e venda. Pode ser interessante agrupar itens ou separá-los um do outro quando a forma como são manuseados é baseada em restrições de peso ou de manuseio. Você também pode especificar para quais clientes ou fornecedores um item pode ser comprado ou vendido.

## <a name="prerequisites"></a>Pré-requisitos

A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.

| Pré-requisito | Instruções |
|---|---|
| Antes de começar a configurar produtos na página **Detalhes do produto liberado**, você deve ativar o processamento de depósito para o grupo de dimensões de armazenamento do produto. | Acesse **Gerenciamento de informações de produto \> Configuração \> Dimensões e grupos de variantes \> Grupos de dimensões de armazenamento** e selecione ou crie um grupo de dimensões de armazenamento em que a opção **Usar processos de gerenciamento de depósito** está definida como *Sim*. |
| Se você usar filtros de cliente e/ou filtros de fornecedor, será necessário habilitar o uso deles nos parâmetros de gerenciamento de depósito. | Acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**. Na guia **Filtros de produto**, defina a opção **Habilitar filtros do cliente** e/ou **Habilitar filtros do fornecedor** como *Sim*. |

## <a name="set-up-product-filters"></a>Configurar os filtros de produto

Os filtros de produto fornecem até 10 características de **Título do filtro**, que são valores de enumeração (enum). Esses valores de enumeração ficam disponíveis para seleção quando você cria um filtro de produto. Os valores de enumeração *Código 1* até *Código 10* são definidos pelo sistema e representam características ou atributos específicos de um item. Por exemplo, o *código 1* pode representar itens que têm uma classificação de material perigoso. O *código 2* pode representar itens que somente os fornecedores podem comprar. Os filtros de produto definem o valor de **Código de filtro** específico associado a um valor de **Título de filtro**.

1. Acesse **Gerenciamento de depósito \> Configuração \> Filtros de produto \> Filtros de produto**.
1. No Painel de Ações, selecione **Novo** para adicionar um filtro de produto à grade.
1. No campo **Título do filtro**, selecione um valor.
1. No campo **Código do filtro**, insira um valor.

    ![Configurar um filtro de produto.](media/Product_Filters10.png "Configurar um filtro de produto")

1. No campo **Descrição**, insira um nome para o código. Por exemplo, o *código 2* pode representar fornecedores. Em seguida, você poderá criar um filtro de produto para um fornecedor ou grupo de fornecedores específico. Para obter mais informações, consulte a seção [Configurar códigos de filtro de fornecedor](#vendor-product-filters) posteriormente neste tópico.

    ![Conjunto de filtros de produto.](media/Product_Filters.png "Conjunto de filtros de produto")

## <a name="set-up-product-filter-groups"></a>Configurar grupos de filtros de produto

É possível usar os grupos de filtros para agrupar os códigos de filtro. Esse recurso é útil quando um grupo for usado em uma consulta em uma diretiva de local e quando você quiser pesquisar o grupo em vez de uma série de códigos. Cada grupo de filtros é associado a um grupo de itens.

> [!IMPORTANT]
> Nem todos os grupos de filtros de produto estão disponíveis para códigos de filtro maiores que o *código 4* (ou seja, do *código 5* a *código 10*). Por exemplo, para produtos liberados, embora todos os códigos de filtro de produtos sejam adicionados, o agrupamento de códigos de filtro não será atualizado. Esse comportamento pode ser atualizado em versões posteriores.

Para configurar os grupos de filtros, siga essas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Filtros de produto \> Grupos de filtros de produto**.
1. No Painel de Ações, selecione **Novo**.
1. Nos campos **Grupo 1** e **Grupo 2**, insira os nomes que serão usados para categorizar os itens.
1. Na guia rápida **Detalhes**, selecione **Novo** para adicionar uma linha.
1. Nos campos **Data/hora de início** e **Data/hora de término**, insira as datas inicial e final do grupo de filtros.
1. No campo **Grupo de itens**, selecione o grupo de itens ao qual o filtro de produtos deve ser aplicado.
1. Nos campos **Código 1** até **Código 10**, selecione os códigos de filtro a serem incluídos no grupo, conforme necessário.

    ![Grupo de itens.](media/ProdFilterGroup.png "Grupo de itens")

> [!NOTE]
> Se receber uma mensagem de erro quando fechar a página, uma configuração de código pode ficar ausente. Na página **Grupos de itens**, você pode tornar os códigos obrigatórios para um grupo de itens selecionando as caixas de seleção **Atribuir código 1 de filtro para o grupo de itens**, **Atribuir código 2 de filtro para o grupo de itens** e assim por diante.

## <a name="set-up-filter-codes-on-item-groups"></a>Configurar códigos de filtros em grupos de itens

Ao configurar os códigos de filtros em um grupo de itens, é possível criar os códigos necessários para os produtos que são anexados ao grupo de itens.

Para configurar os códigos de filtros nos grupos de itens, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Divisão de estoque \> Grupos de itens**.
1. No Painel de Ação, selecione **Novo** para criar um grupo de itens.
1. No campo **Grupo de itens**, digite um nome.
1. No campo **Nome**, insira uma descrição.
1. Na guia rápida **Depósito**, na seção **Filtro necessário**, marque as caixas de seleção para os códigos de filtros que devem ser especificados para os produtos associados ao grupo de itens.

    Para atualizar um produto liberado, abra a página **Detalhes do produto liberado** e, no painel de ações, selecione **Editar**. Os filtros associados a códigos são disponibilizados na guia rápida **Depósito**.

    ![Grupos de itens.](media/ItemGroup10.png "Grupos de itens")

1. Na seção **Filtro do grupo de itens**, marque as caixas de seleção dos filtros que devem corresponder ao grupo de filtros para ser o grupo de filtros padrão de um item.

    Por exemplo, se as caixas de seleção **Usar código 1** e **Usar código 2** forem marcadas, tanto o código de filtro 1 e 2 do item devem corresponder à configuração do grupo de filtros para o grupo de itens, antes de ser possível selecionar o grupo de filtros. Quando você cria um novo item, o grupo de filtros selecionado será o grupo de filtros padrão nos campos **Grupo 1** e **Grupo 2** na guia rápida **Depósito** da página **Detalhes do produto liberado**.

> [!IMPORTANT]
> Os códigos de filtro de produto são habilitados somente para itens que usam o gerenciamento de depósito avançado.

## <a name="specify-filter-codes-for-released-products"></a>Especificar os códigos de filtro para produtos lançados

Siga estas etapas para especificar os códigos de filtros para produtos lançados. Por exemplo, você pode usar os códigos de filtro para agrupar produtos perigosos que os fornecedores específicos compram.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. No Painel de Ação, selecione **Novo** para criar um produto.
1. Na caixa de diálogo **Novo produto liberado**, insira os dados necessários para criar a base de um novo produto e selecione **OK**.

    Os códigos de filtro de produto não são habilitados a menos que o grupo de itens anexado ao produto tenha sido configurado para códigos de filtro.

    Para obter mais informações, consulte [Criar um novo produto](../pim/tasks/create-new-product.md).

1. Na guia rápida **Depósito**, na seção **Códigos de filtro do produto**, selecione os códigos de filtro para os campos **Código 1** até **Código 10**, conforme necessário, para especificar os códigos de filtro para o produto.

## <a name="set-up-generally-available-items"></a>Configurar itens geralmente disponíveis

É possível disponibilizar itens específicos de estoque disponíveis apenas para clientes, apenas para fornecedores ou para clientes e fornecedores.

> [!NOTE]
> , Os filtros do cliente e os filtros do fornecedor não se aplicam a itens que você geralmente configura como disponível.

Para configurar itens geralmente disponíveis, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Filtros de produto \> Produto geralmente disponíveis**.
1. No Painel de Ação, selecione **Novo** para criar um registro.
1. No campo **Cliente ou fornecedor**, selecione *Cliente*, *Fornecedor* ou *Todos* para disponibilizar os itens para clientes, fornecedores ou ambos.
1. No campo **Data/hora de início**, digite a data e a hora em que o item ficará disponível.
1. No campo **Grupo de itens**, selecione o grupo de itens.
1. Nos campos **Código 1** até **Código 10** , selecione os códigos de filtro para limitar os itens que ficam geralmente disponíveis.

    Quando você seleciona um grupo de itens, defina esse grupo de itens como geralmente disponível. Ao selecionar os códigos de filtro nesses campos, você limita os itens que ficam disponíveis.

## <a name="set-up-customer-product-filters"></a>Configurar os filtros de produto do cliente

Você pode usar este procedimento para especificar os itens que devem ficar disponíveis para um cliente, além dos itens que são disponibilizados através da configuração de filtro no formulário página **Itens geralmente disponíveis**. É possível configurar vários filtros para um único cliente.

Para configurar códigos de filtros do cliente, siga estas etapas.

1. Acesse **Vendas e marketing \> Clientes \> Todos os clientes**.
1. Selecione um cliente.
1. No Painel de Ação, na guia **Cliente**, no grupo **Configuração**, selecione **Filtros de produto**.
1. Na página **Códigos de filtro de produto**, no Painel de Ação, selecione **Novo**.
1. Nos campos **Data/hora de início** e **Data/hora de término**, insira as datas inicial e final do grupo de itens selecionado.
1. No campo **Grupo de itens**, selecione o grupo de itens.
1. Nos campos **Código 1** até **Código 10**, selecione os códigos de filtro a serem usados como critérios para limitar os itens disponíveis para clientes no grupo de itens selecionado. Você deve fazer uma seleção para cada código de filtro configurado para o grupo de itens.

## <a name="set-up-vendor-product-filters"></a><a name="vendor-product-filters"></a>Configurar os filtros de produto do fornecedor

Você pode usar este procedimento para especificar os itens que devem ficar disponíveis para um fornecedor, além dos itens que são disponibilizados através da configuração de filtro no formulário página **Itens geralmente disponíveis**. É possível configurar vários filtros para um único fornecedor.

Para configurar códigos de filtros do fornecedor, siga estas etapas.

1. Acesse **Aquisição e fornecimento \> Fornecedores \> Todos os fornecedores**.
1. Selecione um fornecedor.
1. No Painel de Ação, na guia **Fornecedor**, no grupo **Configuração**, selecione **Filtros de produto**.
1. Na página **Códigos de filtro**, no Painel de Ação, selecione **Novo**.
1. Nos campos **Data/hora de início** e **Data/hora de término**, insira as datas inicial e final do grupo de itens selecionado.
1. No campo **Grupo de itens**, selecione o grupo de itens.
1. Nos campos **Código 1** até **Código 10**, selecione os códigos de filtro a serem usados como critérios para limitar os itens disponíveis para fornecedores no grupo de itens selecionado. Você deve fazer uma seleção para cada código de filtro configurado para o grupo de itens.

> [!NOTE]
> A configuração de filtros de produtos de fornecedor aplica-se a produtos liberados nos quais os processos de gerenciamento de depósito estão habilitados para o grupo de dimensões de armazenamento associado. Os códigos de filtro são usados para determinar se o sistema permitirá que os usuários comprem um determinado item de um determinado fornecedor ao criarem linhas da ordem de compra. O Microsoft Dynamics 365 Supply Chain Management tem dois métodos de lidar com a aprovação de fornecedores. Se um ou mais produtos liberados existirem quando o campo **Método de verificação de fornecedores aprovados** estiver definido como *Somente aviso* ou *Não permitido*, os dois métodos de aprovação do fornecedor poderão ser habilitados para esses itens. Essa situação pode causar problemas quando os usuários criarem linhas da ordem de compra.

## <a name="see-also"></a>Consulte também

[Para obter mais informações, consulte a postagem no blog Códigos de filtro de depósito do WMS](http://blog.dynamics-for-operations.com/2017/09/26/wms-warehouse-filter-codes/)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]