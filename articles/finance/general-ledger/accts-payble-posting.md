---
title: Lançamentos de Contas a pagar
description: Este artigo explica como as postagens são configuradas em Contas a pagar e fornece exemplos de configurações de lançamento.
author: rachel-profitt
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPosting, VendPaymMode, VendCashDiscount, MarkupTable\_Vend, VendPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b3593e01ed4d0a88b5816803f1d67fa7ed5e0f6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907999"
---
# <a name="accounts-payable-posting"></a>Lançamento de Contas a pagar

[!include [banner](../includes/banner.md)]

O perfil de lançamento principal do módulo **Contas a pagar** é o perfil de lançamento de fornecedor. Este perfil de lançamentos determina a conta de resumo usada quando saldos de fornecedores são lançados na contabilidade. Uma conta de resumo é uma conta principal. Também é conhecida como conta comercial de Contas a pagar.

Para obter mais informações, consulte [Perfis de lançamento de fornecedor](../accounts-payable/vendor-posting-profiles.md).

Várias configurações de lançamento além do perfil de lançamentos de fornecedor estão disponíveis em Contas a pagar. As seções a seguir fornecem mais informações sobre essas outras configurações de lançamento.

## <a name="methods-of-payment-posting-accounts"></a>Métodos de contas de lançamento de pagamento

Os métodos de pagamento definem como um pagamento será lançado na contabilidade. Eles também controlam o comportamento da saída do pagamento. Normalmente, um método de pagamento é criado para cada tipo de pagamento que sua organização faz (por exemplo, dinheiro, cheque, cartão de crédito, ordem de pagamento e transferência eletrônica).

Os campos na seção **Lançamento** da Guia Rápida **Geral** na página **Métodos de pagamento** (**Contas a pagar > Configuração de pagamentos > Métodos de pagamento**) controlam como um pagamento será lançado na contabilidade. Primeiro você deve selecionar um valor no campo **Tipo de conta**. O tipo de conta selecionado controla o comportamento do campo **Conta de pagamento**. Recomendamos que você selecione **Banco** no campo **Tipo de conta** e selecione a conta bancária no campo **Conta de pagamento**. A vantagem da abordagem é que o sistema lançará o pagamento no Razão auxiliar do banco, que oferece suporte à reconciliação e a outros processos relacionados ao caixa. A tabela a seguir mostra um exemplo da configuração do perfil de lançamento se você estiver usando o módulo **Gerenciamento de caixa e de banco**.

| Tipo de lançamento | Tipo de conta | Exemplo de nome de conta de pagamento | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|--------------|------------------------------|--------------|---------------|------------------|-------------|
| Banco | Banco | Bank of America | Conta bancária vinculada a um ativo | Débito | Não | Para cada método de pagamento, insira a conta principal no campo **Conta de pagamento**. |

Se você não estiver planejando usar o Gerenciamento de caixa e de bancos, selecione **Razão** no campo **Tipo de conta** e, em seguida, selecione a conta principal no campo **Conta de pagamento**. A tabela a seguir mostra um exemplo da configuração do perfil de lançamento se você **não** estiver usando o Gerenciamento de caixa e de banco.

| Tipo de lançamento | Tipo de conta |Exemplo de conta de pagamento | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|--------------|------------------------|--------------|---------------|------------------|-------------|
| Ledger | Ledger | 100100: Bank of America | Ativo | Débito | Não | Para cada método de pagamento, insira a conta principal no campo **Conta de pagamento**. |

## <a name="bridging-accounts"></a>Contas de transição

O lançamento de transição é um processo de duas etapas usado quando os pagamentos são lançados. É um recurso opcional que pode ser usado com contas bancárias de saldo zero, por exemplo. Pode ajudar a garantir um processo de reconciliação bancária mais suave e oportuno. Na primeira etapa, um pagamento é lançado em uma conta temporária (a conta de transição). Na segunda etapa, a entrada lançada é revertida e lançada na conta bancária quando o pagamento limpa o banco. A tabela a seguir mostra um exemplo da configuração do perfil de lançamento para lançamento de transição.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Diário-razão | 130725 | Dinheiro Não Compensado | Passivo | Débito | Sim | Para cada método de pagamento, insira a conta principal no campo **Conta de transição**. |

Para obter mais informações, consulte [Configurar e processar pagamentos de transição](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="customer-cash-discounts-posting-accounts"></a>Contas de lançamento de descontos à vista do cliente

Se a sua organização receber descontos à vista de fornecedores em troca de pagamento rápido, você deverá configurar códigos de desconto à vista e especificar como os descontos devem ser lançados na contabilidade. Várias opções estão disponíveis para especificar a conta principal usada para lançar um desconto à vista do cliente.

Para obter mais informações, consulte [Descontos à vista](../cash-bank-management/cash-discounts.md).

## <a name="payment-fee-posting-accounts"></a>Contas de lançamento de valores de pagamento

Os valores de pagamento permitem que você adicione automaticamente um valor a um pagamento de fornecedor quando um conjunto de condições se aplicar. Os valores de pagamento podem ser pagas ao fornecedor ou podem ser lançadas em sua conta bancária como uma despesa. Veja alguns exemplos:

- Um fornecedor cobra 3% do total do pagamento se você pagar usando um cartão de crédito.
- Seu banco cobra US$ 1,00 por cada transferência eletrônica que você processa e o valor eletrônico é cobrado.

Ao configurar um valor de pagamento de fornecedor, se você definir o campo **Encargo** como **Fornecedor**, o campo **Conta principal** não ficará disponível e o sistema usará o perfil de lançamento de fornecedor para lançar a taxa. Se você definir o campo **Encargo** como **Razão**, deverá definir o campo **Conta principal** como a conta principal na qual o valor do pagamento será lançado. Tipicamente, essa conta será uma conta de despesa. A tabela a seguir mostra um exemplo da configuração do perfil de lançamento para lançamento de valor de pagamento.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|----------------------|---------------------------|--------------|----------------|------------------|-------------|
| Diário-razão | 618190 | Despesa de Tarifa Bancária | Despesa | Débito | Não | Se **Razão** estiver selecionado no campo **Encargo**, escolha essa conta no campo **Conta principal** na página **Valor de pagamento**. |

Para obter mais informações, consulte [Definir taxas de pagamento de fornecedor](../accounts-payable/tasks/define-vendor-payment-fees.md).

## <a name="charges-code-posting-accounts"></a>Contas de lançamento de código de encargos

Se tiver de rastrear valores de compra além das linhas de item, você poderá usar códigos de encargos. Por exemplo, seu fornecedor pode cobrar as taxas de frete e manuseio de você, ou pode custar algumas taxas de frete e manuseio internamente. Você pode especificar se esses valores serão lançados em contas de despesas ou adicionados ao custo dos itens.

Você pode criar códigos de encargos para Contas a receber e Contas a pagar. Ao configurar um código de encargos, você deverá definir o lançamento. O lançamento controla a conta de débito e a conta de crédito. Ao criar códigos de encargos, você poderá selecionar o tipo de lançamento usado para cada código de encargo. A tabela a seguir mostra exemplos de códigos de encargos típicos para Contas a pagar na página **Códigos de encargos**.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Taxa de compra | Deixe o campo em branco. | Não aplicável | Item | Débito | Não | **Exemplo de um valor de compra para um item:** </p><ul><li>Campo **Tipo de débito** = **Item**</li><li>  Campo **Tipo de crédito** = **Cliente/Fornecedor**.</li><li> O lançamento do item usa a conta principal do perfil de lançamento de estoque. |
| Ordem, frete | 600120 | Frete de Entrada | Renda | Débito | Não | **Exemplo de frete pago a um fornecedor:** </p><ul><li>Campo **Tipo de débito** = **Conta contábil**</li><li> Campo **Tipo de crédito** = **Cliente/Fornecedor** |
| Reembolso\* | 503160 | Reembolso de Fornecedor (Contra COGS)| Despesa | Crédito | Não | **Exemplo de um reembolso de fornecedor:**</p><ul><li>Campo **Tipo de débito** = **Cliente/Fornecedor**</li><li>Campo **Tipo de crédito** = **Conta contábil** |

\* Para o exemplo de reembolso, o lançamento só será usado quando um código de encargos for adicionado a uma linha ou a um cabeçalho da ordem de compra. A funcionalidade avançada de reembolso disponível no Microsoft Dynamics 365 Supply Chain Management oferece mais controle e automação de reembolsos. Para obter mais informações, consulte [Reembolsos de fornecedor](../../supply-chain//procurement/vendor-rebates.md).

A tabela anterior mostra três exemplos típicos de tipos de lançamento que podem ser usados para códigos de encargos. Ele deve ser usado como uma diretriz e uma seleção de exemplos. Ele não fornece uma lista abrangente de todas as combinações possíveis ou tipos de lançamento que podem ser usados.

Para obter mais informações, consulte [Criar código de encargos](../accounts-receivable/create-charges-codes.md).
