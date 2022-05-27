---
title: Detalhes da linha de trabalho
description: Este tópico fornece informações sobre a página Detalhes da linha de trabalho, que mostra uma lista abrangente, classificável e filtrável das linhas de trabalho individuais no sistema.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkLocationChange, WHSWorkLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 4d7c6991c0171b0e09752b3305e0fa11a25b7833
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674072"
---
# <a name="work-line-details"></a>Detalhes da linha de trabalho

[!include [banner](../includes/banner.md)]

A página **Detalhes da linha de trabalho** mostra uma lista abrangente, classificável e filtrável das linhas de trabalho individuais em seu sistema. Ela fornece uma visão geral do trabalho que está sendo planejado e executado no depósito. É possível alternar facilmente entre a exibição de todas as linhas de trabalho e a exibição de linhas de trabalho abertas. Os detalhes fornecidos para cada linha incluem o status do trabalho, o número do item, a localização, a quantidade do trabalho, a ID da carga e a ID da remessa.

## <a name="turn-on-the-work-line-details-feature"></a>Ativar o recurso de detalhes da linha de trabalho

A partir da versão 10.0.21 do Supply Chain Management, este recurso está ativado por padrão. Os administradores podem usar a página [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo ou desativá-lo, se necessário. Aqui o recurso está listado como:

- **Módulo:** *Gerenciamento de depósito*
- **Nome do recurso:** *Detalhes da linha de trabalho*

## <a name="open-and-use-the-work-line-details-page"></a>Abrir e usar a página Detalhes da linha de trabalho

Para exibir a lista de detalhes da linha de trabalho, acesse **Gerenciamento de depósito \> Trabalho \> Detalhes da linha de trabalho**. De lá, você poderá executar as seguintes ações:

- Use o campo **Filtro** para procurar linhas que tenham um valor específico para qualquer parâmetro disponível. (Os parâmetros disponíveis incluem muitos parâmetros que não são mostrados como colunas na grade.)
- Use a caixa de seleção **Mostrar fechadas** para mostrar ou ocultar as linhas fechadas.
- Selecione **Exibir dimensões** para abrir a caixa de diálogo **Exibição de dimensões**, na qual você pode optar por mostrar ou ocultar várias colunas de dimensão na grade.
- Selecione qualquer cabeçalho de coluna para abrir um menu no qual é possível optar por classificar ou filtrar a lista por valores nessa coluna.
- Selecione uma linha de trabalho e, em seguida, selecione **Alterar localização** para abrir uma caixa de diálogo na qual é possível alterar a localização dessa linha de trabalho. A localização que você especificar substituirá a configuração da diretiva de localização.
- Selecione uma linha de trabalho e selecione **Cancelar linha de trabalho** para abrir uma caixa de diálogo na qual é possível reduzir parcialmente ou totalmente a quantidade dessa linha de trabalho.
- Ajuste as quantidades.
- Exiba as transações por trás de qualquer linha de trabalho.

## <a name="try-out-the-feature"></a>Experimentar o recurso

Esta seção fornece uma demonstração em três partes que mostra como trabalhar com os detalhes da linha de trabalho.

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para trabalhar com essa demonstração usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

Você também pode usar essa demonstração como orientação ao trabalhar em um sistema de produção. No entanto, você deve substituir seus próprios valores e talvez não tenha alguns tipos de registros necessários fornecidos pelos dados de demonstração padrão.

### <a name="verify-that-the-scenario-setup-includes-enough-available-inventory"></a>Verificar se a configuração do cenário inclui estoque disponível suficiente

Se estiver trabalhando com os dados de demonstração **USMF**, você primeiro deverá se certificar de que o sistema esteja configurado de maneira que haja estoque suficiente disponível em cada local de separação relevante. Para essa demonstração, a expectativa é de que você tenha o seguinte estoque disponível:

- **Item M9200:** 45 unidades. (ou mais)
- **Item M9202:** 10 unidades. (ou mais)

Siga estas etapas para verificar se há estoque suficiente disponível e para fazer os ajustes que forem necessários.

1. Acesse **Gerenciamento de depósito \> Configurar \> Diretivas de localização** e determine quais locais de separação são usados para a separação da ordem de venda no depósito 51. (Para obter mais informações, consulte [Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização](control-warehouse-location-directives.md).)
1. Verifique os níveis de estoque nos locais relevantes.
1. Ajuste o estoque conforme necessário. Você pode criar movimentos manuais, usar reabastecimento ou aplicar qualquer outro fluxo para ajustar o estoque.

### <a name="part-1-create-picking-work"></a>Parte 1: Criar trabalho de separação

Antes de começar a criar o trabalho, verifique se o depósito está configurado para responder às solicitações de trabalho da forma esperada.

Siga estas etapas para criar alguns trabalhos de separação:

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Criar** para abrir a caixa de diálogo **Criar ordem de venda**.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - Na FastTab **Cliente**, defina o campo **Conta do cliente** como _US-001_.
    - Na FastTab **Geral**, defina o campo **Depósito**, como _51_.

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ela inclui uma nova linha vazia na grade **Linhas da ordem de venda**. Nessa linha de ordem, defina os seguintes valores:

    - **Número de item:** _M9200_
    - **Quantidade:** _20_
    - **Unidade:** _ea_

1. Selecione a nova linha da ordem e, no menu **Estoque**, selecione **Reserva** para abrir a página **Reserva**.
1. Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**. O sistema criará uma remessa, a adicionará a uma nova carga e criará o trabalho necessário.
1. Crie uma segunda ordem de venda para a mesma conta de cliente e depósito que você usou para a primeira ordem. Adicione estas duas linhas de ordem à ordem:

    - **Linha 1:** defina o campo **Número do item** como _M9200_, o campo **Quantidade** como _25_ e o campo **Unidade** como _unidade_.
    - **Linha 2:** defina o campo **Número do item** como _M9202_, o campo **Quantidade** como _10_ e o campo **Unidade** como _unidade_.

1. Repita as etapas de 6 a 8 para reservar o estoque para cada linha da ordem (uma por vez) e repita a etapa 9 para liberar a ordem para o depósito.

### <a name="part-2-change-the-location-for-a-work-line"></a>Parte 2: Alterar o local de uma linha de trabalho

1. Acesse **Gerenciamento de depósito \> Trabalho \> Detalhes da linha de trabalho**.
1. Encontre e selecione uma das linhas de trabalho criadas para esta demonstração.
1. Selecione **Alterar localização** para abrir a caixa de diálogo **Selecionar novo local**.
1. Na caixa de diálogo **Selecionar novo local**, no campo **Local**, selecione um novo local para a linha de trabalho.
1. Selecione **OK** para aplicar a alteração e fechar a caixa de diálogo.

> [!IMPORTANT]
> Você pode enviar alterações de localização somente se o novo local tiver estoque suficiente disponível (para uma separação) ou se ele passar a validação do tipo local (para uma colocação).

### <a name="part-3-change-the-quantity-of-a-work-line-or-cancel-a-work-line"></a>Parte 3: Alterar a quantidade de uma linha de trabalho ou cancelar uma linha de trabalho

1. Acesse **Gerenciamento de depósito \> Trabalho \> Detalhes da linha de trabalho**.
1. Encontre e selecione uma das linhas de trabalho criadas para esta demonstração. Observe que você pode cancelar ou alterar quantidades somente para as linhas de trabalho nas quais o tipo de trabalho for _separação_.
1. Selecione **Cancelar linha de trabalho** para abrir a caixa de diálogo **Quantidade a ser cancelada**.
1. Na caixa de diálogo **Quantidade a ser cancelada**, altere o valor no campo **Quantidade** para especificar a quantidade que deve ser *subtraída da* quantidade atualmente especificada para a linha. Por padrão, o campo **Quantidade** mostra a quantidade total.

    - Se você cancelar a quantidade total, o valor do **Status do trabalho** será alterado para _Cancelado_, mas o campo **Quantidade do trabalho** ainda mostrará o valor original.
    - Se você cancelar apenas parte da quantidade, o campo **Quantidade do trabalho** será atualizado para mostrar o novo valor, mas o valor do **Status do trabalho** não será alterado.

1. Selecione **OK** para aplicar a alteração e fechar a caixa de diálogo.

> [!IMPORTANT]
> Se cancelar apenas parte da quantidade de uma linha de trabalho, você também deverá remover a quantidade obsoleta da linha de carga. Caso contrário, a menos que a entrega insuficiente esteja configurada corretamente, a linha de carga poderá ter a remessa confirmada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]