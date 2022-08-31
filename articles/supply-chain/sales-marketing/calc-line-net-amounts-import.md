---
title: Recalcular valores líquidos de linha ao importar ordens de venda, cotações e devoluções
description: Este artigo descreve se e como o sistema recalcula valores líquidos de linha quando ordens de venda, cotações e devoluções são importados. Ele também explica como você pode controlar o comportamento em diferentes versões do Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 08/05/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2022-06-08
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 08b30044a93e46c9c83848b60d69c595bc774570
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335545"
---
# <a name="recalculate-line-net-amounts-when-importing-sales-orders-quotations-and-returns"></a>Recalcular valores líquidos de linha ao importar ordens de venda, cotações e devoluções

[!include [banner](../includes/banner.md)]

Este artigo descreve se e como o sistema recalcula valores líquidos de linha quando ordens de venda, cotações e devoluções são importados. Ele também explica como você pode controlar o comportamento em diferentes versões do Microsoft Dynamics 365 Supply Chain Management.

## <a name="how-updates-to-net-line-amounts-are-calculated-on-import"></a>Como as atualizações de valores de linha líquida são calculadas na importação

Supply Chain Management versão 10.0.23 apresentado [bugfix 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418). Este bugfix alterou as condições em que o campo **Valor líquido** em uma linha pode ser atualizado ou recalculado quando são importadas atualizações para ordens de venda, devoluções e cotações existentes. Na versão 10.0.29, você pode substituir este bugfix ativando o recurso *Calcular valor líquido de linha mediante importação*. Esse recurso tem um efeito semelhante, mas oferece uma configuração global que permite que volte ao comportamento antigo se precisar. Embora o novo comportamento faça o sistema operar de forma mais intuitiva, ele pode gerar resultados inesperados em cenários específicos em que todas estas condições são atendidas:

- Os dados que atualizam registros existentes são importados por meio da entidade *Linhas de ordem de venda V2*, *Linhas de cotação de venda V2* ou *Linhas da ordem de devolução* usando o Protocolo Open Data (OData), incluindo situações em que você usa a gravação dupla, a importação/exportação por meio do Excel e algumas integrações de terceiros.
- [Políticas de avaliação de contrato comercial](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper) que estão em vigor estabelecem uma política de alteração que restringe as atualizações para o campo **Valor líquido** em linhas da ordem de venda, linhas da cotação de venda e/ou linhas da ordem de devolução.
- Os dados importados incluem alterações no campo **Valor líquido** em linhas, ou alterações (como preço unitário, quantidade ou desconto) que levarão ao recálculo do campo **Valor líquido** em linhas para um ou mais registros de linha existentes.

Nesses cenários específicos, o efeito da política de avaliação do contrato comercial é colocar uma restrição em atualizações do campo **Valor líquido** na linha. Essa restrição é conhecida como *política de alteração*. Por causa dessa política, ao usar a interface do usuário para editar ou recalcular o campo, o sistema solicita que você confirme se deseja fazer a alteração. No entanto, quando você importa um registro, o sistema deve fazer a escolha para você. Antes da versão 10.0.23, o sistema sempre deixava o valor líquido da linha inalterado, a menos que o valor líquido da linha de entrada fosse 0 (zero). No entanto, em versões mais recentes, o sistema sempre atualiza ou recalcula o valor líquido conforme necessário, a menos que seja explicitamente orientado a não fazê-lo. Embora o novo comportamento seja mais lógico, ele poderá causar problemas se você já estiver executando processos ou integrações que assumam o comportamento anterior. Este artigo descreve como reverter para o comportamento anterior se você precisar.

## <a name="control-calculations-of-line-net-amounts-in-versions-10029-and-later"></a>Controlar cálculos de valores líquidos de linha na versão 10.0.29 e posteriores

O Supply Chain Management versão 10.0.29 apresentou um recurso chamado *Calcular valor líquido de linha mediante importação*. Este recurso adiciona uma opção chamada **Calcular valor líquido de linha** à página **Parâmetros de contas a receber**. Esta opção permite selecionar entre os comportamentos novos e herdados para o cálculo de valores líquidos de linha na importação.

### <a name="turn-the-calculate-line-net-amount-on-import-feature-on-or-off"></a>Ativar ou desativar o recurso Calcular valor líquido de linha mediante importação

Quando você atualiza para a versão 10.0.29, o recurso *Calcular valor líquido de linha mediante importação* é ativado por padrão e a nova opção **Calcular valor líquido de linha** é inicialmente definida como *Sim*. A configuração *Sim* corresponde ao novo comportamento padrão. Ela corresponde ao comportamento do sistema quando o recurso é desativado, exceto no caso da funcionalidade do [parâmetro CalculateLineAmount](#CalculateLineAmount), conforme descrito posteriormente neste artigo. A configuração *Não* corresponde ao comportamento do sistema antes da versão 10.0.23 e é fornecida principalmente para dar suporte a cenários de integração herdados.

Os administradores podem ativar ou desativar o recurso *Calcular valor líquido de linha mediante importação* usando o [Espaço de trabalho do gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="set-the-calculate-line-net-amount-option"></a>Defina a opção Calcular valor líquido de linha

Quando o recurso *Calcular valor líquido de linha mediante importação* é ativado, você pode definir a opção **Calcular valor líquido de linha** seguindo essas etapas.

1. Acesse **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
1. Na guia **Preços**, na FastTab **Cálculo de valor líquido da linha por meio da integração**, defina a opção **Calcular valor líquido de linha** como um dos seguintes valores:

    - *Sim*: o sistema sempre recalculará e atualizará os valores das linhas, quando necessário. (Portanto, ele ignorará a política de avaliação do contrato comercial.)
    - *Não*: se o valor líquido existente ou recebido para qualquer linha for 0 (zero), o valor dessa linha será recalculado com base em outros valores (como o preço unitário, a quantidade e o desconto). Se o valor líquido existente ou recebido for diferente de 0 (zero) e uma política de alteração for definida no campo **Valor líquido** na linha, o campo não será recalculado ou atualizado, mesmo quando as alterações de entrada no preço de linha, na quantidade e/ou no desconto indicarem que o total da linha deve ser recalculado. Esse é comportamento da versão 10.0.22.

### <a name="how-the-calculate-line-net-amount-on-import-feature-affects-the-calculatelineamount-parameter"></a><a name="CalculateLineAmount"></a>Como o recurso Calcular valor líquido de linha mediante importação afeta o parâmetro CalculateLineAmount

Quando o recurso *Calcular valor líquido de linha mediante importação* estiver ativado, o valor do parâmetro `CalculateLineAmount` para as tabelas `SalesLine` e `SalesQuotationLine` não terá efeito. Em vez disso, o comportamento é controlado globalmente pela opção **Calcular valor líquido de linha** descrita na seção anterior. Portanto, quando o recurso está ativado, você não deve depender do valor `CalculateLineAmount`.

Quando o recurso *Calcular valor líquido de linha mediante importação* está desativado, o parâmetro `CalculateLineAmount` para as tabelas `SalesLine` e `SalesQuotationLine` funciona da mesma forma que no Supply Chain Management da versão 10.0.23 até 10.0.28, conforme descrito na próxima seção.

## <a name="control-line-net-amount-calculations-in-versions-10028-and-earlier"></a>Controlar cálculos de valores líquidos de linha na versão 10.0.28 e anterior

Quando o [bugfix 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418) foi apresentado na versão 10.0.23, tornou-se possível selecionar como cada entidade de dados relevante deve se comportar quando um valor líquido da linha foi editado ou precisou ser recalculado devido a outras alterações (como um preço de item atualizado). Você pode controlar esse comportamento ao definir o novo parâmetro `CalculateLineAmount` de cada linha com um dos seguintes valores no arquivo importado:

- **`CalculateLineAmount` = *1***: o campo **Valor líquido** na linha é sempre recalculado e atualizado, independentemente de uma política de alteração ser definida para o campo e seja qual for o valor líquido da linha de entrada ou existente.
- **`CalculateLineAmount` = *0***: se o valor líquido existente ou recebido para uma linha for 0 (zero), o valor dessa linha será recalculado com base em outros valores (como o preço unitário, a quantidade e o desconto). Se o valor líquido existente ou recebido for diferente de 0 (zero) e uma política de alteração for definida no campo **Valor líquido** na linha, o campo não será recalculado ou atualizado.  

O comportamento do sistema depende da versão do Supply Chain Management:

- Na versão 10.0.22 e anterior, o sistema sempre se comporta como se `CalculateLineAmount` estivesse definido como *0*; não há como fazê-lo se comportar como se `CalculateLineAmount` estivesse definido como *1*.
- Nas versões 10.0.23 até 10.0.28, o sistema se comporta como se `CalculateLineAmount` estivesse definido como *1* para todas as linhas em que ele não está explicitamente definido como *0* no arquivo de importação.
