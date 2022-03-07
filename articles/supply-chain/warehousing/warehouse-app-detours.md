---
title: Configurar desvios para as etapas nos itens de menu do dispositivo móvel
description: Este tópico descreve como configurar desvios para itens de menu de modo que os trabalhadores possam estacionar a tarefa atual, executar outra tarefa e retornar à tarefa original sem perder nenhuma informação.
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
ms.openlocfilehash: 536fe2fa8819129f14e31ff966ab2349f836f0f7
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902112"
---
# <a name="configure-detours-for-steps-in-mobile-device-menu-items"></a>Configurar desvios para as etapas nos itens de menu do dispositivo móvel

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until GA with 10.0.23 -->

> [!IMPORTANT]
> Os recursos descritos neste tópico se aplicam apenas ao novo aplicativo móvel Warehouse Management. Eles não afetam o antigo aplicativo de depósito, que foi preterido.

Este tópico descreve como configurar desvios para itens de menu de modo que os trabalhadores possam "estacionar" a tarefa atual, executar outra tarefa e retornar à tarefa original sem perder nenhuma informação.

Um desvio é um item de menu separado que pode ser aberto a partir de uma etapa em uma tarefa principal. No final do desvio, o trabalhador será devolvido para o local de onde eles saíram da tarefa principal. Durante a configuração, você especifica o item de menu que deve atuar como desvio. Você também seleciona quais valores de campo da tarefa principal devem ser encaminhados automaticamente (copiados) para o desvio e inseridos ali. Portanto, você deve entender onde no fluxo de tarefas deseja que o desvio esteja disponível para trabalhadores. Você também deve garantir que as informações que devem ser copiadas para o desvio estão disponíveis para essa etapa do fluxo de tarefas.

## <a name="enable-detours-in-your-system"></a>Habilitar desvio no sistema

Antes de configurar os desvios para etapas em itens de menu de dispositivo móvel, você deverá concluir o procedimento a seguir para habilitar os recursos necessários e gerar os nomes de campos necessários no aplicativo móvel do Warehouse Management.

1. Acesse **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.
1. No [espaço de trabalho **Gerenciamento de recursos**](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), habilite o recurso listado da seguinte forma:

    - **Módulo:** *Gerenciamento de depósito*
    - **Nome do recurso:** *instruções de etapa do aplicativo Warehouse*

    Para obter mais informações sobre o recurso *Instruções de etapa do aplicativo do Warehouse*, consulte [Personalizar títulos de etapas e instruções para o aplicativo móvel do Warehouse Management](mobile-app-titles-instructions.md). Esse recurso é um pré-requisito para o recurso *Desvios do aplicativo do Warehouse Management*.

1. Habilite o recurso listado da seguinte maneira:

    - **Módulo:** *Gerenciamento de depósito*
    - **Nome do recurso:** *desvios do aplicativo do Warehouse Management*

    Esse recurso é o descrito neste tópico.

1. Atualize os nomes de campo no aplicativo móvel do Warehouse Management acessando **Warehouse management \> Configuração \> Dispositivo móvel \> Nomes de campo do aplicativo do Warehouse** e selecionando **Criar configuração padrão**. Para obter mais informações, consulte [Configurar campos para o aplicativo móvel Warehouse Management](configure-app-field-names-priorities-warehouse.md).
1. Repita a etapa anterior para cada entidade legal (empresa) em que você usa o aplicativo móvel do Warehouse Management.

## <a name="configure-a-detour-from-a-menu-specific-override"></a>Configurar um desvio de uma substituição específica de menu

Use o procedimento a seguir para configurar um desvio de uma substituição específica do menu.

1. Crie uma substituição específica do menu para o menu e a etapa relevantes conforme descrito em [Personalizar títulos e instruções de etapas para o aplicativo móvel do Warehouse Management](mobile-app-titles-instructions.md).
1. Encontre a combinação de valores de **ID da Etapa** e **Nome do item de menu** que deseja editar e então selecione o valor na coluna **ID da Etapa**.
1. Na página exibida, na Guia Rápida **Desvios disponíveis (itens de menu)**, você pode especificar o item de menu que deve atuar como desvio. Você também seleciona quais valores de campo da tarefa principal devem ser copiados automaticamente de e para o desvio. Para obter exemplos que mostrem como usar essas configurações, consulte os cenários posteriormente neste tópico.

## <a name="sample-scenario-1-sales-picking-where-a-location-inquiry-acts-as-a-detour"></a>Cenário de exemplo 1: Separação de vendas em que uma consulta de localização atua como desvio

Este cenário mostra como configurar uma consulta de localização como um desvio em um fluxo de tarefas de separação de vendas direcionada ao trabalhador. Esse desvio permitirá que os funcionários pesquisem todas as placas de licença no local de onde eles estão separando e separem a placa de licença que queiram usar para concluir a separação. Esse tipo de desvio poderá ser útil se o código de barras estiver danificado e, portanto, ilegível para o dispositivo de scanner. Como alternativa, ele poderia ser útil se um trabalhador tivesse de aprender o que está realmente disponível no sistema. Observe que esse cenário só funcionará se você estiver separando dos locais controlados pela placa de licença.

### <a name="enable-sample-data"></a>Habilitar dados de exemplo

Para usar os registros e valores de exemplo especificados para trabalhar neste cenário, você deverá usar um sistema em que os dados de demonstração padrão estejam instalados. Você também deve selecionar a entidade legal **USMF** antes de começar.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-1"></a>Crie uma substituição específica do menu e configure o desvio para o cenário 1

Neste procedimento, você vai configurar um desvio para o item de menu **Separação de vendas** na etapa da placa de licença.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Etapas do dispositivo móvel**.
1. Localize a ID da etapa chamada *LicensePlateId* e selecione-a.
1. No Painel de Ações, selecione **Adicionar configuração de etapa**.
1. Na caixa de diálogo suspensa, use o campo **Item de menu** para localizar e selecione *Separação de vendas*.
1. Selecione **OK**.
1. A página de detalhes da substituição que você acabou de criar aparecerá. Na Guia Rápida **Desvios disponíveis (itens de menu)**, selecione **Adicionar** na barra de ferramentas.
1. Na caixa de diálogo **Adicionar desvio**, selecione **Consulta de localização** como o desvio que será disponibilizado no aplicativo móvel do Warehouse Management.
1. Selecione **OK**.
1. Na Guia Rápida **Desvios disponíveis (itens de menu)**, selecione o desvio que você acabou de adicionar e, em seguida, selecione **Selecionar campos a serem enviados** na barra de ferramentas.
1. Na caixa de diálogo **Selecionar campos para enviar**, especifique as informações que devem ser enviadas de e para o desvio. Neste cenário, você está permitindo que os funcionários usem o local no qual devem ser selecionados como entrada para o desvio de consulta de localização. Portanto, na seção **Enviar de separação de vendas**, selecione **Adicionar** na barra de ferramentas para adicionar uma linha à grade. Defina os seguintes valores para a nova linha:

    - **Copiar da Separação de Vendas:** *Localização*
    - **Cole em Consulta de Localização:** *Localização*

1. Como o desvio neste cenário é configurado na etapa da placa de licença, ele será útil se os funcionários puderem trazer a placa de licença de volta da consulta para o fluxo principal. Portanto, na seção **Trazer de volta da consulta de localização**, selecione **Adicionar** na barra de ferramentas para adicionar uma linha à grade. Defina os seguintes valores para a nova linha:

    - **Copie de Consulta de Localização:** *Placa de licença*
    - **Colar na Separação de Vendas:** *Placa de licença*

1. Selecione **OK**.

Agora, o desvio está totalmente configurado. Um botão para iniciar o desvio **Consulta de localização** aparecerá agora na etapa da placa de licença para o item de menu **Separação de vendas**.

### <a name="complete-a-sales-pick-on-a-mobile-device-and-use-the-detour"></a>Concluir uma separação de vendas em um dispositivo móvel e usar o desvio

Neste procedimento, você concluirá uma separação de vendas usando o aplicativo móvel do Warehouse Management. Você usará o desvio que acabou de configurar para localizar a placa de licença que será usada para concluir a etapa de separação.

1. No Microsoft Dynamics 365 Supply Chain Management, crie uma ordem de venda que exigirá uma etapa de seleção para separar de um local rastreado na placa de licença. Em seguida, libere a ordem de venda para o depósito. Anote a ID do trabalho gerada.
1. Abra o aplicativo móvel do Warehouse Management e entre no depósito 24. (Nos dados de demonstração padrão, entre usando *24* como a ID do usuário e *1* como a senha.)
1. Selecione o menu **Saída** e selecione o item de menu **Separação de vendas**.
1. Siga as instruções de entrada de dados na tela para inserir a ID do trabalho que foi gerada na etapa 1.
1. Na etapa que contém o texto **Digitalizar uma placa de licença**, abra o menu de ações. Você verá um novo botão com o rótulo **Consulta de localização**. Uma seta no canto superior esquerdo indica que o botão iniciará um desvio. Selecione **Consulta de localização**.
1. O desvio é iniciado. Na página seguinte, confirme a localização que foi copiada do fluxo principal.
1. Na lista de placas de licença disponíveis na localização, toque na placa de licença que você deseja copiar novamente para o fluxo principal. Em seguida, selecione o botão **Voltar**.
1. Você será devolvido ao fluxo principal de separação de vendas e a placa de licença foi copiada de volta para ele desde o desvio. Confirme o valor para prosseguir para a próxima etapa.
1. Agora você pode concluir o restante do fluxo padrão inserindo as instruções de entrada de dados solicitadas.

Agora, o trabalho de depósito está concluído. O trabalho abriu com êxito um desvio para executar uma tarefa secundária (consulta de localização) sem perder seu lugar na tarefa principal e colocou novamente as informações necessárias para concluir a tarefa principal.

## <a name="sample-scenario-2-item-inquiry-with-movement-and-adjustment-detours"></a>Cenário 2: Consulta de item com desvios de movimento e de ajuste

Este cenário mostra como configurar o movimento e os ajustes como vários desvios no fluxo de tarefas de consulta da localização. Essa funcionalidade pode ser útil em situações nas quais um trabalhador chega em um local, descobre que o estoque no local é diferente do que está registrado no sistema e, portanto, deve ajustar ou mover mercadorias.

Você pode substituir a consulta de localização por uma consulta de placa de licença ou uma consulta de item conforme necessário.

### <a name="enable-sample-data"></a>Habilitar dados de exemplo

Para usar os registros e valores de exemplo especificados para trabalhar neste cenário, você deverá usar um sistema em que os dados de demonstração padrão estejam instalados. Você também deve selecionar a entidade legal **USMF** antes de começar.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-2"></a>Crie uma substituição específica do menu e configure o desvio para o cenário 2

Neste procedimento, você vai configurar um desvio para o item de menu **Separação de vendas** na etapa da placa de licença.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Etapas do dispositivo móvel**.
1. Localize e selecione a ID da etapa chamada *LocationInquiryList*.

    > [!NOTE]
    > Para usar uma consulta de item em vez de uma consulta de localização, selecione uma linha na qual a ID da etapa chama-se *ItemInquiryList*. Para usar uma consulta de placa de licença, selecione uma linha em que a ID da etapa chama-se *LPInquiryList*.

1. No Painel de Ações, selecione **Adicionar configuração de etapa**.
1. Na caixa de diálogo suspensa, use o campo **Item de menu** para localizar e selecione *Consulta de localização*.
1. Selecione **OK**.
1. A página de detalhes da substituição que você acabou de criar aparecerá. Na Guia Rápida **Desvios disponíveis (itens de menu)**, selecione **Adicionar** na barra de ferramentas.
1. Na caixa de diálogo **Adicionar desvio**, selecione **Movimento** como o desvio que será disponibilizado no aplicativo móvel do Warehouse Management.
1. Selecione **OK**.
1. Na Guia Rápida **Desvios disponíveis (itens de menu)**, selecione o desvio que você acabou de adicionar e, em seguida, selecione **Selecionar campos a serem enviados** na barra de ferramentas.
1. No diálogo **Selecionar campos para enviar**, especifique as informações que devem ser enviadas de e para o desvio. Neste cenário, espera-se que os trabalhadores procurem os locais controlados por placa de licença. Portanto, será útil copiar a placa de licença da consulta para o desvio **Movimento**. Na seção **Enviar de separação de vendas**, selecione **Adicionar** na barra de ferramentas para adicionar uma linha à grade. Defina os seguintes valores para a nova linha:

    - **Copie de Consulta de Localização:** *Localização*
    - **Cole em Movimento:** *Loc/LP*

    Neste desvio, você não está esperando que as informações sejam copiadas de volta, já que o fluxo principal era uma consulta sem etapas adicionais necessárias.

1. Selecione **OK**.

Agora, o desvio está totalmente configurado. Um botão para iniciar o desvio **Movimento** aparecerá agora na etapa da placa de licença para o item de menu **Consulta de localização**.

### <a name="do-a-location-inquiry-on-a-mobile-device-and-use-the-detour"></a>Fazer uma consulta de localização em um dispositivo móvel e usar o desvio

Neste procedimento, você fará uma consulta de localização usando o aplicativo móvel do Warehouse Management. Em seguida, você usará o desvio para concluir uma movimentação de bens.

1. Abra o aplicativo móvel do Warehouse Management e entre no depósito 24. (Nos dados de demonstração padrão, entre usando *24* como a ID do usuário e *1* como a senha.)
1. Selecione o menu **Estoque** e selecione o item de menu **Consulta de localização**.
1. Insira uma localização para consulta, por exemplo, *FL-001*.
1. Quando a lista for exibida, toque e segure em um dos cartões nela para mostrar os desvios disponíveis.
1. Selecione **Movimento**.
1. Observe que a placa de licença foi copiada do cartão selecionado. Confirme o valor.
1. Agora você pode seguir o fluxo de tarefas padrão para concluir o movimento. Depois que o trabalho for concluído, abra o menu de ações e selecione **Cancelar**.
1. Você retornará à página **Consulta de localização**. Observe que os valores não são atualizados automaticamente. Portanto, você deverá atualizar manualmente a página para ver as alterações do desvio de movimento.
