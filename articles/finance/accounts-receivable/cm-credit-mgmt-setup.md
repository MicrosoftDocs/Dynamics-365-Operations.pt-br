---
title: Configuração dos parâmetros de gerenciamento de crédito
description: Este tópico descreve as opções que você pode usar para configurar o Gerenciamento de crédito de acordo com as necessidades da sua empresa.
author: JodiChristiansen
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 768fb5121ae6be513c4a533a20027cf784640b2a
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753456"
---
# <a name="credit-management-parameters-setup"></a>Configuração dos parâmetros de gerenciamento de crédito

[!include [banner](../includes/banner.md)]

Este tópico descreve as opções que você pode usar para configurar o Gerenciamento de crédito de acordo com as necessidades da sua empresa. Para usar os recursos de Gerenciamento de crédito, configure os parâmetros na página **Parâmetros de crédito e cobranças** (**Crédito e cobranças \> Configuração \> Parâmetros de crédito e cobranças**).

## <a name="credit-parameters"></a>Parâmetros de crédito

Existem quatro FastTabs na seção **Crédito** onde é possível alterar os parâmetros que controlam o Gerenciamento de crédito: **Bloqueios de crédito**, **Ponto de verificação de gerenciamento de crédito**, **Estatísticas de gerenciamento de crédito** e **Limites de crédito**. As seções a seguir descrevem as configurações disponíveis em cada FastTab.

### <a name="credit-holds"></a>Bloqueios de crédito

- Defina a opção **Permitir a edição das ordens de venda após a liberação do bloqueio da ordem** como **Sim** para exigir que as regras de lançamento sejam verificadas novamente se o valor da ordem de venda (preço bruto) tiver sido aumentada desde que a ordem de venda foi liberada da lista de bloqueio. .
- No campo **Motivos das ordens canceladas**, selecione o motivo de liberação que será usado por padrão quando uma ordem de venda que estava em bloqueio de gerenciamento de crédito for cancelada.
- Defina a opção **Verificar limite de crédito de grupos de crédito de cliente** como **Sim** para verificar o limite de crédito de um grupo de crédito de cliente quando o cliente em uma ordem de venda pertencer a um grupo de crédito de cliente. O limite de crédito do grupo será verificado e, se for suficiente, o limite de crédito do cliente será verificado.
- Defina a opção **Verificar o limite de crédito quando as condições de pagamento forem estendidas** como **Sim** para verificar as classificações de condições de pagamento a fim de determinar se as condições de pagamento na ordem de venda diferem das condições de pagamento padrão do cliente. Se as novas condições de pagamento tiverem uma classificação superior à das condições de pagamento originais, a ordem será colocada em bloqueio de gerenciamento de crédito.
- Defina a opção **Verificar o limite de crédito quando um desconto de liquidação for aumentado** como **Sim** para verificar as classificações de desconto de liquidação a fim de determinar se o desconto à vista na ordem de venda difere do desconto à vista padrão do cliente. Se o novo desconto à vista tiver uma classificação superior à do desconto à vista original, a ordem será colocada em bloqueio de gerenciamento de crédito.
- No campo **Motivo para liberar ordens modificadas**, selecione o motivo de liberação que será usado por padrão quando as ordens modificadas forem liberadas automaticamente do bloqueio de gerenciamento de crédito.
- Defina a opção **Ignorar regra de limite de crédito expirado quando a data de vencimento estiver em branco** como **Sim** para controlar o comportamento da regra **Limite de crédito expirado**. Defina a opção como **Não** para bloquear uma ordem quando a data de vencimento estiver em branco.
- No Gerenciamento de depósito, é possível criar cargas no momento da entrada da ordem de venda. Defina a opção **Remover linhas de carga bloqueadas** como **Não** para deixar linhas da ordem de venda na carga quando uma ordem de venda estiver em bloqueio de crédito. A carga não pode ser processada enquanto a ordem de venda está em espera. Defina a opção como **Sim** para remover linhas da ordem de venda da carga quando uma ordem de venda estiver em bloqueio de crédito. Dessa forma, a carga poderá ser processada.
- As ordens de venda podem ser liberadas automaticamente da revisão de gerenciamento de crédito. No campo **Motivo para liberar automaticamente**, selecione o motivo de liberação que será usado por padrão quando as ordens de venda forem liberadas automaticamente.
- As ordens de venda podem ser liberadas automaticamente da revisão de gerenciamento de crédito. No campo **Liberado automaticamente**, selecione **Sem lançamento** para liberar o bloqueio de uma ordem. Você deve executar manualmente o processo que colocou a ordem em espera. Selecione **Com lançamento** para lançar a ordem usando o mesmo processo de lançamento que foi executado quando a ordem de venda foi colocada em espera.

### <a name="credit-management-checkpoint"></a>Ponto de verificação de gerenciamento de crédito

É possível definir o tempo usado para verificar ordens de venda no caso de problemas de crédito. A FastTab **Ponto de verificação de gerenciamento de crédito** identifica os processos de lançamento de documentos que incluem o processamento de regras de gerenciamento de crédito. Também é possível verificar as regras de crédito enquanto você executa um lançamento pro forma ou um lançamento completo da ordem de venda. Marque as caixas de seleção para definir os processos de lançamento que devem colocar uma ordem em espera se for encontrado um problema após o processamento das regras de bloqueio de gerenciamento de crédito.

Você também pode definir o número de dias de carência antes que as regras de crédito sejam verificadas novamente. Apesar de você poder especificar que as regras de gerenciamento de crédito sejam verificadas no lançamento, as regras não serão verificadas pelo número especificado de dias de carência. Por exemplo, você confirma uma ordem de venda no dia 1 e especifica dois dias de carência para a etapa de confirmação. Nesse caso, as regras de crédito não serão verificadas na próxima etapa de lançamento (por exemplo, a criação de uma guia de remessa ou o faturamento da ordem) até o dia 4. No dia 4 ou depois dele, as regras serão verificadas novamente quando ocorrer o lançamento, e o número de dias de carência será alterado para o valor especificado para o próximo ponto de verificação de lançamento.

Se você não especificar o número de dias de carência, as regras de crédito serão verificadas a cada etapa de lançamento configurada para executar regras de gerenciamento de crédito. Se você liberar a ordem de venda sem lançar e, depois, executar a mesma etapa de processamento da ordem novamente, as regras de crédito serão verificadas de novo. Por exemplo, uma ordem é colocada em espera após uma confirmação, e você a libera com ou sem lançamento. Nesse caso, a ordem será colocada em espera novamente se você confirmá-la mais uma vez. Use os dias de carência se a ordem tiver de avançar para a próxima etapa de processamento sem ser colocada em espera novamente.

Não é possível especificar dias de carência para alguns pontos de verificação de lançamento, mas não para outros. Você deve configurar todos os pontos de verificação de lançamento para que tenham dias de carência ou deve configurá-los para que não tenham dias de carência.

- Marque a caixa de seleção **Lançamento** para executar as regras de gerenciamento de crédito quando o ponto de verificação de lançamento mostrado na linha for executado. Se você não marcar a caixa de seleção, as regras serão verificadas apenas uma vez durante todo o processo de lançamento.
- Se você marcar a caixa de seleção **Lançamento**, especifique o número de dias de carência que devem passar antes que as regras de bloqueio sejam verificadas novamente. Você não poderá adicionar dias de carência se a caixa de seleção **Lançamento** estiver desmarcada.
- Marque a caixa de seleção **Pro forma** para executar as regras de gerenciamento de crédito quando o ponto de verificação de lançamento pro forma mostrado na linha for executado. Na maioria dos casos, o campo **Pro forma** é definido como **Não** na caixa de diálogo exibida quando uma ordem de venda é lançada.
- Se você marcar a caixa de seleção **Lançamento**, especifique o número de dias de carência que devem passar antes que as regras de bloqueio sejam verificadas novamente. Você não poderá adicionar dias de carência se a caixa de seleção **Lançamento** estiver desmarcada.

### <a name="credit-management-statistics"></a>Estatísticas de gerenciamento de crédito

Várias estatísticas de gerenciamento de crédito são incluídas no Quadro de Fatos **Estatísticas de gerenciamento de crédito de cliente** da página **Cliente**. Você deve especificar diversos valores que são necessários para calcular essas estatísticas. Insira o número de meses usado para calcular os seguintes valores no Quadro de Fatos **Estatísticas de gerenciamento de crédito de cliente**:

1. Vendas Diárias Pendentes 1
2. Vendas Diárias Pendentes 2
3. Saldo médio 1
4. Saldo médio 2
5. Limite médio de crédito %
6. Média de exposição em %

### <a name="credit-limits"></a>Limites de crédito

- No Gerenciamento de crédito, o limite de crédito do cliente é mostrado na moeda do cliente. Você deve definir o tipo de taxa de câmbio para o limite de crédito na moeda do cliente. No campo **Tipo de taxa de câmbio de limite de crédito**, selecione o tipo de taxa de câmbio que deve ser usado para converter o limite de crédito principal para o limite de crédito do cliente.
- Defina a opção **Permitir a edição manual de limites de crédito** como **Não** para impedir que os usuários editem os limites crédito na página **Cliente**. Se esta opção for definida como **Não**, as alterações no limite de crédito de um cliente só poderão ser feitas lançando transações de ajuste de limite de crédito.

### <a name="number-sequences-and-shared-number-sequence-parameters"></a>Sequências numéricas e parâmetros compartilhados de sequência numérica

Uma ID de diário é necessária para processar ajustes de limite de crédito. Você deve adicionar o número do ajuste de limite de crédito que deve ser usado para gerar a ID do diário.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
