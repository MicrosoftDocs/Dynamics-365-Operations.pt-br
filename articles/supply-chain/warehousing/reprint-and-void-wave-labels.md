---
title: Reimprimir e anular etiquetas de onda
description: Este tópico explica como anular e reimprimir etiquetas de onda existentes.
author: perlynne
ms.date: 07/09/2020
ms.topic: article
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSWaveTableListPage, WHSWorkException, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelLayout, WHSWaveLabelType, WHSWaveLabelTemplateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-07-09
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: caba37d3e7bb5d2f08a8c10ff0f0e1bc886e5648
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102749"
---
# <a name="reprint-and-void-wave-labels"></a>Reimprimir e anular etiquetas de onda

[!include [banner](../includes/banner.md)]

Este tópico explica como gerenciar etiquetas geradas pelo processamento de ondas. (Para obter uma descrição detalhada e instruções de configuração, consulte [Configurar a impressão de etiquetas de onda](../warehousing/configure-wave-label-printing.md) .)

Você pode reimprimir etiquetas de onda a qualquer momento. Por exemplo, talvez você precise imprimir uma única etiqueta se uma etiqueta existente foi perdida ou danificada. Como alternativa, um funcionário ou supervisor de depósito pode ter que reimprimir um rolo inteiro de etiquetas se o número e/ou a composição de uma série inteira de etiquetas de onda for alterada (por exemplo, devido a escassez de estoque ou outros motivos). Geralmente, mesmo que somente o número de caixas tenha sido alterado, o rolo todo deve ser reimpresso para manter o número total preciso na seção "Caixa X de Y" de cada etiqueta.

O recurso de reimpressão de etiquetas de onda oferece suporte às seguintes funcionalidades:

- Reimprimir etiquetas do aplicativo de depósito e do cliente avançado.
- Anular etiquetas e reimprimi-las simultaneamente. (A capacidade de anular etiquetas é incorporada a cenários de separação insuficiente, por exemplo.)
- Limpar o histórico de etiquetas de onda.

Este tópico apresenta um conjunto de cenários que mostram, por meio de exemplos, como trabalhar com o recurso de reimpressão de etiquetas de ondas.

> [!IMPORTANT]
> Para trabalhar nos cenários apresentados neste tópico, você deve primeiramente ativar e configurar os recursos de impressão de onda relevantes, conforme descrito em [Configurar a impressão de etiquetas de onda](../warehousing/configure-wave-label-printing.md). Vários cenários neste tópico também exigem que você trabalhe primeiro com os cenários neste tópico para gerar os dados de exemplo de pré-requisito.

## <a name="scenario-1-reprint-labels-from-the-web-client"></a>Cenário 1: reimprimir etiquetas por meio do cliente Web

Você pode exibir e reimprimir etiquetas de onda nas páginas a seguir. No Painel de Ações de cada página, na guia **Remessas**, no grupo **Informações relacionadas**, selecione **Etiquetas de onda**.

- Todas as remessas \> Detalhes da remessa
- Todas as cargas \> Detalhes da carga
- Todas as ondas
- Etiquetas de onda
- Histórico da etiqueta de onda

Para reimprimir uma etiqueta de onda por meio do cliente Web, siga estas etapas:

1. Vá para **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione a onda da qual deseja reimprimir as etiquetas.
1. No Painel de Ações, na guia **Onda**, no grupo **Imprimir**, selecione **Etiquetas de onda**.
1. Siga uma ou ambas as etapas a seguir:

    - Para reimprimir a etiqueta, selecione a impressora no campo **Nome da impressora**. (Deixe esse campo em branco se você quiser apenas atualizar os detalhes da etiqueta de onda, sem reimprimir a etiqueta.)
    - Para atualizar a etiqueta, marque a caixa de seleção **Atualizar detalhes da etiqueta de onda**. (Deixe essa caixa de seleção desmarcada se você quiser apenas imprimir a etiqueta anterior.)

    > [!NOTE]
    > Toda vez que uma etiqueta de onda é impressa ou reimpressa, seus dados são convertidos por meio do layout da etiqueta de onda apropriado e todos os espaços reservados são substituídos pelos valores reais. A cadeia de caracteres resultante é armazenada como um registro no histórico de etiquetas de onda. Se a caixa de seleção **Atualizar detalhes da etiqueta de onda** estiver desmarcada, os dados armazenados linguagem de programação zebra (ZPL) serão usados quando uma etiqueta for reimpressa. Se a caixa de seleção **Atualizar detalhes da etiqueta de onda** estiver marcada, será gerada uma nova cadeia de caracteres. As etiquetas de onda existentes também serão recalculadas e quaisquer etiquetas em excesso (por exemplo, se as linhas de trabalho relacionadas foram canceladas ou modificadas) serão marcadas como **Anuladas** e não são reimpressas.

1. Selecione **OK** para confirmar a seleção.

## <a name="scenario-2-reprint-labels-from-the-warehousing-app"></a>Cenário 2: reimprimir etiquetas por meio do aplicativo de depósito

Esse cenário geralmente se aplica se um rolo de etiquetas tiver sido perdido ou danificado. Ele fornece um exemplo que mostra como configurar itens de menu do dispositivo móvel que permitirão que os funcionários reimprimam etiquetas únicas e várias etiquetas. Em seguida, ele mostra como usar esses novos itens de menu enquanto você estiver trabalhando em um dispositivo móvel.

### <a name="set-up-the-required-menu-items-and-menu-for-the-mobile-device"></a>Configurar os itens de menu e o menu necessários para o dispositivo móvel

Antes que os trabalhadores possam reimprimir etiquetas por meio de um dispositivo móvel, você deve configurar itens de menu para fornecer essa funcionalidade e, depois, adicionar esses itens ao menu do aplicativo de depósito.

#### <a name="create-new-mobile-device-menu-items"></a>Crie novos itens de menu de dispositivo móvel

Siga estas etapas para criar uma nova coleção de itens de menu para reimprimir etiquetas por meio do aplicativo de depósito.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Crie um item de menu e defina os seguintes valores para ele:

    - **Nome do item de menu:** *Reimprimir etiqueta de onda única*
    - **Título:** *Reimprimir etiqueta de onda única*
    - **Modo:** *Indireto*
    - **Código da atividade:** *Reimprimir etiqueta de onda única*

1. Crie um segundo item de menu e defina os seguintes valores para ele:

    - **Nome do item de menu:** *Reimprimir etiquetas (Item)*
    - **Título:** *Reimprimir etiquetas de onda (Item)*
    - **Modo:** *Indireto*
    - **Código da atividade:** *Reimprimir várias etiquetas de onda*
    - **Exibir filtro de agrupamento de lista de trabalho:** *Sim*
    - **Campo de agrupamento do sistema:** *ShipmentID*
    - **Etiqueta de agrupamento do sistema:** *ShipmentID*
    - **Modo de impressão:** *Produto*

1. No Painel de Ações, selecione **Lista de campos** para abrir uma página na qual é possível selecionar os campos que serão mostrados para ajudar os funcionários a identificar o rolo de etiquetas correto.
1. Você pode exibir até sete campos. Use as listas suspensas para selecionar o campo que será mostrado em cada posição disponível. Deixe os campos que não são necessários em branco. 

    Este é um exemplo:

    - **Campo de exibição:** *LabelItemId*
    - **Campo de exibição 2:** *LabelItemName*
    - **Campo de exibição 3:** *InventQty*
    - **Campo de exibição 4:** *LabelUnitId*

1. Feche a página.
1. Crie um terceiro item de menu e defina os seguintes valores para ele:

    - **Nome do item de menu:** *Reimprimir etiquetas (Enumeração)*
    - **Título:** *Reimprimir etiquetas de onda (Enumeração)*
    - **Modo:** *Indireto**
    - **Código da atividade:** *Reimprimir várias etiquetas de onda*
    - **Exibir filtro de agrupamento de lista de trabalho:** *Sim*
    - **Campo de agrupamento do sistema:** *ShipmentID*
    - **Etiqueta de agrupamento do sistema:** *ShipmentID*
    - **Modo de impressão:** *Enumeração*

1. No Painel de Ações, selecione **Lista de campos** e use as listas suspensas para selecionar os campos que serão mostrados para ajudar os funcionários a identificar o rolo de etiquetas correto (por exemplo, *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* e *NumberOfLabels*).
1. Feche a página.
1. Crie um quarto item de menu e defina os seguintes valores para ele:

    - **Nome do item de menu:** *Reimprimir etiquetas (pela última)*
    - **Título:** *Reimprimir etiquetas de onda (pela última)*
    - **Modo:** *Indireto*
    - **Código da atividade:** *Reimprimir várias etiquetas de onda*
    - **Exibir filtro de agrupamento de lista de trabalho:** *Sim*
    - **Campo de agrupamento do sistema:** *ShipmentID*
    - **Etiqueta de agrupamento do sistema:** *ShipmentID*
    - **Modo de impressão:** *Última ID de etiqueta de onda da mercadoria*

1. No Painel de Ações, selecione **Lista de campos** e use as listas suspensas para selecionar os campos que serão mostrados para ajudar os funcionários a identificar o rolo de etiquetas correto (por exemplo, *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* e *NumberOfLabels*).
1. Feche a página.

#### <a name="set-up-the-mobile-device-menu"></a>Configura o menu de dispositivo móvel

Siga estas etapas para adicionar os novos itens de menu ao menu de aplicativo de depósito.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. Selecione um menu de **Saída** existente.
1. Na lista à esquerda, localize os itens de menu para reimpressão que você acabou de criar e use o botão de seta para a direita para adicioná-los à lista à direita.
1. Feche a página.

### <a name="use-cases"></a>Casos de uso

Os casos de uso fornecidos aqui oferecem exemplos que mostram como usar os vários itens de menu do dispositivo móvel configurados para permitir que os trabalhadores reimprimam etiquetas de onda.

Antes de trabalhar com esses casos de uso, os seguintes pré-requisitos devem ser atendidos:

- Os dados de demonstração devem estar instalados e você deve selecionar a entidade legal **USMF**.
- A impressão de etiquetas de onda deve estar configurada, e algumas etiquetas devem ser geradas, conforme descrito em [Configurar impressão de etiquetas de onda](../warehousing/configure-wave-label-printing.md).

#### <a name="use-case-21-a-single-wave-label-is-scratched-and-must-be-reprinted"></a>Caso de uso 2.1: uma única etiqueta de onda está arranhada e deve ser reimpressa.

1. Entre no aplicativo de depósito como um usuário com acesso ao depósito *62*. (Nos dados de demonstração padrão, você pode entrar usando a ID do usuário *62* e a senha *1*.)
1. Acesse **Saída \> Reimprimir etiqueta de onda única**.
1. Insira ou digitalize a ID da etiqueta de onda.
1. Selecione a impressora na qual fazer a reimpressão.
1. Selecione **OK** para confirmar a ação.

#### <a name="use-case-22-several-labels-for-boxes-of-the-same-item-were-damaged-and-must-be-reprinted-each-label-has-a-product-bar-code-but-no-enumeration-or-sscc-number"></a>Caso de uso 2.2: várias etiquetas para caixas do mesmo item foram danificadas e devem ser reimpressas. Cada etiqueta tem um código de barras do produto, mas nenhuma enumeração ou número de SSCC.

1. Entre no aplicativo de depósito como um usuário com acesso ao depósito *62*. (Nos dados de demonstração padrão, você pode entrar usando a ID do usuário *62* e a senha *1*.)
1. Acesse **Saída \> Reimprimir etiquetas (Item)**.
1. Insira ou digitalize a ID da remessa.
1. Selecione o bloco que contém o rolo de etiquetas correto do qual fazer a reimpressão.
1. Examine o código de barras do produto de uma etiqueta existente para confirmar se a linha correta foi selecionada.
1. Insira o número de etiquetas a serem reimpressas.
1. Selecione a impressora na qual fazer a reimpressão.
1. Selecione **OK** para confirmar a ação.

#### <a name="use-case-23-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-because-the-labels-have-enumeration-you-can-define-the-carton-range-to-reprint"></a>Caso de uso 2.3: várias etiquetas para as caixas não foram impressas por causa de uma obstrução na impressora. Como as etiquetas têm enumeração, você pode definir o intervalo de caixas a ser reimpresso.

1. Entre no aplicativo de depósito como um usuário com acesso ao depósito *62*. (Nos dados de demonstração padrão, você pode entrar usando a ID do usuário *62* e a senha *1*.)
1. Acesse **Saída \> Reimprimir etiquetas (Enumeração)**.
1. Insira ou digitalize a ID da remessa.
1. Selecione o bloco que contém o rolo de etiquetas correto do qual fazer a reimpressão.
1. Insira a primeira caixa para a qual reimprimir a etiqueta.
1. Insira a última caixa para a qual reimprimir a etiqueta. Como alternativa, deixe esse campo em branco para reimprimir etiquetas para todas as caixas após a primeira caixa especificada.
1. Selecione a impressora na qual fazer a reimpressão.
1. Selecione **OK** para confirmar a ação.

#### <a name="use-case-24-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-the-last-good-label-has-a-wave-label-id-that-is-printed-as-a-bar-code"></a>Caso de uso 2.4: várias etiquetas para as caixas não foram impressas por causa de uma obstrução na impressora. A última etiqueta de mercadoria tem uma ID de etiqueta de onda que é impressa como um código de barras.

1. Entre no aplicativo de depósito como um usuário com acesso ao depósito *62*. (Nos dados de demonstração padrão, você pode entrar usando a ID do usuário *62* e a senha *1*.)
1. Acesse **Saída \> Reimprimir etiquetas (pela última)**.
1. Insira ou digitalize a ID da remessa.
1. Selecione o bloco que contém o rolo de etiquetas correto do qual fazer a reimpressão.
1. Insira ou digitalize a ID da etiqueta de onda da última etiqueta de onda da mercadoria. O aplicativo identifica a próxima etiqueta na sequência como a primeira caixa para a qual a etiqueta será reimpressa.
1. Insira a última caixa para a qual reimprimir a etiqueta. Como alternativa, deixe esse campo em branco para reimprimir etiquetas para todas as caixas após a primeira caixa especificada.
1. Selecione a impressora na qual fazer a reimpressão.
1. Selecione **OK** para confirmar a ação.

## <a name="scenario-3-short-pick-and-reprint"></a>Cenário 3: Separação insuficiente e reimpressão

Antes de trabalhar com esse cenário, os seguintes pré-requisitos devem ser atendidos:

- Os dados de demonstração devem estar instalados e você deve selecionar a entidade legal **USMF**.
- A impressão de etiquetas de onda deve estar configurada, e algumas etiquetas devem ser geradas, conforme descrito em [Configurar impressão de etiquetas de onda](../warehousing/configure-wave-label-printing.md).

### <a name="set-up-work-exceptions"></a>Configurar exceções de trabalho

As exceções de trabalho controlam o comportamento da separação insuficiente. Siga essas etapas para configurar uma exceção de trabalho:

1. Acesse **Gerenciamento de depósito \> Configurar \> Trabalho \> Exceções de trabalho**.
1. Crie um registro com as seguintes configurações:

    - **Código de exceção do trabalho:** *Separação insuficiente e reimpressão*
    - **Tipo de exceção:** *Separação insuficiente*
    - **Sugerir reimpressão de etiquetas de onda:** *Sim*

### <a name="void-and-reprint-after-a-short-pick"></a>Anular e reimprimir após uma separação insuficiente

1. Entre no aplicativo de depósito como um usuário com acesso ao depósito *62*. (Nos dados de demonstração padrão, você pode entrar usando a ID do usuário *62* e a senha *1*.)
1. Abra um fluxo de processamento de trabalho para o trabalho da ordem de venda que foi criado quando as etiquetas de onda foram impressas originalmente.
1. Selecione **Separação insuficiente**.
1. Selecione o código de exceção do trabalho que você criou para este cenário.
1. Se você selecionou a exceção correta, a caixa de seleção **Anular e reimprimir** deverá estar disponível. Marque esta caixa e confirme. Após a confirmação, a sequência do rolo de etiquetas identificada pelo campo **ID de criação da etiqueta** é recalculada com base na quantidade da linha do trabalho alterada. Em seguida, ele será reimpressa na impressora especificada.

## <a name="additional-resources"></a>Recursos adicionais

- [Impressão de etiqueta do ciclo](configure-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]