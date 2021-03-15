---
title: Regra de liberação para o depósito
description: Este tópico fornece informações sobre o recurso Regra de liberação para o depósito, que oferece flexibilidade durante a liberação para o depósito. Ele adiciona uma opção de configuração que controla se o sistema permite que as linhas de ordem parcialmente reservadas sejam liberadas.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 8c4775ca3f44486fd3cd557df49acd229048d186
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996164"
---
# <a name="release-to-warehouse-rule"></a>Regra de liberação para o depósito

[!include [banner](../includes/banner.md)]

O recurso *Regra de liberação para o depósito* oferece flexibilidade durante a liberação para o depósito. Ele adiciona uma opção de configuração para cada depósito. Você pode usar essa opção para especificar se as linhas de ordem parcialmente reservadas podem ser liberadas para esse depósito. O recurso funciona em conjunto com a funcionalidade de distribuição integrada avançada em situações nas quais parte da quantidade de uma linha de ordem é marcada em relação a uma fonte de fornecimento, mas a parte restante pode ser processada no depósito. Portanto, a linha pode ser liberada para que o processamento de depósito da quantidade de estoque disponível possa continuar.

## <a name="turn-on-and-initialize-the-release-to-warehouse-rule-feature"></a>Ativar e inicializar o recurso Regra de liberação para o depósito

### <a name="turn-on-the-feature"></a>Ativar o recurso

Para que você possa usar o recurso *Regra de liberação para o depósito*, ele deve estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Regra de liberação para o depósito*

### <a name="initialize-the-feature"></a>Inicializar o recurso

Depois que o recurso for ativado no sistema, você deverá inicializá-lo para definir a regra do estado inicial correto para todos os depósitos.

- Para depósitos que não estão habilitados para gerenciamento de depósito, a regra é inicialmente definida como **Não aplicável**.
- Para depósitos que estão habilitados para gerenciamento de depósito, a regra é inicialmente definida como **Permitir reserva parcial**

Para inicializar o recurso e definir a regra de liberação para o depósito para todos os depósitos, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na página **Parâmetros de gerenciamento de depósito**, na guia **Geral**, na seção **Informações da empresa**, selecione o link para a regra **Inicializar liberação para o depósito**. (Se esse link não for exibido, o recurso não está ativado ou já foi inicializado.)
1. Quando for solicitado a confirmar a ação, selecione **Sim** para inicializar o recurso.

## <a name="set-the-release-to-warehouse-rule-for-each-warehouse"></a><a name="set-option-warehouse"></a>Definir a regra de liberação para o depósito para cada depósito

Depois que o recurso for ativado e inicializado, todos os seus depósitos terão uma configuração inicial, conforme descrito na seção anterior. Você pode alterar essa configuração para depósitos individuais seguindo estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Depósitos**.
1. Selecione o depósito a ser configurado.
1. Selecione **Editar** para colocar a página no modo de edição.
1. Na FastTab **Depósito**, na seção **Reservas**, o campo **Requisito para reserva de estoque** controla se a liberação parcial das ordens é permitida. Selecione um dos seguintes valores:

    - **Não aplicável** – Quando o recurso é ativado e inicializado pela primeira vez, este valor é automaticamente atribuído a todos os depósitos que não estão habilitados para gerenciamento de depósito. Ele não pode ser alterado. Esse valor não está disponível para depósitos habilitados para gerenciamento de depósito.
    - **Permitir reserva parcial** – As ordens poderão ser liberadas quando qualquer quantidade for reservada. O sistema avaliará se a quantidade não reservada deve ser marcada para distribuição integrada avançada e marcará essa quantidade como necessária. Se não houver marcação, o sistema criará o trabalho somente para a quantidade reservada. Quando o recurso é ativado e inicializado pela primeira vez, esse valor é automaticamente atribuído a todos os depósitos que estão habilitados para gerenciamento de depósito. Esse valor não está disponível para depósitos não habilitados para gerenciamento de depósito.
    - **Exigir reserva cheia** – As ordens só poderão ser liberadas se a quantidade total for reservada. Elas não poderão ser liberadas se a quantidade total não for fisicamente reservada ou planejada para distribuição integrada. Esse valor não está disponível para depósitos não habilitados para gerenciamento de depósito.

1. Selecione **Salvar**.

## <a name="scenarios"></a>Cenários

Esta seção fornece dois cenários que você pode analisar para saber o que o recurso faz e como usá-lo.

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para analisar esses cenários usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

Você também pode usar estes cenários como orientação para o recurso ao trabalhar em um sistema de produção. No entanto, nesse caso, você deve substituir seus próprios valores e talvez não tenha alguns tipos de registros necessários fornecidos pelos dados de demonstração padrão.

### <a name="scenario-1-require-full-release-no-planned-cross-docking"></a><a name="scenario1"></a>Cenário 1: Exigir liberação completa (sem distribuição integrada planejada)

Este cenário mostra como o recurso funciona para depósitos que estão definidos como **Exigir reserva cheia**.

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Depósitos**.
1. Para o depósito _62_, defina o campo **Requisito para reserva de estoque** como **Exigir reserva cheia**, conforme descrito na seção [Definir a regra de liberação para o depósito para cada depósito](#set-option-warehouse) anteriormente neste tópico.
1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar uma ordem de venda.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - Na FastTab **Cliente**, defina o campo **Conta de cliente** como _US-004_.
    - Na FastTab **Geral**, defina o campo **Depósito** como _62_.

1. Selecione **OK** para criar a nova ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ela inclui uma linha vazia na grade da seção **Linhas da ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *2*

1. Selecione **Adicionar linha** para adicionar uma nova linha e defina os seguintes valores:

    - **Número de item:** *A0002*
    - **Quantidade:** *2*

1. Selecione a primeira linha da ordem e, no menu **Estoque**, acima da grade, selecione **Reserva**.
1. Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. Não reserve a segunda linha da ordem.
1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.
1. Observe que você receberá a seguinte mensagem de erro: "A quantidade total deve ser reservada fisicamente." Portanto, o sistema não cria nenhum trabalho, remessa ou carga para a ordem.

    > [!NOTE]
    > A mesma mensagem de erro será exibida se você reservar parcialmente a segunda linha.

### <a name="scenario-2-allow-partial-release"></a>Cenário 2: Permitir liberação parcial

Este cenário mostra como o recurso funciona para depósitos que estão definidos como **Permitir liberação parcial**.

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Depósitos**.
1. Para o depósito _62_, defina o campo **Requisito para reserva de estoque** como **Permitir reserva parcial**, conforme descrito na seção [Definir a regra de liberação para o depósito para cada depósito](#set-option-warehouse) anteriormente neste tópico.
1. Como você fez no [cenário anterior](#scenario1), vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda** e crie uma ordem de venda para a conta de cliente _US-004_ do depósito _62_. Adicione estas duas linhas de ordem:

    - **Linha 1:** defina o campo **Número do item** como _A0001_, o campo **Quantidade** como _2_ e o campo **Unidade** como _Pçs._.
    - **Linha 2:** defina o campo **Número do item** como _A0002_, o campo **Quantidade** como _2_ e o campo **Unidade** como _Pçs._.

1. Como você fez no [cenário anterior](#scenario1), reserve a quantidade total para a linha de ordem 1, mas não reserve a linha de ordem 2.
1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.
1. Observe que você não receberá uma mensagem de erro desta vez. Em vez disso, o sistema cria trabalhos, remessas e cargas conforme necessário e mostra os resultados.
1. Para exibir as informações de remessas, cargas e trabalhos, use as opções no menu **Depósito** acima da grade:

    - **Linha 1:** três opções estão disponíveis: **Detalhes da remessa**, **Detalhes da carga** e **Detalhes do trabalho**. Selecione cada opção para exibir os detalhes da remessa, da carga e do trabalho que foram criados quando a ordem foi liberada para o depósito.
    - **Linha 2:** somente a opção **Detalhes do trabalho** está disponível. Selecione-a e observe que nenhum trabalho foi criado porque nenhum estoque foi reservado. Portanto, nenhuma remessa ou carga foi criada também.

> [!NOTE]
> O mesmo resultado é esperado quando a segunda linha é parcialmente reservada. Nesse caso, o trabalho será criado para a quantidade da linha reservada, mas não para a quantidade não reservada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]