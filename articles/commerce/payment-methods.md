---
title: Métodos de pagamento
description: Cada tipo de pagamento que o varejista aceita deve ser configurado quando o sistema for configurado. Este artigo descreve os tipos de pagamento que você pode configurar e descreve o processo para defini-los para cima.
author: rubencdelgado
ms.date: 06/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 414b49d1099575f1626c29e8f3b07f522e3ab370
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804494"
---
# <a name="payment-methods"></a>Métodos de pagamento

[!include [banner](includes/banner.md)]

Cada tipo de pagamento que o varejista aceita deve ser configurado quando o sistema for configurado. Este artigo descreve os tipos de pagamento que você pode configurar e descreve o processo para defini-los para cima.

Os varejistas podem aceitar vários tipos de pagamento em troca de produtos e serviços vendidos. Embora o pagamento à vista seja a forma mais comum de pagamento, os varejistas também podem receber pagamento em forma de cheques, cartões, comprovantes, etc. Cada tipo de pagamento que o varejista aceita deve ser configurado no Dynamics 365 Commerce quando o sistema for configurado. A lista a seguir descreve cada tipo de pagamento que pode ser configurado:

- **Pagamento à vista** – dinheiro em sua forma física, como cédulas e moedas. A moeda pode ser a moeda da empresa ou a moeda local da loja.
- **Cheque** – um instrumento negociável que instrui o pagamento de um valor específico em uma determinada moeda e que é emitido em um banco específico. Um cheque é normalmente válido por tempo indeterminado ou por seis meses após a data de saída, a menos que seja especificado outro período de validade. Esse período varia dependendo do banco em que o cheque é emitido. Há vários tipos de cheques, como cheques nominais, cheques avulsos, cheques ao portador e cheques com cruzamento especial. É possível configurar cheques como um método de pagamento para cada loja. Os cheques podem ser aceitos na moeda definida no nível da empresa ou no nível da loja. Será necessário configurar os cheques como método de pagamento antes de ser possível aceitar um cheque como pagamento em uma loja.
- **Moeda** – a principal forma de pagamento além da moeda padrão da empresa. Moedas e cédulas são formas de moeda. O método de pagamento da moeda representa todas as moedas usadas. Antes de utilizar esse método de pagamento, será necessário configurar as moedas e especificar as informações de câmbio para as moedas.
- **Cartão** – todos os tipos de cartões usados, como cartões de crédito e de débito. É uma boa ideia configurar um método de pagamento em cartão no nível da organização para representar todos os tipos de cartão. E no nível da loja, configurar um método de pagamento para cada cartão ou conjunto de cartões, que será processado usando as mesmas configurações. Configure os cartões de fabricantes disponíveis no mercado, como cartões de crédito e de débito, para que você possa aceitar os cartões como forma de pagamento em uma loja.
- **Nota de crédito** – as notas de crédito são emitidos e resgatados no ponto de venda. A nota de crédito pode ser um crédito ou uma nota de crédito de devolução emitida para uma venda de devolução. Se as notas de crédito forem resgatadas apenas parcialmente, o programa emite uma nova nota de crédito para o novo saldo. A nova nota de crédito tem um novo número. Uma nota de crédito só pode ser usada uma vez, e o sistema mantém um registro de todos os números que serão usados. O registro pode ser exibido na página **Tabela de nota de crédito**. Um cliente não pode resgatar um valor acima da nota de crédito.
- **Vale-presente** – vales-presentes são emitidos e resgatados no ponto de venda. O pagamento a maior não é permitido em vale-presentes. Todos os vale-presentes devem ter mapeamentos de número de cartão. 
- **Conta de cliente** – pagamentos que podem ser cobrados na conta de um cliente na registradora, no momento da venda. Também é possível usar esse método de pagamento para coletar informações de vendas ou descontos específicos ao cliente quando este faz um pagamento usando outro método de pagamento. Nesse caso, você deve configurar informações específicas do cliente.
- **Pontos de fidelidade** – Os pontos que os clientes acumulam ao longo do programa de fidelidade. Se criar programas de fidelidade, os clientes podem ter pontos e resgatá-los de várias formas. Por exemplo, em alguns programas de fidelidade, os clientes podem resgatar os pontos de fidelidade na forma de um desconto ou mesmo usá-los como uma forma de pagamento.

Para configurar métodos de pagamento, conclua as tarefas a seguir.

1. Configure métodos de pagamento de uma organização. Crie os métodos de pagamento aceitos pela organização inteira.
2. Criar tipos e números de cartão no nível da organização. Se cartões de crédito ou de débito forem aceitos, você deve criar um tipo de método de pagamento com cartões e os tipos e números de cartão no nível da organização.
3. Configurar método de pagamento da loja. Associe métodos de pagamento a cada loja e insira as configurações específicas da loja para cada método de pagamento.
4. Configurar métodos de pagamento de cartão para lojas. Para todos os métodos de pagamento de cartão que a loja aceita, conclua a configuração do cartão.


[!INCLUDE[footer-include](../includes/footer-banner.md)]