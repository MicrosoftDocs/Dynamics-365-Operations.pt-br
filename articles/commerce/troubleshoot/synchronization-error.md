---
title: Problemas de sincronização de ordens assíncronas
description: Este artigo descreve razões comuns para a falha na criação de ordens assíncronas no Microsoft Dynamics 365 Commerce, e fornece etapas de solução de problemas para ajudar os usuários e parceiros do sistema a compreender o que deu errado.
author: Shajain
ms.date: 11/30/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 27bccced3c07149fe1842524660447a49f86f3fc
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815747"
---
# <a name="asynchronous-order-synchronization-issues"></a>Problemas de sincronização de ordens assíncronas

[!include [banner](../../includes/banner.md)]

Este artigo descreve razões comuns para a falha na criação de ordens assíncronas no Microsoft Dynamics 365 Commerce, e fornece etapas de solução de problemas para ajudar os usuários e parceiros do sistema a compreender o que deu errado.

## <a name="symptom"></a>Sintoma

As ordens assíncronas criadas a partir de comércio eletrônico do Dynamics 365 Commerce ou do ponto de venda (PDV) não são refletidas no Commerce headquarters.

## <a name="troubleshooting"></a>Solução de problemas

A criação da ordem pode falhar na sede por motivos distintos, dependendo da fase em que o processo de criação da ordem falha. As etapas de solução de problemas a seguir passam pelas possíveis causas raiz.

### <a name="validate-that-the-transaction-related-to-the-asynchronous-order-has-reached-headquarters"></a>Validar que a transação relacionada à ordem assíncrona atingiu a sede

Para ordens de comércio eletrônico, na sede, vá para **Varejo e Comércio \> Consultas e relatórios \> Transações da loja online**. Se você tiver um número de confirmação da ordem, filtre as transações inserindo o número de confirmação no campo **ID de referência do canal**. Se você não tiver o número de confirmação, filtre as transações inserindo o número da conta do cliente.

Para ordens PDV, abra a página **Armazenar transações** e filtre os registros pelo número do recibo ou pelo número da conta do cliente. Se a transação não for encontrada, execute o trabalho de transações de canal **P-0001** , que sincroniza transações dos canais para a sede. Se o trabalho **P-0001** falhar, abra um tíquete de suporte para a falha do trabalho. Se o trabalho **P-0001** for bem-sucedido, mas as transações ainda não aparecerem na sede, abra um tíquete de suporte que inclua as informações relevantes.
 
### <a name="check-the-synchronization-status-if-the-transaction-is-present-in-headquarters-but-isnt-linked-with-a-sales-order"></a>Verifique o status da sincronização se a transação estiver presente na sede, mas não estiver vinculada a uma ordem de venda

Se a transação estiver presente na sede, mas a ordem de venda não tiver sido criada, abra a página **Transações da loja online** e selecione a FastTab **Status da sincronização**. Se o trabalho **Sincronizar ordens** tentar sincronizar esta transação, o campo **Status da ordem pendente** deverá mostrar o status **Bem-sucedido** ou **Com falha**. Se o status for **Bem-sucedido**, o campo da ordem de venda deverá estar presente nessa transação. Se o status for **Com falha**, você poderá exibir detalhes do erro no campo **Detalhes do erro da ordem** na FastTab **Status da sincronização**. Se nenhum desses status for exibido, significa que não houve tentativa de processar a transação. Nesse caso, você pode selecionar **Sincronizar ordem** na parte superior da página para executar o trabalho de sincronização.

Verifique se o trabalho **Ordens de sincronização** está agendado para ser executado periodicamente, de modo que as transações assíncronas sejam criadas como ordens na matriz.

As seções a seguir fornecem informações sobre alguns erros comuns e as correções propostas.

#### <a name="the-order-error-details-field-shows-the-following-error-message-number-sequence-has-been-exceeded"></a>O campo Detalhes do erro da ordem mostra a seguinte mensagem de erro: "A sequência numérica foi excedida"

As sequências numéricas são usadas para criar ordens de venda na sede. Se todos os números permitidos para uma sequência numérica esgotarem, o sistema gerará essa mensagem de erro. A sequência numérica usada para criar ordens de venda se encontrada em **Parâmetros de contas a receber \> Sequências numéricas \> Ordem de venda**. Para corrigir esse erro, corrija a sequência numérica existente ou substitua-a por uma nova.

#### <a name="the-order-error-details-field-shows-the-following-error-message-there-must-be-a-default-payment-service-to-process-credit-card-transactions"></a>O campo Detalhes do erro da ordem mostra a seguinte mensagem de erro: "deve haver um serviço de pagamento padrão para processar transações de cartão de crédito"

Para corrigir esse erro, confirme se um pagamento padrão está definido na sede. Se não houver um pagamento padrão definido, você deverá definir um. Vá para **Contas a receber \> Configuração de pagamento \> Serviços de pagamento**. Verifique se a opção **Processador padrão para novos cartões de crédito** está definida como **Sim** para um serviço de pagamento.
    
#### <a name="the-order-error-details-field-shows-an-account-structure-error-message"></a>O campo Detalhes do erro da ordem mostra uma mensagem de erro da estrutura de conta

O texto da mensagem de erro da estrutura da conta pode variar, como mostram os exemplos a seguir. No entanto, os erros compartilham uma causa raiz comum relacionada à configuração da estrutura de conta.

- "Os resultados do lançamento para número de lote do diário 0009656328 Comprovante ARP-000959899 1.00 para o comprovante ARP-000959899 na empresa usrt serão lançados como um pagamento a maior ou a menor"
- "Os resultados do lançamento para número de lote do diário 0009656328 Comprovante ARP-000959899 Comprovante ARP-000959901 Estrutura da conta, para a combinação 618160, não é válido para o razão Conta Principal Corporativa Compartilhada"
- "Os resultados do lançamento para o número de lote do diário 0009656328 Comprovante ARP-000959899 Comprovante ARP-000959901 Relatado de contas de empresa usrt"
- "Resultados do lançamento para número de lote do diário 0009656328 Comprovante ARP-000959899 Lançamento foi cancelado"
    
Para corrigir esses erros, revise as estruturas de conta para obter precisão. Para saber mais, consulte [Configurar estruturas de conta](/dynamics365/finance/general-ledger/configure-account-structures).
    
Após a correção do erro, selecione a transação com falha e, depois, selecione **Sincronizar ordem** na parte superior da página para executar o trabalho de sincronização.
    
#### <a name="other-types-of-errors-that-might-require-the-transaction-data-to-be-fixed"></a>Outros tipos de erros que podem exigir a correção de dados da transação

Para corrigir outros tipos de erros que possam exigir a correção de dados da transação, você pode usar o recurso "Editar e auditar transações". Para obter mais informações, consulte [Editar e auditar transações](../edit-order-trans.md).
