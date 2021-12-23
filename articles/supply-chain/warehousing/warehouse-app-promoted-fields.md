---
title: Configurar campos promovidos para etapas no aplicativo móvel do Warehouse Management
description: Este tópico descreve como promover e destacar informações específicas para qualquer etapa nos fluxos de tarefas para o aplicativo móvel do Warehouse Management.
author: Mirzaab
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 117730fd7b744e0462e10468e32a13203d0695bf
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2021
ms.locfileid: "7901837"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>Configurar campos promovidos para etapas no aplicativo móvel do Warehouse Management

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until GA with 10.0.23 -->

> [!IMPORTANT]
> Os recursos descritos neste tópico se aplicam apenas ao novo aplicativo móvel Warehouse Management. Eles não afetam o antigo aplicativo de depósito, que foi preterido.

Este tópico descreve como promover e destacar informações específicas para qualquer etapa nos fluxos de tarefas para o aplicativo móvel do Warehouse Management. Esse recurso pode ajudar a concentrar a atenção dos funcionários nos campos mais importantes enquanto eles funcionam em um fluxo. Para cada etapa em cada processo, os administradores podem selecionar os campos a serem promovidas e os campos a serem realçados.

## <a name="enable-promoted-fields-in-your-system"></a>Habilitar os campos promovidos no sistema

Antes de configurar os campos promovidos, você deve concluir o procedimento a seguir para habilitar os recursos necessários e gerar os nomes de campos necessários no aplicativo móvel do Warehouse Management.

1. Acesse **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.
1. No [espaço de trabalho **Gerenciamento de recursos**](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), habilite o recurso listado da seguinte forma:

    - **Módulo:** *Gerenciamento de depósito*
    - **Nome do recurso:** *instruções de etapa do aplicativo Warehouse*

    Para obter mais informações sobre o recurso *Instruções de etapa do aplicativo do Warehouse*, consulte [Personalizar títulos de etapas e instruções para o aplicativo móvel do Warehouse Management](mobile-app-titles-instructions.md). Esse recurso é um pré-requisito para o recurso *Campos promovidos do aplicativo do Warehouse*.

1. Habilite o recurso listado da seguinte maneira:

    - **Módulo:** *Gerenciamento de depósito*
    - **Nome do recurso:** *campos promovidos do aplicativo do Warehouse*

    Esse recurso é o descrito neste tópico.

1. Atualize os nomes de campo no aplicativo móvel do Warehouse Management acessando **Warehouse management \> Configuração \> Dispositivo móvel \> Nomes de campo do aplicativo do Warehouse** e selecionando **Criar configuração padrão**. Para obter mais informações, consulte [Configurar campos para o aplicativo móvel Warehouse Management](configure-app-field-names-priorities-warehouse.md).
1. Repita a etapa anterior para cada entidade legal (empresa) em que você usa o aplicativo móvel do Warehouse Management.

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>Configurar campos promovidos de uma substituição específica de menu

Use o procedimento a seguir para configurar os campos promovidos.

1. Crie uma substituição específica do menu para o menu e a etapa relevantes conforme descrito em [Personalizar títulos e instruções de etapas para o aplicativo móvel do Warehouse Management](mobile-app-titles-instructions.md).
1. Encontre a combinação de valores de **ID da Etapa** e **Nome do item de menu** que deseja editar e então selecione o valor na coluna **ID da Etapa**.
1. Na página exibida, na Guia Rápida **Selecionar campos promovidos**, selecione **Selecionar campos** na barra de ferramentas.
1. Na caixa de diálogo **Campos promovidos**, selecione os campos que deseja promover. Você também pode realçar até dois campos selecionados. Os campos realçados serão mostrados em negrito no aplicativo móvel do Warehouse Management. À medida que você seleciona campos, considere o fato de que algumas telas podem ser grandes o suficiente para mostrar somente os primeiros ou dois campos promovidos. Para obter um exemplo que mostra como usar essas configurações, consulte o cenário posteriormente neste tópico.

    > [!NOTE]
    > A lista **Campos disponíveis** é limitada aos campos que podem aparecer para o item de menu. No entanto, outros fatores (como composição de item) determinam se um campo aparece realmente no aplicativo móvel do Warehouse Management. Se você tiver configurado campos promovidos, somente os campos selecionados aparecerão na página principal do aplicativo móvel do Warehouse Management. No entanto, os trabalhadores ainda poderão exibir os campos restantes tocando na página de detalhes.

1. Selecione **OK** para aplicar as configurações. Os campos selecionados agora estão listados na Guia Rápida **Selecionar campos promovidos**.

## <a name="example-scenario"></a>Cenário de exemplo

### <a name="enable-sample-data"></a>Habilitar dados de exemplo

Para usar os registros e valores de exemplo especificados para trabalhar neste cenário, você deverá usar um sistema em que os dados de demonstração padrão estejam instalados. Você também deve selecionar a entidade legal **USMF** antes de começar.

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>Configurar a separação de vendas com as etapas promovidas na etapa da placa de licença

Neste procedimento, você configurará campos promovidos e realçados para o item de menu **Separação de vendas** na etapa da placa de licença.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Etapas do dispositivo móvel**.
1. Localize a ID da etapa chamada *LicensePlateId* e selecione-a.
1. No Painel de Ações, selecione **Adicionar configuração de etapa**.
1. Na caixa de diálogo suspensa, use o campo **Item de menu** para localizar e selecione *Separação de vendas*.
1. Selecione **OK**.
1. A página de detalhes da substituição que você acabou de criar aparecerá. Na Guia Rápida **Selecionar campos promovidos**, selecione **Selecionar campos** na barra de ferramentas.
1. Na caixa de diálogo **Campos promovidos**, você pode selecionar os campos a serem promovidos e realçados. Na lista **Campos disponíveis**, localize e selecione os campos a seguir e use os botões para movê-los para a lista **Campos selecionados**:

    - Localização
    - Item
    - Nome do produto
    - Status do estoque

1. Use os botões de seta para cima e para baixo para personalizar a ordem dos campos na lista **Campos selecionados**. No aplicativo móvel do Warehouse Management, os campos serão exibidos na ordem definida aqui.
1. Selecione o campo **Local** e selecione **Realçar**.
1. Selecione **OK** para salvar a configuração.

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>Exibir os campos promovidos no aplicativo móvel do Warehouse Management

Neste procedimento, você abrirá o aplicativo móvel do Warehouse Management e passará pelas etapas para exibir os campos que você promoveu e realçou no procedimento anterior.

1. No Microsoft Dynamics 365 Supply Chain Management, crie uma ordem de venda que exigirá uma etapa de seleção para separar de um local rastreado na placa de licença. Em seguida, libere a ordem de venda para o depósito. Anote a ID do trabalho gerada.
1. Abra o aplicativo móvel do Warehouse Management e entre no depósito 24. (Nos dados de demonstração padrão, entre usando *24* como a ID do usuário e *1* como a senha.)
1. Selecione o menu **Saída** e selecione o item de menu **Separação de vendas**.
1. Siga as instruções de entrada de dados na tela para inserir a ID do trabalho que foi gerada na etapa 1.
1. Na etapa que contém o texto **Digitalizar uma placa de licença**, você verá as alterações feitas na página de detalhes. Os campos aparecem na ordem que você define para os campos promovidos, e o campo **Local** é mostrado em negrito.
