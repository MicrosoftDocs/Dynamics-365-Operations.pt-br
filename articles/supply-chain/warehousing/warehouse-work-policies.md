---
title: Políticas de trabalho
description: Este tópico explica como configurar políticas de trabalho.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 5ea93324547ed81df120db3412ee41fce2a93f4a
ms.sourcegitcommit: 27233e0fda61dac541c5210ca8d94ab4ba74966f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2020
ms.locfileid: "3651996"
---
# <a name="work-policies"></a>Políticas de trabalho

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar o sistema e o aplicativo de depósito para que eles ofereçam suporte a políticas de trabalho. Você pode usar essa funcionalidade para registrar rapidamente o estoque, sem criar o trabalho de armazenamento ao receber ordens de compra ou de transferência ou ao concluir processos de fabricação. Este tópico fornece informações gerais. Para obter informações detalhadas relacionadas ao recebimento da placa de licença, consulte [Recebimento da placa de licença por meio do aplicativo de depósito](warehousing-mobile-device-app-license-plate-receiving.md).

Uma política de trabalho controla se o trabalho de depósito é criado quando um item fabricado é relatado como concluído ou quando as mercadorias são recebidas usando o aplicativo de depósito. Configure cada política de trabalho definindo as condições em que ela se aplica: os tipos e os processos de ordem de trabalho, a localização de estoque e (opcionalmente) os produtos. Por exemplo, uma ordem de compra para o produto *A0001* deve ser recebida no local *RECV* no depósito *24*. Posteriormente, o produto é consumido em outro processo no local *RECV*. Nesse caso, você pode configurar uma política de trabalho para impedir que trabalho de armazenamento seja criado quando um trabalhador relatar o produto *A0001* como recebido no local *RECV*.

> [!NOTE]
> - Para que uma política de trabalho fique ativa, você deve definir pelo menos uma localização para ela na FastTab **Locais de estoque** da página **Políticas de trabalho**. 
> - Não é possível especificar a mesma localização para várias políticas de trabalho.
> - A opção **Imprimir etiqueta** para os itens de menu do dispositivo móvel não imprimirá uma etiqueta de placa de licença, a menos que tenha sido criado um trabalho.

## <a name="activate-the-features-in-your-system"></a>Ativar os recursos no sistema

Para disponibilizar toda a funcionalidade descrita neste tópico no sistema, ative estes dois recursos no [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Aprimoramentos de recebimento da placa de licença
- Aprimoramentos da política de trabalho para trabalho de entrada

## <a name="the-work-policies-page"></a>A página Políticas de trabalho

Para configurar políticas de trabalho, vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Políticas de trabalho**. Em seguida, em cada FastTab, defina os campos conforme descrito nas subseções a seguir.

### <a name="the-work-order-types-fasttab"></a>A FastTab Tipos de ordem de trabalho

Na FastTab **Tipos de ordem de trabalho**, adicione todos os tipos de ordem de trabalho e os processos de trabalho relacionados aos quais a política de trabalho se aplica. Os tipos de ordem de trabalho e processos de trabalho relacionados a seguir têm suporte para políticas de trabalho.

| Tipo de ordem de serviço | Processo de trabalho |
|---|---|
| Separação de matéria-prima| Todos os processos relacionados |
| Armazenamento de coproduto e subproduto | Todos os processos relacionados |
| Armazenamento de mercadorias acabadas | Todos os processos relacionados |
| Recebimento de transferência | Recebimento (e armazenamento) da placa de licença |
| Ordens de Compra | <ul><li>Recebimento (e armazenamento) da placa de licença</li><li>Recebimento (e armazenamento) do item de carga</li><li>Recebimento (e armazenamento) da linha da ordem de compra</li><li>Recebimento (e armazenamento) do item da ordem de compra</li></ul> |

Para configurar uma política de trabalho de forma que ela se aplique a vários processos de trabalho do mesmo tipo de ordem de trabalho, adicione uma linha separada para cada processo de trabalho à grade.

Para cada linha da grade, defina o campo **Método de criação de trabalho** com um dos seguintes valores:

- **Nunca** – a política de trabalho impedirá que o trabalho de depósito seja criado para o tipo de ordem de trabalho selecionado e o processo de trabalho relacionado.
- **Distribuição integrada** – a política de trabalho criará o trabalho de distribuição integrada usando a política selecionada no campo **Nome da política de distribuição integrada**.

### <a name="the-inventory-locations-fasttab"></a>A FastTab Localizações de estoque

Na FastTab **Localizações de estoque**, adicione todos os locais onde a política de trabalho deve ser aplicada. Se nenhuma localização for associada à política de trabalho, ela não será aplicada a nenhum processo.

Não é possível especificar a mesma localização para várias políticas de trabalho.

Você pode usar uma localização de depósito atribuída a um perfil de localização, em que a opção **Usar rastreamento da placa de licença** está desativada. Nesse caso, os trabalhadores registrarão diretamente o estoque disponível.

### <a name="the-products-fasttab"></a>A FastTab Produtos

Na guia **Produtos**, defina o campo **Seleção de produtos** para controlar os produtos aos quais a política deve se aplicar:

- **Tudo** – a política deve ser aplicada a todos os produtos.
- **Selecionado** – a política deve se aplicar somente a produtos listados na grade. Use a barra de ferramentas na FastTab **Produtos** para adicionar produtos à grade ou para removê-los da grade.

## <a name="default-and-custom-to-locations"></a>Locais "de destino" padrão e personalizados

> [!NOTE]
> Para disponibilizar a funcionalidade descrita nesta seção no sistema, você deve ativar os recursos *Aprimoramentos de recebimento da placa de licença* e os *Aprimoramentos de política de trabalho para trabalho de entrada* no [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Anteriormente, o sistema tem suporte para receber somente no local padrão definido para cada depósito. Entretanto, os itens de menu de dispositivo móvel que usam os processos de criação de trabalho a seguir agora fornecem a opção **Usar dados padrão**. Esta opção permite atribuir um local "de destino" personalizado a um ou mais itens de menu. (Esta opção já estava disponível para alguns outros tipos de itens de menu.)

- Recebimento (e armazenamento) da placa de licença
- Recebimento (e armazenamento) do item de carga
- Recebimento (e armazenamento) da linha da ordem de compra
- Recebimento (e armazenamento) do item da ordem de compra

A configuração **Local de destino** para um item de menu substitui o local de recebimento padrão para o depósito, para todas as ordens que são processadas usando esse item de menu.

Para configurar um item de menu de dispositivo móvel para dar suporte ao recebimento em um local personalizado, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Selecione ou crie um item de menu que use um dos processos de criação de trabalho listados anteriormente nesta seção.
1. Na FastTab **Geral**, defina a opção **Usar dados padrão** como **Sim**.
1. No Painel de Ações, selecione **Dados padrão**.
1. Na página **Dados padrão**, defina os seguintes valores:

    - **Campo de dados padrão:** defina este campo como *Local de destino*.
    - **Depósito:** selecione o depósito de destino a ser usado com este item de menu.
    - **Local:** este campo lista todas as IDs de local que estão disponíveis para o depósito selecionado. No entanto, a configuração deste campo não terá efeito. Portanto, você pode deixá-lo em branco. No entanto, você pode usar a lista para confirmar a ID que deve ser inserida no campo **Valor codificado**.
    - **Valor codificado:** insira a ID de local para o local de recebimento que se aplica a este item de menu.

> [!TIP]
> Uma política de trabalho só poderá ser aplicada se todos os locais de recebimento estiverem listados na configuração da política de trabalho relevante. Esse requisito se aplica independentemente de você estar usando o local de recebimento do depósito padrão ou um local "de destino" personalizado.

## <a name="example-scenario-warehouse-receiving"></a>Cenário de exemplo: recebimento de depósito

Todos os produtos recebidos pelo processo *Recebimento (e armazenamento) de itens da ordem de compra* devem ser registrados no local *FL-001* e serem disponibilizados no depósito *24*. Mas, o trabalho não deve ser criado. Os produtos recebidos por qualquer outro processo (ou seja, usando outros itens de menu de dispositivo móvel) devem ser registrados no local de recebimento do depósito padrão (*RECV*) e o trabalho deve ser criado como de costume. (Esse cenário não mostra a configuração de recebimento padrão.)

Este cenário exige os seguintes elementos:

- Uma política de trabalho para o processo *Recebimento (e armazenamento) de itens da ordem de compra* no local *FL-001* para todos os produtos
- Um item de menu de dispositivo móvel com dados padrão e que defina o campo **Local de destino** como *FL-001*

### <a name="prerequisites"></a>Pré-requisitos

Para disponibilizar a funcionalidade descrita neste cenário no sistema, você deve ativar os recursos *Aprimoramentos de recebimento da placa de licença* e os *Aprimoramentos de política de trabalho para trabalho de entrada* no [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Este cenário usa os dados de demonstração padrão. Então, se desejar trabalhar usando os valores fornecidos aqui, trabalhe em um sistema em que os dados de demonstração estejam instalados. Além disso, você deve selecionar a entidade legal **USMF**.

### <a name="set-up-a-work-policy"></a>Configurar uma política de trabalho

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Políticas de trabalho**.
1. Selecione **Novo**.
1. No campo **Nome da política de trabalho**, digite *Nenhum trabalho de armazenamento de item de compra*.
1. Selecione **Salvar**.
1. Na FastTab **Tipos de ordem de trabalho**, selecione **Adicionar** para adicionar uma linha à grade e, em seguida, defina os seguintes valores para a nova linha:

    - **Tipo de ordem de trabalho:** *Ordens de compra*
    - **Processo de trabalho:** *Recebimento (e armazenamento) de item da ordem de compra*
    - **Método de criação de trabalho:** *Nunca*
    - **Nome da política de distribuição integrada:** deixe este campo em branco.

1. Na FastTab **Locais de estoque**, selecione **Adicionar** para adicionar uma linha à grade e, em seguida, defina os seguintes valores para a nova linha:

    - **Depósito:** *24*
    - **Local:** *FL-001*

1. Na FastTab **Produtos**, defina o campo **Seleção de produtos** como *Todos*.
1. Selecione **Salvar**.

### <a name="set-up-a-mobile-device-menu-item-to-change-the-receiving-location"></a>Configurar um item de menu do dispositivo móvel para alterar o local de recebimento

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No painel esquerdo, selecione o item de menu **Recebimento de compra** existente.
1. Na FastTab **Geral**, defina a opção **Usar dados padrão** como *Sim*.
1. Selecione **Salvar**.
1. No Painel de Ações, selecione **Dados padrão**.
1. Na página **Dados padrão**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade e, em seguida, defina os seguintes valores para a nova linha:

    - **Campo de dados padrão:** *Local de destino*
    - **Depósito:** *24*
    - **Local:** deixe este campo em branco.
    - **Valor codificado:** *FL-001*

1. Selecione **Salvar**.

### <a name="receive-a-purchase-order-without-creating-work"></a>Receber uma ordem de compra sem criar trabalho

O exemplo desta seção mostra como receber um item de ordem de compra, mas sem criar trabalho, em um local diferente do local de recebimento padrão configurado para o depósito. Este exemplo usa a política de trabalho e o item de dispositivo móvel que você criou antes neste cenário.

#### <a name="create-a-purchase-order"></a>Criar uma ordem de compra

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:

    - **Conta do fornecedor:** *US-101*
    - **Local:** *2*
    - **Depósito:** *24*

1. Selecione **OK** para fechar a caixa de diálogo e abrir a nova ordem de compra.
1. Na FastTab **Linhas da ordem de compra**, defina os seguintes valores para a linha vazia:

    - **Número de item:** *A0001*
    - **Quantidade:** *1*

1. Selecione **Salvar**.
1. Anote o número da ordem de compra.

#### <a name="receive-a-purchase-order"></a>Receber uma ordem de compra

1. No dispositivo móvel, entre no depósito *24* usando *24* como a ID de usuário e *1* como a senha.
1. Selecione **Entrada**.
1. Selecione **Recebimento de compra**. O campo **Local** deve ser definido como *FL-001*.
1. Insira o número da ordem de compra para a ordem de compra criada no procedimento anterior.
1. No campo **Número do item**, insira *A0001*.
1. Selecione **OK**.
1. No campo **Quantidade**, insira *1*.
1. Selecione **OK**.

A ordem de compra é recebida agora, mas nenhum trabalho está associado a ela. O estoque disponível foi atualizado e uma quantidade *1* do item *A0001* está disponível no local *FL-001*.

## <a name="example-scenario-manufacturing"></a>Cenário de exemplo: fabricação

No exemplo a seguir, há duas ordens de produção, *PRD-001* e *PRD-002*. A ordem de produção *PRD-001* tem uma operação que é chamada *Montagem*, em que o produto *SC1* está sendo relatado como acabado para o local *001*. A ordem de produção *PRD-002* tem uma operação que é chamada *Pintura* e consome o produto *SC1* do local *001*. A ordem de produção *PRD-002* também consome a matéria-prima *RM1* do local *001*. A matéria-prima *RM1* é armazenada na localização de depósito *BULK-001* e será separada para o local *001* pelo trabalho de depósito para a separação de matéria-prima. O trabalho de separação será gerado quando a produção *PRD-002* for liberada.

[![Políticas de trabalho de depósito](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)

Quando você pretender configurar uma política de trabalho de depósito para este cenário, considere os seguintes pontos:

- O trabalho de depósito para o armazenamento de mercadorias acabadas não é necessário quando você relata o produto *SC1* como acabado da ordem de produção *PRD-001* para o local *001*. O motivo é que operação *Pintura* para a ordem de produção *PRD-002* consome o produto *SC1* no mesmo local.
- O trabalho de depósito para a separação de matéria-prima é necessário para mover a matéria-prima *RM1* da localização de depósito *BULK-001* para o local *001*.

Veja um exemplo de política de trabalho que você pode configurar com base nestas considerações:

- **Nome da política de trabalho:** *sem trabalho de armazenamento*
- **Tipos de ordem de trabalho:** *Armazenamento de mercadorias acabadas* e *Armazenamento de coproduto e subproduto*
- **Locais de estoque:** depósito *51* e local *001*
- **Produtos:** *SC1*

O exemplo de cenário a seguir fornece instruções passo a passo para configurar a política de trabalho de depósito para este cenário.

## <a name="example-scenario-report-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Exemplo de cenário: relatar como acabado para um local que não seja controlado por placa de licença

Este cenário mostra um exemplo em que uma ordem de produção é relatada como acabada para um local que não é controlado por placa de licença.

Este cenário usa os dados de demonstração padrão. Então, se desejar trabalhar usando os valores fornecidos aqui, trabalhe em um sistema em que os dados de demonstração estejam instalados. Além disso, você deve selecionar a entidade legal **USMF**.

### <a name="set-up-a-warehouse-work-policy"></a>Configurar uma política de trabalho de depósito

Os processos de depósito nem sempre incluem o trabalho do depósito. Ao definir uma política de trabalho, você pode impedir a criação de trabalho para a separação de matéria-prima e o armazenamento de mercadorias acabadas para um conjunto de produtos em locais específicos.

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Políticas de trabalho**.
1. Selecione **Novo**.
1. No campo **Nome da política de trabalho**, insira *Nenhum trabalho de armazenamento*.
1. No Painel de ações, selecione **Salvar**.
1. Na FastTab **Tipos de ordem de trabalho**, selecione **Adicionar** para adicionar uma linha à grade e, em seguida, defina os seguintes valores para a nova linha:

    - **Tipo de ordem de trabalho:** *Armazenamento de mercadorias acabadas*
    - **Processo de trabalho:** *todos os processos de trabalho relacionados*
    - **Método de criação de trabalho:** *Nunca*
    - **Nome da política de distribuição integrada:** deixe este campo em branco.

1. Selecione novamente **Adicionar** para adicionar uma segunda linha à grade e, depois, defina os seguintes valores para a nova linha:

    - **Tipo de ordem de trabalho:** *Armazenamento de coproduto e subproduto*
    - **Processo de trabalho:** *todos os processos de trabalho relacionados*
    - **Método de criação de trabalho:** *Nunca*
    - **Nome da política de distribuição integrada:** deixe este campo em branco.

1. Na FastTab **Locais de estoque**, selecione **Adicionar** para adicionar uma linha à grade e, em seguida, defina os seguintes valores para a nova linha:

    - **Depósito:** *51*
    - **Local:** *001*

1. Na FastTab **Produtos**, defina o campo **Seleção de produtos** como *Selecionado*.
1. Na FastTab **Produtos**, selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina o campo **Número do item** como *L0101*.
1. No Painel de ações, selecione **Salvar**.

### <a name="set-up-an-output-location"></a>Configurar uma localização de saída

1. Vá para **Administração da organização \> Recursos \> Grupos de recursos**.
1. No painel esquerdo, selecione o grupo de recursos **5102**.
1. Na FastTab **Geral**, defina os seguintes valores:

    - **Depósito de saída:** *51*
    - **Local de saída:** *001*

1. No Painel de ações, selecione **Salvar**.

> [!NOTE]
> O local *001* não é um local controlado por placa de licença. Você poderá configurar um local de saída que não seja controlado por placa de licença somente se existir uma política de trabalho para o local.

### <a name="create-a-production-order-and-report-it-as-finished"></a>Criar uma ordem de produção e relatar quando estiver concluída

1. Vá para **Controle de produção \> Ordens de produção \> Todas ordens de produção**.
1. No Painel de Ações, selecione **Nova ordem de produção**.
1. Na caixa de diálogo **Criar ordem de produção**, defina o campo **Número do item** como *L0101*.
1. Selecione **Criar** para criar a ordem e feche a caixa de diálogo.

    Uma nova ordem de produção é adicionada à grade na página **Todas as ordens de produção**.

    Mantenha a nova ordem de produção selecionada.

1. No Painel de Ações, na guia **Ordem de produção**, no grupo **Processo**, selecione **Estimar**.
1. Na caixa de diálogo **Estimar**, leia a estimativa e, depois, selecione **OK** para fechar a caixa de diálogo.
1. No Painel de Ações, na guia **Ordem de produção**, no grupo **Processo**, selecione **Iniciar**.
1. Na caixa de diálogo **Iniciar**, na guia **Geral**, defina o campo **Consumo automático de BOM** como *Nunca*.
1. Selecione **OK** para salvar sua configuração e feche a caixa de diálogo.
1. No Painel de Ações, na guia **Ordem de produção**, no grupo **Processar**, selecione **Relatar como concluído**.
1. Na caixa de diálogo **Relatar como concluído**, na guia **Geral**, defina a opção **Aceitar erro** como *Sim*.
1. Selecione **OK** para salvar sua configuração e feche a caixa de diálogo.
1. No Painel de Ação, na guia **Depósito**, no grupo **Geral**, selecione **Detalhes do trabalho**.

Quando a ordem de produção é relatada como concluída, nenhum trabalho é gerado para armazenamento. Esse comportamento ocorre porque uma política de trabalho é definida que impede que o trabalho seja gerado quando o produto *L0101* é relatado como concluído no local *001*.

## <a name="more-information"></a>Mais informações

Para obter mais informações sobre itens do menu do dispositivo móvel, consulte [Configurar dispositivos móveis para trabalho de depósito](configure-mobile-devices-warehouse.md).

Para obter mais informações sobre o recebimento da placa de licença e políticas de trabalho, consulte [Recebimento da placa de licença por meio do aplicativo de depósito](warehousing-mobile-device-app-license-plate-receiving.md).

Para obter mais informações sobre o gerenciamento de carga de entrada, consulte [Manuseio de depósito de cargas de entrada para ordens de compra](inbound-load-handling.md).
