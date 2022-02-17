---
title: Lançamento de contas a receber
description: Este tópico explica como os lançamentos são configurados em Contas a receber e fornece exemplos de configurações de lançamento.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustPaymMode, CustCashDiscount, CommissionPosting, MarkupTable\_Cust, CustPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e664c42461e4f2995cac9a747d85d0f2a0fdf85
ms.sourcegitcommit: 96f936267d3f314f06da6ce6f809eba2ec3b205f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2022
ms.locfileid: "8021596"
---
# <a name="accounts-receivable-posting"></a>Lançamento de contas a receber

[!include [banner](../includes/banner.md)]

O perfil de lançamento principal do módulo **Contas a receber** é o perfil de lançamento de cliente. Este perfil de lançamentos determina a conta de resumo usada quando saldos de clientes são lançados na contabilidade. Uma conta de resumo é uma conta principal. Ela também é conhecida como conta comercial de Contas a receber.

Para obter mais informações, consulte [Perfis de postagem do cliente](../accounts-receivable/customer-posting-profiles.md).

Várias configurações de lançamento além do perfil de lançamentos de cliente estão disponíveis em Contas a receber. As seções a seguir fornecem mais informações sobre essas outras configurações de lançamento.

## <a name="posting-accounts-for-methods-of-payment"></a>Contas de lançamento para métodos de pagamento

Os métodos de pagamento definem como um pagamento será lançado na contabilidade. Eles também controlam o comportamento da saída do pagamento. Normalmente, um método de pagamento é criado para cada tipo de pagamento que sua organização aceita (por exemplo, dinheiro, cheque, cartão de crédito, ordem de pagamento e transferência eletrônica).

Os campos na seção **Lançamento** na FastTab **Geral** controlam como um pagamento será lançado na contabilidade. Primeiro você deve selecionar um valor no campo **Tipo de conta**. O tipo de conta selecionado controla o comportamento do campo **Conta de pagamento**. Recomendamos que você selecione **Banco** no campo **Tipo de conta** e selecione a conta bancária no campo **Conta de pagamento**. A vantagem desta abordagem é que o sistema lançará o pagamento no Razão auxiliar do banco, que oferece suporte à reconciliação e a outros processos relacionados ao caixa. A tabela a seguir mostra um exemplo da configuração do perfil de lançamento se você estiver usando o módulo **Gerenciamento de caixa e de banco**.

| Tipo de lançamento | Tipo de conta | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Banco | Banco | Bank of Contoso | Conta bancária vinculada a um ativo | Crédito | Número | Para cada método de pagamento, insira a conta principal no campo **Conta de pagamento**. |

Se você não pretende usar o Gerenciamento de caixa e de bancos, selecione **Razão** no campo **Tipo de conta** e, depois, selecione a conta principal no campo **Conta de pagamento**. Veja um exemplo da configuração do perfil de lançamento na tabela a seguir se você não estiver usando o Gerenciamento de caixa e de bancos.

| Tipo de lançamento | Tipo de conta | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Razão | Razão | 100100: Bank of Contoso | Ativo | Crédito | Número | Para cada método de pagamento, insira a conta principal no campo **Conta de pagamento**. |

## <a name="bridging-accounts"></a>Contas de transição

O lançamento de transição é um processo de duas etapas usado quando os pagamentos são lançados. É um recurso opcional que pode ser usado com contas bancárias de saldo zero, por exemplo. Pode ajudar a garantir um processo de reconciliação bancária mais suave e oportuno. Na primeira etapa, um pagamento é lançado em uma conta temporária (a conta de transição). Na segunda etapa, a entrada lançada é revertida e lançada na conta bancária quando o pagamento limpa o banco. A tabela a seguir mostra um exemplo da configuração do perfil de lançamento para lançamento de transição.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Diário-razão | 130725 | Dinheiro Não Compensado | Passivo | Débito | Sim | Para cada método de pagamento, insira a conta principal no campo **Conta de transição**. |

Para obter mais informações, consulte [Configurar e processar pagamentos de transição](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="posting-accounts-for-customer-cash-discounts"></a>Contas de lançamento para descontos à vista do cliente

Se a sua organização oferecer descontos à vista a clientes em troca de pagamento rápido, você deverá configurar códigos de desconto à vista e especificar como os descontos devem ser lançados na contabilidade. Várias opções estão disponíveis para especificar a conta principal usada para lançar um desconto à vista do cliente.

Para obter mais informações, consulte [Descontos à vista](../cash-bank-management/cash-discounts.md).

## <a name="posting-accounts-for-payment-fees"></a>Contas de lançamento para taxas de pagamento

As taxas de pagamento permitem que você adicione automaticamente um valor a um pagamento de cliente quando um conjunto de condições se aplicar. As taxas de pagamento podem ser cobradas do cliente ou podem ser lançadas em sua conta bancária como uma despesa. Veja alguns exemplos:

- Você cobrará dos clientes 3% do total do pagamento se eles pagarem usando um cartão de crédito.
- Seu banco cobra US$ 1,00 por cada transferência eletrônica processada e a taxa da transferência eletrônica é cobrado.

Ao configurar um valor de pagamento de cliente, se você definir o campo **Encargo** como **Cliente**, o campo **Conta principal** ficará indisponível e o sistema usará o perfil de lançamento de cliente para lançar a taxa. Se você definir o campo **Encargo** como **Razão**, deverá definir o campo **Conta principal** como a conta principal na qual o valor do pagamento será lançado. Tipicamente, essa conta será uma conta de despesa. A tabela a seguir mostra um exemplo da configuração do perfil de lançamento para lançamento de valor de pagamento.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Diário-razão | 618190 | Despesa de Tarifa Bancária | Despesa | Débito | Não |  Se **Razão** estiver selecionado no campo **Encargo**, escolha essa conta no campo **Conta principal** para a taxa de pagamento. |

Para obter mais informações, consulte [Estabelecer taxas de pagamento de clientes](../accounts-receivable/tasks/establish-customer-payment-fees.md).

## <a name="posting-accounts-for-charges-codes"></a>Contas de lançamento para códigos de encargos

Se precisar rastrear valores de vendas além das linhas de item, você poderá usar códigos de encargos. Por exemplo, você pode cobrar taxas de frete e manuseio dos clientes, ou pode cobrar algumas taxas de frete e manuseio internamente. Você pode especificar se esses valores serão lançados em contas de despesas ou adicionados ao custo dos itens.

Você pode criar códigos de encargos para Contas a receber e Contas a pagar. Ao configurar um código de encargos, você deverá definir o lançamento. O lançamento controla a conta de débito e a conta de crédito. Para cada código de encargos criado, você pode selecionar o tipo de lançamento utilizado. A tabela a seguir mostra exemplos típicos de códigos de encargos para Contas a receber.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Taxa de pagamento | 411400 | Receita – taxas | Receita | Crédito | Número | **Exemplo para fundos não suficientes:** Debitar cliente/fornecedor e creditar conta contábil |
| Ordem, frete | 403500 | Receita – frete | Renda | Crédito | Número | **Exemplo de frete cobrado de um cliente:** debitar cliente/fornecedor e creditar conta contábil |
| Reembolso\* | 403200 | Desconto | Receita | Débito | Número | **Exemplo para reembolso de um cliente:** Debitar conta contábil e creditar cliente/fornecedor |

\* Para o exemplo de reembolso, o lançamento só será usado quando um código de encargos for adicionado a uma linha ou a um cabeçalho da ordem de compra. A funcionalidade avançada de reembolso disponível no Microsoft Dynamics 365 Supply Chain Management oferece mais controle e automação de reembolsos. Para obter mais informações, consulte [Reembolsos do cliente](../../supply-chain/sales-marketing/tasks/process-customer-rebates.md).

A tabela anterior mostra três exemplos típicos de tipos de lançamento que podem ser usados para códigos de encargos. Ela deve ser usada como uma diretriz e um exemplo. Ele não fornece uma lista abrangente de todas as combinações possíveis ou tipos de lançamento que podem ser usados.

Para obter mais informações, consulte [Criar código de encargos](../accounts-receivable/create-charges-codes.md).

## <a name="posting-accounts-for-commissions"></a>Contas de lançamento para comissões

Opcionalmente, você pode configurar o sistema para calcular comissões de um representante de vendas ou um grupo de representantes de vendas em determinada ordem de venda. Se você habilitar essa funcionalidade, deverá configurar a conta de lançamento usada para calcular a comissão. Essa configuração é feita na página **Lançamento da comissão** no módulo **Vendas e marketing**.

Para obter mais informações, consulte [Configurar regras de comissão de vendas](../../supply-chain/sales-marketing/tasks/set-up-sales-commission-rules.md).
