---
title: Alternância offline perfeita para operações de vale-presente e memorando de crédito
description: Este artigo fornece uma visão geral de melhorias que fornecem um comutador off-line transparente para tipos de pagamento específicos.
author: BrianShook
ms.date: 02/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 20120-02-28
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: e0416a61bd5fd3b875b427ad8a6313d0e9936f0d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869152"
---
# <a name="seamless-offline-switch-for-gift-card-and-credit-memo-operations"></a>Alternância offline perfeita para operações de vale-presente e memorando de crédito

[!include [banner](../includes/banner.md)]

Se um dispositivo de ponto de venda (PDV) perder a conexão com o banco de dados do canal, a maioria das operações e transações de PDV que estão em andamento podem prosseguir após o caixa receber uma mensagem de aviso sobre a perda de conectividade. No entanto, em alguns casos, as transações têm elementos que dependem do serviço em tempo real e não há suporte para esses elementos quando o PDV está off-line. Este artigo descreve algumas funcionalidades que ajudam a reduzir o impacto da perda de conectividade nesses cenários.

## <a name="completing-gift-card-transactions-in-offline-mode"></a>Conclusão de transações de cartão-presente no modo offline

Os cartões-presente internos dependem do serviço em tempo real porque o saldo dos cartões-presentes deve ser mantido centralmente no Microsoft Dynamics 365 Commerce headquarters. Para ajudar a prevenir fraudes ou outras saídas de sincronização, vales-presentes são bloqueados assim que são adicionados a uma transação. A função de bloqueio garante que um vale-presente não possa ser usado em vários terminais ao mesmo tempo. Quando uma transação é concluída, o vale-presente é atualizado e desbloqueado.

No entanto, se o PDV perder conectividade depois que um vale-presente tiver sido adicionado a uma transação, o vale-presente poderá ficar inutilizado. Para ajudar a evitar essa situação, o Dynamics 365 Commerce tem um parâmetro que permite que as transações que incluem uma linha de vale-presente sejam concluídas enquanto o pos está off-line. Quando esse parâmetro é ativado, as transações de vale-presente forçadas a ficar off-line serão salvas juntamente com as transações offline e serão sincronizadas com o Commerce headquarters quando as transações offline forem sincronizadas. A sincronização também desbloqueará o vale-presente para que possa ser usado em outro terminal.

Para habilitar a funcionalidade para concluir transações de vale-presente depois de alternar para o modo offline, Acesse a guia **Postar** na página **Parâmetros do Commerce**. Nessa guia, localize a Guia Rápida **Cartão presente** e defina **Permitir transações de vale-presente conclusivo no modo offline** como **Sim**.

![Configuração de cartão de presente offline.](../media/gift.png)

Os parâmetros comerciais são normalmente armazenados em cache. Portanto, depois que a configuração desse parâmetro é atualizada, e a agenda de distribuição é iniciada para sincronizar a alteração no canal, a alteração pode levar até 24 horas para ter efeito. Para que a alteração seja efetivada imediatamente, redefina os serviços de informações da Internet da Microsoft (IIS).

## <a name="completing-credit-memo-transactions-in-offline-mode"></a>Conclusão de transações de memorando de crédito no modo offline

Como vales-presentes internos, os memorandos de crédito são mantidos centralmente no Commerce headquarters. O Commerce tem um parâmetro que permite que as transações de memorando de crédito sejam concluídas enquanto o PDV está off-line. Esse parâmetro funciona como o parâmetro de vale-presente mencionado na seção anterior. Quando o parâmetro é ativado, as transações de memorando de crédito que são forçadas offline são sincronizadas novamente com o banco de dados do canal, junto com outras transações que foram executadas enquanto o PDV estava off-line.

Para habilitar a funcionalidade para concluir transações de memorando de crédito depois de alternar para o modo offline, Acesse a guia **Postar** na página **Parâmetros do Commerce**. Nessa guia, localize a Guia Rápida **Memorando de crédito** e defina **Permitir transações de memorando de crédito conclusivo no modo offline** como **Sim**.

![Configuração de memorando de crédito offline.](../media/creditmemo.png)

Os parâmetros comerciais são normalmente armazenados em cache. Portanto, depois que a configuração desse parâmetro é atualizada, e a agenda de distribuição é iniciada para sincronizar a alteração no canal, a alteração pode levar até 24 horas para ter efeito. Para que a alteração seja efetivada imediatamente, redefina o IIS.

## <a name="related-articles"></a>Artigos relacionados

- [Funcionalidade de ponto de venda (PDV) offline](../pos-offline-functionality.md)
- [Operações de ponto de venda (PDV) online e offline](../pos-operations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]