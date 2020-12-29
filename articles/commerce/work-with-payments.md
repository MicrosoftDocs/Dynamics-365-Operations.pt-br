---
title: Métodos de pagamento em call centers
description: Este tópico descreve os diversos métodos de pagamento que você pode usar em um call center no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRSalesTableOrderHistory, MCRCCAuthManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e7636f5c664634c680edf2ff9d8bae5ebb9035af
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410204"
---
# <a name="payment-methods-in-call-centers"></a>Métodos de pagamento em call centers

[!include [banner](includes/banner.md)]

No Dynamics 365 Commerce, a configuração do canal de call center inclui uma configuração chamada **Habilitar a conclusão de ordem**. Essa configuração ajuda a garantia que todas as ordens criadas por esses usuários do canal só sejam liberadas para processamento de ordens se tiverem um pagamento antecipado ou um pagamento pré-autorizado que esteja dentro das tolerâncias aprovadas. Se a configuração **Habilitar a conclusão de ordem** estiver ativada, os usuários de call center poderão inserir pagamentos para ordens de venda para clientes usando os recursos de processamento de pagamento de call center. Se a configuração estiver desativada, os usuários de call center não poderão usar os recursos de processamento de pagamento de Call center, mas ainda poderão aplicar pagamentos antecipados a ordens de venda usando a funcionalidade Contas a receber padrão.

Como parte da configuração de canal, uma empresa pode definir métodos de pagamento permitidos para um canal de call center. O canal de call center usa os mesmos métodos de pagamento definidos para os canais de loja.

Para configurar os métodos de pagamento para um canal de call center, vá para **Varejo e Comércio** \> **Canais** \> **Call centers** \> **Todos os call centers** e, então, no menu **Configurar** , selecione a opção **Métodos de pagamento**.

Quando você cria um método de pagamento, há cinco funções de método de pagamento que pode atribuir.

| Função            | descrição |
|---------------------|-------------|
| Normal              | Use a função **Normal** no método de pagamento ao definir métodos de pagamento como à vista ou comprovantes. Quando esses tipos de pagamentos forem aplicados a uma ordem de venda no call center, o sinalizador **Pagamento antecipado** será padronizado como **Sim**. Isso lançará imediatamente um comprovante de pagamento antecipado na conta de cliente quando essa ordem for enviada. Os usuários podem alterar o sinalizador **Pagamento antecipado** como **Não**, se desejado, de modo que o comprovante de pagamento não seja criado até a fatura ser lançada. O comprovante de pagamento antecipado é lançado no histórico de transações de cliente, onde será sistematicamente liquidado de acordo com a fatura da ordem de venda. |
| Verificação               | Use a função **Cheque** quando você definir um instrumento do cheque bancário como forma de pagamento. Quando esse tipo de pagamento for aplicado a uma ordem de venda, o usuário deverá digitar o número de cheque de cliente como parte do processamento do aplicativo de pagamento. Os pagamentos em cheque serão sempre tratados como pagamentos antecipados quando forem aplicados. Os comprovantes de pagamento serão criados logo após o envio da ordem. Esses comprovantes de pagamento antecipado serão liquidados sistematicamente de acordo com as faturas criadas para a ordem. |
| Cartões               | Os tipos de pagamento por cartão representam qualquer tipo de pagamento que exija a entrada de um número de cartão definido no cartão de pagamento do cliente. Exemplos incluem cartões de crédito e cartões-presente. Quando você configura esses tipos de pagamentos, deve usar o menu **Configuração de cartão** para definir as IDs de cartão associadas a esse método de pagamento. No momento da entrada de ordem, os usuários podem determinar se o pagamento do cartão será pago antecipadamente usando a opção **Pagamento antecipado** que aparece na página de entrada de pagamento. A menos que a empresa exija pagamentos antecipados, o fluxo típico de um verdadeiro pagamento por cartão de crédito é um processo de duas etapas, onde a autorização é obtida no momento da entrada de ordem e o pagamento é liquidado e coletado do cartão do cliente no momento do faturamento. Para pagamentos de cartão-presente, o pagamento antecipado é recomendado, já que o saldo do cartão-presente deve ser reduzido imediatamente de modo que o cliente não possa aplicar esse mesmo valor em outro lugar. |
| Cliente            | A função **Cliente** em um método de pagamento implica que a liquidação será aplicada ao limite de crédito do cliente ou colocada "por conta". No Commerce, um cliente pode receber um limite de crédito que pode ser validado no momento da entrada de ordem. Os pagamentos feitos usando um método de pagamento vinculado à função **Cliente** criará um passivo na conta de cliente. Então, quando a ordem de venda for faturada, um saldo devido será mostrado. Nessas situações, os fornecedores geralmente enviam um pagamento, conforme as condições oferecidas. Como alternativa, um comprovante de crédito em aberto anterior na conta do cliente pode ser aplicado para liquidar o saldo devido. Observe que, se você definir esse método de pagamento, ele não aparecerá entre as opções de seleção de pagamento na entrada de ordem do call center, a menos que o sinalizador **Permitir na conta** esteja definido no registro do cliente com quem você está trabalhando. Esse sinalizador é encontrado na guia **Padrões de Pagamento** do registro de cliente. |
| Método de Pagamento para Remoção/Suprimento | A função **Método de Pagamento para Remoção/Suprimento** não é usada pelo call center. Será aplicável somente quando você definir os métodos de pagamento que o aplicativo de PDV (ponto de venda) usar um canal de armazenamento. |

À medida que os métodos de pagamento forem sendo definidos, deverão ser vinculados a uma conta contábil ou bancária. Caso você omita esta etapa, os usuários receberão erros quando tentarem salvar o tipo de pagamento.

## <a name="refund-payment-methods"></a>Métodos de pagamento de reembolso

Para os cenários de processamento de reembolso, o Call center também usa alguns dos métodos de pagamento definidos em Contas a receber. Para configurar esses métodos de pagamento, vá para **Varejo e Comércio** \> **Configuração de canal** \> **Configuração de call center** \> **Métodos de reembolso de call center**. Será necessário concluir essa configuração para processar os cheques de reembolso para os clientes. Por exemplo, se um cliente tiver originalmente pago por uma ordem com dinheiro ou cheque, o usuário poderá querer enviar para ele um cheque de reembolso por meio de Contas a receber. Nesse caso, os tipos de pagamento à vista e com cheque no call center devem ser mapeados para o método de pagamento correto em Contas a receber para ajudar a garantir que o desconto seja processado corretamente.

Adicionalmente, se um usuário estiver processando uma ordem de devolução como um usuário de call center no Commerce mas não puder vincular a devolução a uma venda original, o método de pagamento **Devolução** deverá ser definido nos Parâmetros de call center. Acesse **Varejo e Comércio** \> **Configuração de canal** \> **Configuração de call center** \> **Parâmetros de call center** e, então, na guia **ADM/Devolução**, no campo **Método de pagamento**, verifique se um método de pagamento foi definido. O método de pagamento será aquele usado para reembolsos. Normalmente, será definido como um método de cheque ou um método de conta de cliente.
