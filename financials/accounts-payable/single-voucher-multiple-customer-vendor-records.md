---
title: "Comprovante único com vários registros de cliente ou de fornecedor"
description: "Este tópico fornece uma visão geral do que acontece quando você lança um único comprovante com vários registros de cliente ou de fornecedor. Esta funcionalidade será descontinuada em versões futuras do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, consequentemente, não recomendamos usar este método de lançamento devido ao impacto da contabilidade no processamento da liquidação."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 222534
ms.assetid: d4df11ce-4d36-4c66-8230-f5fc58e021bc
ms.search.region: global
ms.author: Shiva.Pandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 31040ff14b99a9b351268feb88698ac706befb55
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---

# <a name="single-voucher-with-multiple-customer-or-vendor-records"></a>Comprovante único com vários registros de cliente ou de fornecedor

[!include[banner](../includes/banner.md)]


Este tópico fornece uma visão geral do que acontece quando você lança um único comprovante com vários registros de cliente ou de fornecedor. Esta funcionalidade será descontinuada em versões futuras do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, consequentemente, não recomendamos usar este método de lançamento devido ao impacto da contabilidade no processamento da liquidação. 

Alguns exemplos comuns em que um comprovante é usado para vários clientes ou fornecedores incluem a transferência de saldo entre clientes e a remuneração de saldos entre clientes e fornecedores na mesma organização. 

Um comprovante que contenha mais de um cliente ou fornecedor pode ser inserido usando-se um dos seguintes métodos:

-   Usar um diário que tenha a opção **Apenas um número de comprovante** selecionada de modo que cada linha adicionada ao diário seja incluída no mesmo comprovante.
-   Usar um comprovante de várias linhas, em que não haja nenhuma conta contábil de compensação, com mais de um cliente ou fornecedor.
-   Inserir um comprovante com a conta e a contrapartida como sendo fornecedor/fornecedor, cliente/cliente, fornecedor/cliente, ou cliente/fornecedor.

Este tópico mostra como a liquidação será processada quando um comprovante com vários registros de cliente ou de fornecedor é lançado. Adicionalmente, este tópico fornece soluções alternativas para ajudar você a entender como evitar usar um comprovante com vários clientes ou fornecedores. Particularmente, há exemplos que ilustram dois cenários comuns de liquidação que são afetados pelo uso de um comprovante com vários clientes ou fornecedores:

-   A contabilização de descontos à vista
-   A contabilização de reavaliações

## <a name="how-does-settlement-impact-single-voucher-usage"></a>Como a liquidação impacta o uso de comprovantes únicos
Ao lançar um comprovante que contém vários registros de cliente ou de fornecedor, é criado um comprovante contábil único que contém vários saldos de contas a receber ou de contas a pagar. Durante o processo de liquidação, as entradas contábeis originais são usadas para criar as entradas contábeis para descontos à vista, lucros e perdas não realizados, lucros e perdas realizados, e a compensação na conta resumo do documento original. Por exemplo, se um desconto à vista for aplicado ao liquidar um pagamento de fornecedor de uma fatura, a conta de desconto à vista deverá fazer o lançamento na conta contábil de contas a pagar da fatura original. Se a fatura original for lançada em um comprovante que contenha vários registros de fornecedor, a contabilidade original será resumida. Nesse caso, como não há uma forma de acessar a contabilidade detalhada para cada transação de fornecedor em um único comprovante, não há nenhuma forma de determinar como o usuário pretendeu que o desconto à vista fosse contabilizado.

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-cash-discount-accounting"></a>Um comprovante com vários fornecedores e o impacto na contabilização de descontos à vista

No exemplo a seguir, várias faturas de fornecedor são registradas na contabilidade em um único comprovante na página **Diário geral**. Essas faturas são distribuídas entre várias dimensões de conta.

|             |                  |              |                 |           |            |
|-------------|------------------|--------------|-----------------|-----------|------------|
| **Comprovante** | **Tipo de conta** | **Conta**  | **Descrição** | **Débito** | **Crédito** |
| GNJL001     | Fornecedor           | 1001         | INV1            |           | 100,00     |
| GNJL001     | Fornecedor           | 1001         | INV2            |           | 200,00     |
| GNJL001     | Fornecedor           | 1001         | INV3            |           | 300,00     |
| GNJL001     | Razão           | 606300-001-- | INV1            |   50,00   |            |
| GNJL001     | Razão           | 606300-002-- | INV1            |   50,00   |            |
| GNJL001     | Razão           | 606300-003-- | INV2            | 200,00    |            |
| GNJL001     | Razão           | 606300-004-- | INV3            | 300,00    |            |

Após o lançamento, um comprovante é criado.

|             |              |                  |                                    |
|-------------|--------------|------------------|------------------------------------|
| **Comprovante** | **Conta**  | **Tipo de lançamento** | **Valor na moeda da transação** |
| GNJL001     | 606300-001-- | Diário-razão   | 50,00                              |
| GNJL001     | 606300-002-- | Diário-razão   | 50,00                              |
| GNJL001     | 606300-003-- | Diário-razão   | 200,00                             |
| GNJL001     | 606300-004-- | Diário-razão   | 300,00                             |
| GNJL001     | 200110-001-  | Saldo de fornecedor   | -100,00                            |
| GNJL001     | 200110-001-  | Saldo de fornecedor   | -200,00                            |
| GNJL001     | 200110-001-  | Saldo de fornecedor   | -300,00                            |

Observe que o comprovante contém três entradas do tipo de lançamento de saldo de fornecedor em um único comprovante. Não há como indicar que o débito de 50,00 para 606300-001 e o débito de 50,00 para 606300-002 sejam destinados a compensar o saldo do fornecedor de 200110-001. Isso porque o usuário inseriu vários registros de fornecedor em um único comprovante.

Usando este exemplo, podemos analisar o impacto que o uso de um comprovante tem no downstream da contabilização de liquidação. Suponha que você pague 197,00 da fatura de 200,00, obtendo um desconto à vista de 3,00. Observe que o valor da conta de desconto é alocado em todas as dimensões das contas de despesa do comprovante da fatura. Isso ocorre porque um comprovante foi usado para lançar a fatura acima, sem nenhuma indicação de como o usuário pretendeu que as distribuições de despesas se correlacionassem com o saldo do fornecedor em um único comprovante.

|             |              |                      |           |            |
|-------------|--------------|----------------------|-----------|------------|
| **Comprovante** | **Conta**  | **Tipo de lançamento**     | **Débito** | **Crédito** |
| APPAYM001   | 200110-001-  | Saldo de fornecedor       | 197.00    |            |
| APPAYM001   | 110110-001-  | Banco                 |           | 197.00     |
| 14000056    | 520200-001-- | Desconto à vista do fornecedor |           | 0.25       |
| 14000056    | 520200-002-- | Desconto à vista do fornecedor |           | 0.25       |
| 14000056    | 520200-003-- | Desconto à vista do fornecedor |           | 1.00       |
| 14000056    | 520200-004-- | Desconto à vista do fornecedor |           | 1.50       |
| 14000056    | 200110-001-  | Saldo de fornecedor       | 3,00      |            |

Se o usuário estiver descontente com a alocação do desconto à vista em todas distribuições de despesas da fatura original, em vez de um comprovante, vários comprovantes devem ser usados para registrar as faturas. Veja um exemplo de como vários comprovantes podem ser inseridos na contabilidade, em vez de usar um comprovante, conforme mostrado no início deste exemplo.

|             |                  |              |                 |           |            |                 |                    |
|-------------|------------------|--------------|-----------------|-----------|------------|-----------------|--------------------|
| **Comprovante** | **Tipo de conta** | **Conta**  | **Descrição** | **Débito** | **Crédito** | **Tipo de compensação** | **Contrapartida** |
| GNJL001     | Fornecedor           | 1001         | INV1            |           | 100,00     | Razão          | &lt;em branco&gt;:      |
| GNJL001     | Razão           | 606300-001-- | INV1            |   50,00   |            | Razão          | &lt;em branco&gt;:      |
| GNJL001     | Razão           | 606300-002-- | INV1            |   50,00   |            | Razão          | &lt;em branco&gt;:      |
| GNJL002     | Fornecedor           | 1001         | INV2            |           | 200,00     | Razão          | 606300-003--       |
| GNJL003     | Fornecedor           | 1001         | INV3            |           | 300,00     | Razão          | 606300-004--       |

Agora, quando INV2 for pago, a entrada a seguir será feita. Observe que as dimensões financeiras do desconto à vista acompanham as dimensões financeiras da despesa associada.

|             |              |                      |           |            |
|-------------|--------------|----------------------|-----------|------------|
| **Comprovante** | **Conta**  | **Tipo de lançamento**     | **Débito** | **Crédito** |
| APPAYM001   | 200110-001-  | Saldo de fornecedor       | 197.00    |            |
| APPAYM001   | 110110-001-  | Banco                 |           | 197.00     |
| 14000056    | 520200-003-- | Desconto à vista do fornecedor |           | 3,00       |
| 14000056    | 200110-001-  | Saldo de fornecedor       | 3,00      |            |

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-realized-gainloss-accounting"></a>Um comprovante com vários fornecedores e o impacto na contabilidade de lucros/perdas realizadas

|             |                  |             |                 |           |            |                  |              |
|-------------|------------------|-------------|-----------------|-----------|------------|------------------|--------------|
| **Comprovante** | **Tipo de conta** | **Conta** | **Descrição** | **Débito** | **Crédito** | **Tipo de conta** | **Conta**  |
| GNJL001     | Fornecedor           | 1001        | INV1            |           | 100,00     | Razão           | 606300-001-- |
| GNJL001     | Fornecedor           | 1001        | INV2            |           | 200,00     | Razão           | 606300-002-- |

No exemplo a seguir, várias faturas de fornecedor são registradas na contabilidade em um único comprovante na página **Diário geral**. Essas faturas são distribuídas entre várias dimensões de conta. Após o lançamento, um comprovante é criado.

|             |              |                  |                                          |                                         |
|-------------|--------------|------------------|------------------------------------------|-----------------------------------------|
| **Comprovante** | **Conta**  | **Tipo de lançamento** | **Valor na moeda da transação (EUR)** | **Valor na moeda contábil (USD)** |
| GNJL001     | 606300-001-- | Diário-razão   | 100,00                                   | 114.00                                  |
| GNJL001     | 606300-002-- | Diário-razão   | 200,00                                   | 228.00                                  |
| GNJL001     | 200110-001-  | Saldo de fornecedor   | -100,00                                  | -114,00                                 |
| GNJL001     | 200110-001-  | Saldo de fornecedor   | -200,00                                  | -228,00                                 |

Observe que o comprovante contém duas entradas do tipo de lançamento de saldo de fornecedor em um único comprovante. Não há como indicar que o débito para 606300-001 seja destinado para compensar a entrada de 100,00 do saldo do fornecedor de 200110-001. Isso ocorre porque o usuário inseriu vários registros de fornecedor em um único comprovante. 

Usando este exemplo, podemos analisar o impacto que o uso de um comprovante tem no downstream da contabilização de liquidação. Suponha que a moeda contábil seja USD e as transações acima foram lançadas em uma moeda de transação de euros (EUR). Suponha que você pague totalmente a fatura de 200,00 euros, mas que encontre uma perda realizada devido à diferença na taxa de câmbio entre o tempo que você lançou a fatura e o pagamento. Observe que o valor da conta de perda realizada é alocado em todas as dimensões das contas de despesa do comprovante da fatura. Nesse caso, as dimensões 001 e 002 foram alocadas, embora o usuário possa ter a impressão de que somente 002 pertença à conta de despesas da fatura que estiver sendo liquidada. Isso ocorre porque um comprovante foi usado para lançar a fatura acima, não deixando nenhuma forma de indicar como o usuário pretendeu que as distribuições de despesas se correlacionassem com o saldo do fornecedor em um único comprovante.

|             |             |                    |                                          |                                         |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| **Comprovante** | **Conta** | **Tipo de lançamento**   | **Valor na moeda da transação (EUR)** | **Valor na moeda contábil (USD)** |
| APPAYM001   | 200110-001- | Saldo de fornecedor     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Banco               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-001- | Perda cambial | 0,00                                     | 0.67                                    |
| 14000056    | 801300-002- | Perda cambial | 0,00                                     | 1.33                                    |
| 14000056    | 200110-001- | Saldo de fornecedor     |                                          | -2,00                                   |

Se o usuário estiver descontente com a alocação da perda da taxa de câmbio em todas distribuições de despesas da fatura original, em vez de um comprovante, vários comprovantes devem ser usados para registrar as faturas. Veja um exemplo de como vários comprovantes podem ser inseridos na contabilidade, em vez de usar um comprovante, conforme mostrado no início deste exemplo.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Comprovante** | **Tipo de conta** | **Conta** | **Descrição** | **Débito** | **Crédito** | **Tipo de compensação** | **Contrapartida** |
| GNJL002     | Fornecedor           | 1001        | INV1            |           | 100,00     | Razão          | 606300-001--       |
| GNJL003     | Fornecedor           | 1001        | INV2            |           | 200,00     | Razão          | 606300-002--       |

Agora, quando INV2 for pago, a entrada a seguir será feita. Observe que as dimensões financeiras da perda da taxa de câmbio acompanham as dimensões financeiras da despesa associada.

|             |             |                    |                                          |                                         |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| **Comprovante** | **Conta** | **Tipo de lançamento**   | **Valor na moeda da transação (EUR)** | **Valor na moeda contábil (USD)** |
| APPAYM001   | 200110-001- | Saldo de fornecedor     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Banco               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-002- | Perda cambial | 0,00                                     | 2.00                                    |
| 14000056    | 200110-001- | Saldo de fornecedor     |                                          | -2,00                                   |

## <a name="one-voucher-for-balance-transfers-and-netting-scenarios"></a>Um comprovante para transferências de saldo e cenários de remuneração
Dois cenários de uso comum que utilizam um comprovante que contenha vários clientes ou fornecedores incluem transferências de um cliente/fornecedor a outro cliente/fornecedor e a remuneração de um cliente e um fornecedor que sejam a mesma organização. Os dois exemplos a seguir ilustram o método preferido para inserir esses cenários no Finanças e Operações como uma alternativa a inseri-los em um comprovante. 

Uma *transferência de saldo* é um comprovante com vários clientes, inserido com a finalidade de transferir o saldo de um cliente para outro (o mesmo para fornecedores). Este cenário pode ocorrer quando a responsabilidade de pagar a fatura muda para outra parte, como uma empresa filial mudando a responsabilidade para a matriz. 

Este exemplo usa uma venda em que o cliente esteja qualificado para obter um desconto à vista se o pagamento for feito em 10 dias. O cliente neste exemplo utiliza uma seguradora que é responsável por pagar a conta. A seguradora é configurada como um segundo cliente no sistema. O saldo original do cliente é transferido para a seguradora, que paga a conta, obtendo um desconto à vista de 2% por pagar dentro do período de desconto. 

Para ilustrar, suponha que a venda a seguir foi feita ao cliente ACME. As entradas contábeis a seguir representam a venda.

|                    |                  |           |            |
|--------------------|------------------|-----------|------------|
| **Conta contábil** | **Tipo de lançamento** | **Débito** | **Crédito** |
| 401100-002-023-    | Receita          |           | 100        |
| 130100-002-        | Saldo do cliente | 100       |            |

Em seguida, o usuário transfere o saldo devido da ACME para a seguradora, em um comprovante no diário de pagamentos de contas a receber. No Finanças e Operações, a seguradora será configurada como o cliente Seguradora.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Comprovante** | **Tipo de conta** | **Conta** | **Descrição** | **Débito** | **Crédito** | **Tipo de compensação** | **Contrapartida** |
| ARPAYM001   | Cliente         | ACME        | Transferência        |           | 100,00     | Cliente        | Seguro          |

Observe que a entrada acima está contida em um comprovante. Esse comprovante contém dois registros de cliente. O comprovante a seguir será criado quando a entrada de contabilidade acima for lançada.

|             |             |                  |                                    |
|-------------|-------------|------------------|------------------------------------|
| **Comprovante** | **Conta** | **Tipo de lançamento** | **Valor na moeda da transação** |
| ARPAYM001   | 130100-002- | Saldo do cliente | 100,00                             |
| ARPAYM001   | 130100-002- | Saldo do cliente | -100,00                            |

Em seguida, suponha que você receba um pagamento do cliente Seguradora de 98,00 e opte por liquidar o pagamento com a fatura criada pela transferência de saldo. Isso resultará no lançamento do comprovante a seguir É possível que se espere que a liquidação use as dimensões financeiras da fatura original, mas isso não é possível porque não há um documento de fatura para o cliente Seguradora. Observe que, por padrão, as dimensões de distribuição no desconto à vista vêm da transação de cliente criada a partir da transferência, não da conta de receita da fatura original. O padrão é um resultado do uso de um comprovante para transferir os saldos.

|             |             |                  |           |            |
|-------------|-------------|------------------|-----------|------------|
| **Comprovante** | **Conta** | **Tipo de lançamento** | **Débito** | **Crédito** |
| ARPAYM002   | 110110-002- | Banco             | 98.00     |            |
| ARPAYM002   | 130100-002- | Saldo do cliente |           | 98.00      |

No comprovante relacionado para o desconto à vista, o padrão para a dimensão financeira vem da transação de cliente criada a partir da transferência, pois a transferência tem mais de um cliente.

|             |             |                        |           |            |
|-------------|-------------|------------------------|-----------|------------|
| **Comprovante** | **Conta** | **Tipo de lançamento**       | **Débito** | **Crédito** |
| ARP-00001   | 403300-002- | Desconto à vista do cliente | 2.00      |            |
| ARP-00001   | 130100-002- | Saldo do cliente       |           | 2.00       |

Se o usuário estiver descontente com o padrão das dimensões financeiras para o desconto à vista, em vez de um comprovante, vários comprovantes devem ser usados para registrar a transferência de saldos. Este cenário é possível criando-se um memorando de crédito para o cliente DO QUAL o saldo for movido e um memorando ou uma fatura para o cliente PARA O QUAL o saldo for movido. O exemplo a seguir mostra como vários comprovantes podem ser inseridos no diário de pagamentos de contas a receber para transferir o saldo, em vez de usar um comprovante, conforme exibido anteriormente neste exemplo.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Comprovante** | **Tipo de conta** | **Conta** | **Descrição** | **Débito** | **Crédito** | **Tipo de compensação** | **Contrapartida** |
| ARPAYM001   | Cliente         | ACME        |                 |           | 100,00     | Razão          | 401100-002-023-    |
| ARPAYM002   | Cliente         | Seguro   |                 | 100,00    |            | Razão          | 401100-002-023-    |

Isso significa que quando o cliente Seguradora paga 98,00 com o comprovante ARPAYM02, as dimensões financeiras corretas da entrada da conta contábil do comprovante ARPAYM002 serão usadas.

|             |             |                  |           |            |
|-------------|-------------|------------------|-----------|------------|
| **Comprovante** | **Conta** | **Tipo de lançamento** | **Débito** | **Crédito** |
| ARPAYM003   | 110110-002- | Banco             | 98.00     |            |
| ARPAYM003   | 130100-002  | Saldo do cliente |           | 98.00      |

No comprovante relacionado para o desconto à vista, as dimensões financeiras serão usadas da conta de receita de compensação mostrada no comprovante ARPAYM002.

|             |                 |                        |           |            |
|-------------|-----------------|------------------------|-----------|------------|
| **Comprovante** | **Conta**     | **Tipo de lançamento**       | **Débito** | **Crédito** |
| ARP-00001   | 403300-002-023- | Desconto à vista do cliente | 2.00      |            |
| ARP-00001   | 130100-002-     | Saldo do cliente       |           | 2.00       |

### 

## <a name="one-voucher-with-a-netting-for-multiple-customers-and-vendors"></a>Um comprovante com uma remuneração para vários clientes e fornecedores
A remuneração pode ser útil quando uma organização compra e vende para a mesma empresa. Em vez de pagar faturas do fornecedor e aguardar para receber o pagamento das faturas do cliente, as faturas do fornecedor e do cliente são remuneradas. A transação de remuneração é liquidada em relação aos saldos pendentes. 

Para ilustrar, suponha que o fornecedor 1001 e o cliente US-008 sejam a mesma entidade, portanto sua organização deseja remunerar os saldos a pagar e a receber antes de pagar/receber o saldo restante. Suponha que o registro de cliente deva EUR 75,00 e o registro do fornecedor deva receber EUR 100,00, o que significa que você preferiria remunerar os saldos e pagar somente EUR 25,00 ao fornecedor. Suponha também que a moeda contábil seja USD. Nesse caso, uma transação de remuneração será inserida em um comprovante no diário de pagamentos de contas a pagar.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Comprovante** | **Tipo de conta** | **Conta** | **Descrição** | **Débito** | **Crédito** | **Tipo de compensação** | **Contrapartida** |
| APPAYM001   | Fornecedor           | 1001        | Remuneração         |  75,00    |            | Cliente        | US-008             |

Para evitar problemas indesejados com futuros pagamentos para esta transação, em vez de usar um comprovante, vários comprovantes devem ser inseridos no diário para registrar a transação de remuneração. Observe que os saldos do cliente e do fornecedor são compensados com uma única conta de compensação para evitar o uso de um comprovante que contenha vários saldos de cliente e de fornecedor.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Comprovante** | **Tipo de conta** | **Conta** | **Descrição** | **Débito** | **Crédito** | **Tipo de compensação** | **Contrapartida** |
| 001         | Cliente         | US-008      |                 |           |  75,00     | Razão          | 999999---          |
| 002         | Fornecedor           | 1001        |                 |  75,00    |            | Razão          | 999999---          |

 




