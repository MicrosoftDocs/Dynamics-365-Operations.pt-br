---
title: Verificação de integridade para serviços e periféricos PDV
description: Este artigo fornece uma visão geral da operação de verificação de integridade no ponto de venda (PDV).
author: BrianShook
ms.date: 03/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 44fd4b6246d3d7947527416c2b8b447bd64f179f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863312"
---
# <a name="health-check-for-pos-peripherals-and-services"></a>Verificação de integridade para serviços e periféricos PDV

[!include [banner](includes/banner.md)]

Este artigo descreve a operação de verificação de integridade no ponto de venda (PDV).

## <a name="overview"></a>Visão Geral

Os armazenamentos de varejo podem ser ambientes complexos nos quais vários aplicativos e dispositivos são usados. À medida que as operações crescem, pode se tornar difícil garantir que as operações sejam sempre executadas suavemente, devido a dependências, por exemplo, periféricos que podem quebrar ou ser acidentalmente desconectados durante o dia. A solução de problemas relacionados a dispositivos e serviços pode ser cara para comerciantes maiores e igualmente frustrante para operações menores.

As versões 10.0.10 e posteriores do Microsoft Dynamics 365 Commerce incluem uma operação de verificação de integridade que pode ajudar a evitar alguns desses custos e frustração. Esta operação fornece um método para testar dispositivos diretamente do PDV fora das operações normais. Portanto, ele pode ajudar os varejistas a detectar problemas antes que eles ocorram.

## <a name="key-terms"></a>Condições principais

| Termo | descrição |
|---|---|
| Periférico | Qualquer dispositivo que o aplicativo PDV use para facilitar transações e outras operações no armazenamento. Exemplos incluem caixa registradora, scanners de código de barras e terminais de pagamento. |
| Serviço | Neste artigo, um serviço é um aplicativo auxiliar do qual o aplicativo PDV depende para realizar transações e operações diárias. Exemplos incluem aplicativos que ajudam com cálculos de impostos ou remessas. |

## <a name="health-check-operation"></a>Operação de verificação de integridade

A operação de verificação de integridade é a operação 717 na página **Operações de PDV** no Commerce headquarters. Ele pode ser usado enquanto o PDV estiver no modo não sacador. No entanto, uma estação de hardware deve estar ativa.

Por padrão, a verificação de integridade testa somente os dispositivos que estão configurados no perfil de hardware para a estação de hardware ativa no momento de uma registradora. Se um registro usar várias estações de hardware durante um dia, para realizar verificações de integridade para todas elas, ele deve se conectar a uma estação de hardware por vez. Não há verificação de integridade no nível de armazenamento. No entanto, é possível que esse tipo de verificação possa ser feito por meio da extensibilidade do Commerce Server.

### <a name="out-of-box-health-checks"></a>Verificações de integridade prontas para uso

| Tipo | Conexão | Detalhes |
|---|---|---|
| Impressora | OPOS | Esta verificação testa as funções básicas de vinculação e incorporação de objetos para PDV (OPOS). Eis alguns exemplos:<ul><li>Abrir: **Abrir** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fechar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Fechar**</li></ul> |
| Display LCD de linhas | OPOS | Esta verificação testa funções básicas OPOS. Eis alguns exemplos:<ul><li>Abrir: **Abrir** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fechar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Fechar**</li></ul> |
| Exibição dual | Windows | Essa verificação garante que o sistema operacional detecte uma segunda tela do Windows. | 
| LTM | OPOS | Esta verificação testa funções básicas OPOS. Eis alguns exemplos:<ul><li>Abrir: **Abrir** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fechar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Fechar**</li></ul> |
| Sacador | OPOS | Esta verificação testa funções básicas OPOS. Eis alguns exemplos:<ul><li>Abrir: **Abrir** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fechar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Fechar**</li></ul> | 
| Scanner | OPOS | Esta verificação testa funções básicas OPOS. Eis alguns exemplos:<ul><li>Abrir: **Abrir** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fechar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Fechar**</li></ul> | 
| Escala | OPOS | Esta verificação testa funções básicas OPOS. Eis alguns exemplos:<ul><li>Abrir: **Abrir** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fechar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Fechar**</li></ul> |
| Teclado do PIN | OPOS | Esta verificação testa funções básicas OPOS. Eis alguns exemplos:<ul><li>Abrir: **Abrir** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fechar: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Fechar**</li></ul> |
| Terminal de pagamento | SDK de pagamentos | Esta verificação testa as funções básicas de terminal de pagamento fornecidas pelo SDK de pagamentos. <ul><li>Bloquear</li><li>BeginTransaction</li><li>EndTransaction</li><li>ReleaseDevice</li><li>Fechar</li></ul> |

### <a name="using-the-health-check-operation-in-the-pos"></a>Usando a operação de verificação de integridade no PDV

Quando a operação de verificação de integridade é iniciada no PDV, um painel à direita lista os dispositivos configurados e mostra o status de cada dispositivo. Para fazer uma verificação de integridade de um único dispositivo, selecione o dispositivo e, em seguida, selecione **Testar selecionado**. Para fazer uma verificação de integridade para todos os dispositivos, selecione **Testar tudo**. A função **Testar tudo** testa todos os dispositivos, um por vez, e atualiza o status de cada dispositivo na coluna **Status**.

A coluna **Última verificação** mostra quando a verificação de integridade foi executada por último para cada dispositivo.

Se a verificação de integridade de um dispositivo passar (ou seja, se nenhum erro for encontrado), o status do dispositivo será **OK**. Se a verificação de integridade falhar, o status indicará que houve um erro. Nesse caso, o painel à direita fornece os detalhes relacionados ao erro ou instrui o usuário a contatar o administrador do sistema.

Alguns dispositivos, como o bloqueio de tecla OPOS, não têm testes de verificação de integridade prontos para uso. Se um teste de verificação de integridade não for detectado para nenhum dispositivo usado, o status será **Não suportado**.

### <a name="extending-health-checks"></a>Estendendo verificações de integridade

Os testes de avaliação de integridade prontos para uso são configurados para fornecer algumas mensagens amigáveis para erros comuns. No entanto, nem todos os cenários são cobertos. Por meio da extensibilidade, os comerciantes podem mapear mensagens amigáveis de usuário para erros que possam ser específicos do seu ambiente.

As verificações de integridade personalizadas também podem ser criadas para testar dispositivos que não têm suporte da caixa ou para testar quaisquer serviços dos quais o PDV dependa.

## <a name="related-articles"></a>Artigos relacionados

[Disparadores e impressão do Modern POS (MPOS)](dev-itpro/pos-trigger-printing.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]