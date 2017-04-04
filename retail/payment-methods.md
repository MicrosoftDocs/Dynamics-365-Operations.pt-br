---
title: "Métodos de pagamento"
description: "Cada tipo de pagamento a um fornecedor aceita deve ser configurado no retail e no comércio no Microsoft Dynamics 365 para operações quando o sistema é configurado. Este artigo descreve os tipos de pagamento que você pode configurar e descreve o processo para defini-los para cima."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: MargoC
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b887fc5d03ea8982515e92725ce98cc416e56f9e
ms.openlocfilehash: 011beec07bf1ab858892ab1c374f1acf3839e877
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods"></a>Métodos de pagamento

Cada tipo de pagamento a um fornecedor aceita deve ser configurado no retail e no comércio no Microsoft Dynamics 365 para operações quando o sistema é configurado. Este artigo descreve os tipos de pagamento que você pode configurar e descreve o processo para defini-los para cima.

Os varejistas podem aceitar vários tipos de pagamento em troca de produtos e serviços vendidos. Embora o pagamento à vista seja a forma mais comum de pagamento, os varejistas também podem receber pagamento em forma de cheques, cartões, comprovantes, etc. Cada tipo de pagamento do fornecedor deve aceitar ser configurado em dynamics 365 para operações - a vende varejo quando o sistema é configurado. A lista a seguir descreve cada tipo de pagamento que pode ser configurado em dynamics 365 para operações de varejo:

-   **Pagamento à vista** – dinheiro em sua forma física, como cédulas e moedas. A moeda pode ser a moeda da empresa ou a moeda local da loja.
-   **Cheque** – um instrumento negociável que instrui o pagamento de um valor específico em uma determinada moeda e que é emitido em um banco específico. Um cheque é normalmente válido por tempo indeterminado ou por seis meses após a data de saída, a menos que seja especificado outro período de validade. Esse período varia dependendo do banco em que o cheque é emitido. Há vários tipos de cheques, como cheques nominais, cheques avulsos, cheques ao portador e cheques com cruzamento especial. É possível configurar cheques como um método de pagamento para cada loja. Os cheques podem ser aceitos na moeda definida no nível da empresa ou no nível da loja. Será necessário configurar os cheques como método de pagamento antes de ser possível aceitar um cheque como pagamento em uma loja.
-   **Moeda** – a principal forma de pagamento além da moeda padrão da empresa. Moedas e cédulas são formas de moeda. O método de pagamento da moeda representa todas as moedas usadas em Varejo e comércio. Antes de ser possível usar esse método de pagamento, será necessário configurar as moedas e especificar as informações do comércio varejista para as moedas.
-   **Cartão** – todos os tipos de cartões usados em Varejo e comércio, como cartões de crédito e de débito. É uma boa ideia configurar um método de pagamento em cartão no nível da organização para representar todos os tipos de cartão. E no nível da loja, configurar um método de pagamento para cada cartão ou conjunto de cartões, que será processado usando as mesmas configurações. Configure os cartões de fabricantes disponíveis no mercado, como cartões de crédito e de débito, para que você possa aceitar os cartões como forma de pagamento em uma loja.
-   **Nota de crédito** – as notas de crédito são emitidos e resgatados no ponto de venda. A nota de crédito pode ser um crédito ou uma nota de crédito de devolução emitida para uma venda de devolução. Se as notas de crédito forem resgatadas apenas parcialmente, o programa emite uma nova nota de crédito para o novo saldo. A nova nota de crédito tem um novo número. Uma nota de crédito só pode ser usada uma vez, e o sistema mantém um registro de todos os números que serão usados. O registro pode ser exibido na página **Tabela de nota de crédito**. Um cliente não pode resgatar um valor acima da nota de crédito.
-   **Vale-presente** – vales-presentes são emitidos e resgatados no ponto de venda. O pagamento a maior não é permitido em vale-presentes.
-   **Conta de cliente** – pagamentos que podem ser cobrados na conta de um cliente na registradora, no momento da venda. Também é possível usar esse método de pagamento para coletar informações de vendas ou descontos específicos ao cliente quando este faz um pagamento usando outro método de pagamento. Nesse caso, você deve configurar informações específicas do cliente.
-   ** Aponta ** a fidelidade – os pontos que os clientes são acumulados dos programas de fidelidade. Se criar programas de fidelidade, os clientes podem ter pontos e resgatar-los em várias formas. Por exemplo, em alguns programas de fidelidade, os clientes podem resgatar os pontos de fidelidade na forma de um desconto ou mesmo usá-los como uma forma de pagamento.

Para configurar métodos de pagamento em Varejo e comércio, você deverá concluir as tarefas a seguir.

1.  Configure métodos de pagamento de uma organização. Crie os métodos de pagamento aceitos pela organização inteira.
2.  Criar tipos e números de cartão no nível da organização. Se cartões de crédito ou de débito forem aceitos, você deve criar um método de pagamento para cartões, e depois criar tipos e números de cartão no nível da organização.
3.  Método de instalação de pagamento da loja. Associar métodos de pagamento a cada loja, e insira as configurações específicas para cada método.
4.  Configurar métodos de pagamento de cartão para lojas. Para todos os métodos de pagamento do cartão que aceite a loja, conclua a configuração do cartão.



