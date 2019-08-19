---
title: Pagamentos de impostos no Brasil
description: Este tópico fornece informações sobre pagamentos de impostos no Brasil. No Brasil, os usuários podem registrar e lançar pagamentos de impostos junto com as informações fiscais relacionadas que será reportadas às autoridades fiscais.
author: sndray
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FBTaxAssessmentPayment_BR, FBTaxAssessmentPaymentOtherDebits_BR
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 270254
ms.assetid: 92223189-69a8-4a40-b867-ef9b4f14c23d
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4239e9d960ba9097f079af69ad18ba7b72e60c0c
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849362"
---
# <a name="tax-payments-in-brazil"></a>Pagamentos de impostos no Brasil

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre pagamentos de impostos no Brasil. No Brasil, os usuários podem registrar e lançar pagamentos de impostos junto com as informações fiscais relacionadas que será reportadas às autoridades fiscais.

<a name="overview"></a>Visão Geral
--------

Cada tipo de imposto no Brasil tem seu próprio processo, data de vencimento e informações adicionais de demonstrativo de imposto que é exigido pelas autoridades fiscais. O módulo **Livros fiscais** gera as instruções do Sistema Público de Escrituração Digital (SPED) obrigatórias para os impostos. O processo de pagamento de impostos é separado por tipos de imposto: ICMS, ICMS-ST, ICMS-DIF, IPI, ISS e PIS-COFINS.

-   ICMS, ICMS-ST e ICMS-DIF são impostos estaduais relacionados à movimentação de mercadorias.
-   ISS é um imposto municipal que é cobrado pela cidade.
-   IPI é um imposto de produção que é cobrado pelo governo federal. O governo federal também é responsável pelos impostos PIS e COFINS que são aplicados aos produtos.

A diferença entre o valor do imposto arrecadado em vendas de mercadorias e o valor do imposto ICMS pago em compras de mercadorias é calculada. Se o valor líquido for uma obrigação fiscal, uma entrada de diário de nota fiscal do fornecedor poderá ser criada. Depois, o valor do imposto devido à autoridade fiscal é pago. Para pagar impostos, uma apuração do imposto relacionado é criada. A apuração de imposto coleta informações das transações para o período correto, conforme exigido pelo imposto. Na página **Apuração de imposto**, você seleciona o imposto desejado. Na página **Pagamento de imposto**, você gera o pagamento do imposto relacionado. Dependendo do requisito de cobrança, há duas maneiras de criar o pagamento de impostos:

-   **Criar a partir da apuração** – Coletar e pagar imposto mensalmente, de acordo com as regras que são estabelecidas pela autoridade fiscal.
-   **Outros débitos** – coletar e pagar um determinado valor de imposto fora do processo normal quando a autoridade de imposto requer o pagamento.

![Criando pagamentos de impostos](./media/taxpaymentsbra.jpg) 


### <a name="overview"></a>Visão Geral

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tipo de Pagamento</td>
<td>Selecione uma das seguintes opções:
<ul>
<li><strong>Periódico</strong> – Cria um pagamento periódico mensal (regular). Todas as transações de impostos geradas de notas fiscais, e todos ajustes de transação (geral ou por nota fiscal) em que a configurações especiais do débito de ajuste não são marcadas, são resumidas para gerar pagamento periódico.</li>
<li><strong>Outros débitos</strong> – Faz um pagamento específico de ICMS fora do processo normal, porque o pagamento é solicitado por lei. Os exemplos incluem diferencial % do ICMS e Importação de mercadorias. Todas as transações de ajuste marcadas como <strong>Pagamento de outros débitos</strong> na configuração são resumidas para gerar um pagamento.</li>
</ul></td>
</tr>
<tr class="even">
<td>Data</td>
<td>A data do pagamento.</td>
</tr>
<tr class="odd">
<td>Código do ICMS a recolher</td>
<td>O código de pagamento do ICMS que as autoridades fiscais exigem. Este campo está disponível apenas para impostos ICMS, ICMS-ST e ICMS-DIF. As opções a seguir estão disponíveis:
<ul>
<li>000: ICMS a coletar</li>
<li>003: Antecipação de parte diferencial de alíquota</li>
<li>004: Antecipação de mercadorias de importação</li>
<li>005: Antecipação de impostos</li>
<li>006: Antecipação de ICMS adicional</li>
<li>090: Outras obrigações</li>
</ul></td>
</tr>
<tr class="even">
<td>Código da receita</td>
<td>A classificação de pagamento, conforme definido pelas autoridades fiscais estaduais. O programa deve oferecer o código de receita mais recente usado nas transações anteriores. Os códigos de receita variam, dependendo do tipo de pagamento. Se selecionar <strong>Outros débitos</strong> como o tipo de pagamento, o código de receita será inserido automaticamente as transações de ajuste, desde que as transações de ajuste possuam um código padrão de receita.</td>
</tr>
<tr class="odd">
<td>Data de Vencimento</td>
<td>A data de vencimento do pagamento. Se o campo <strong>Condições de pagamento</strong> estiver em branco, você deve inserir um valor neste campo. Caso contrário, o valor será definido como a data de vencimento que é gerada com base nas condições de pagamento. Depois que a integração do razão for ativada, a data de vencimento da transação do razão será inserida.</td>
</tr>
<tr class="even">
<td>Valor do imposto</td>
<td>O valor total do ICMS a pagar. O valor é calculado com base no tipo de pagamento.</td>
</tr>
<tr class="odd">
<td>Valor dos juros</td>
<td>O valor dos juros no caso de pagamentos atrasados.</td>
</tr>
<tr class="even">
<td>Valor da multa</td>
<td>O valor de multas, no caso de pagamentos atrasados.</td>
</tr>
<tr class="odd">
<td>Valor</td>
<td>A soma do valor do imposto, o valor dos juros e o valor da multa.</td>
</tr>
<tr class="even">
<td>Mês de referência</td>
<td>O mês de referência para este pagamento de ICMS, como <strong>012017</strong>.</td>
</tr>
<tr class="odd">
<td>Comprovante</td>
<td>O número do comprovante. Esse número é atribuído automaticamente quando o pagamento é lançado e a integração do razão é ativada.</td>
</tr>
</tbody>
</table>

#### <a name="general"></a>Geral

| Campo                     | descrição                                                                                                                                                                                             |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| descrição               | Insira uma descrição para o pagamento de imposto.                                                                                                                                                         |
| Autoridade fiscal                 | Selecione a autoridade fiscal na qual a apuração do imposto foi criada. A autoridade fiscal define um número de conta de fornecedor usada para transferir pagamentos de impostos ao fornecedor que faz o pagamento. |
| Condições de pagamento          | As condições de pagamento que são usadas para determinar a data de vencimento de um pagamento de imposto. As condições de pagamento que você selecionar aqui serão usadas para a fatura de fornecedor.                                     |
| Empresa                   | A entidade legal na qual a transação de pagamento de imposto será lançada, se a integração do razão for ativada.                                                                                                   |
| Revertido                  | Uma opção selecionada indica que o pagamento do imposto foi revertido.                                                                                                                                          |
| Número de rastreamento              | O número de rastreamento do pagamento revertido.                                                                                                                                                              |
| Número do processo referenciado | O número do processo referenciado.                                                                                                                                                                          |
| Agência                    | A agência a qual o processo referenciado pertence.                                                                                                                                                      |
| descrição               | A descrição do processo referenciado.                                                                                                                                                              |

#### <a name="tax-payments"></a>Pagamentos de imposto

Os pagamentos de impostos a seguir podem ser feitos na página **Pagamento de imposto** (**Livros fiscais** &gt; **Comum** &gt; **Período de escrituração** &gt; **Apuração**):

-   Apuração de imposto ICMS ou ICMS-ST
-   Pagamento de IPI
-   Pagamento de ICMS-DIF
-   Pagamento de ISS
-   Pagamento de PIS e COFINS - Um pagamento é feito para PIS e outro para COFINS. O tipo de regime de PIS e COFINS é mostrado na seção **Visão geral** do pagamento de imposto. Um pagamento pode ser relacionado ao regime cumulativo, regime não cumulativo ou ambos.

## <a name="reversing-tax-payments"></a>Revertendo pagamentos de impostos
Você pode reverter a transação para um pagamento de impostos que foi lançado, selecionando o pagamento de impostos e clicando em **Transação**. O processo de reversão de transação reverte a transação original e todas as transações relacionadas criadas quando a transação original foi lançada. A sequência numérica para as referências do número de rastreamento e reversão da transação nas sequências numéricas deve ser configurada para permitir o registro das reversões. Os pagamentos de impostos existentes podem ser revertidos nas seguintes condições:

-   A integração do razão com os Livros fiscais é ativada na página **Integração do razão**.
-   O passivo que é gerado quando o pagamento do imposto for lançado ainda está em aberto. Além disso, o saldo atual da conta do fornecedor da autoridade fiscal deve ser maior ou menor que 0,00

Quando um pagamento de imposto for revertido, o status da transação original é definido como **Revertido** e o número de sequência relacionado é inserido no campo **Número de rastreamento**.

## <a name="deleting-tax-payments"></a>Excluindo pagamentos de impostos
Você pode excluir pagamentos de impostos se o número do comprovante não estiver em branco, quando a transação de pagamento for lançada.

Para obter mais informações, consulte os seguintes tópicos:

 - [Configurar juros e multas para pagamentos de fornecedores](tasks/br-00065-1-set-up-interest-fines-vendor-payments.md)
 - [Calcular juros e multas sobre pagamentos de fornecedores](tasks/br-00065-2-calculate-interest-fines-vendor-payments.md)
 - [Configurar juros e multas em pagamentos de clientes](tasks/br-00066-1-set-up-interest-fines-customer-payments.md)
 - [Calcular juros e multas em pagamentos de clientes](tasks/br-00066-2-calculate-interest-fines-customer-payments.md)


