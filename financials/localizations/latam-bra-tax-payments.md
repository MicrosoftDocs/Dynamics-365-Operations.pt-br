---
title: Pagamentos de impostos em O Brasil
description: "Este tópico fornece informações sobre pagamentos de impostos em O Brasil. Em O Brasil, os usuários podem registrar e lançar pagamentos de imposto com informações de impostos relacionadas que deve ser informada para as autoridades fiscais."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FBTaxAssessmentPayment_BR, FBTaxAssessmentPaymentOtherDebits_BR
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 270254
ms.assetid: 92223189-69a8-4a40-b867-ef9b4f14c23d
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: fa0033d84c5ed36c4c2cfdee8232fe8946ca81df
ms.lasthandoff: 03/31/2017


---

# <a name="tax-payments-in-brazil"></a>Pagamentos de impostos em O Brasil

Este tópico fornece informações sobre pagamentos de impostos em O Brasil. Em O Brasil, os usuários podem registrar e lançar pagamentos de imposto com informações de impostos relacionadas que deve ser informada para as autoridades fiscais.

<a name="overview"></a>Visão Geral
--------

Cada tipo de imposto em O Brasil tem seu próprio processo, data de vencimento, e informações de extratos de imposto adicionais necessárias pelas autoridades de impostos. ** Livros fiscais ** o módulo gera as instruções de O Sistema Publico de Escrituração Digital (SPED) necessárias para impostos. O processo de liquidação de impostos é separado por tipos de imposto: ICMS, ICMS-ST, ICMS-DIF, IPI, ISS e, PIS-COFINS.

-   ICMS, ICMS-ST e, ICMS-DIF são fazenda relacionados para vender movimento.
-   O ISS é um imposto da cidade que são cobrados por cidade.
-   IPI é um imposto de produção que são cobrados pelo governo federal. O governo federal também é responsável pelos impostos PIS e COFINS aplicados a produtos.

A diferença entre o valor do imposto que é cobrado em vendas de bens e do valor de IMPOSTO ICMS que é pago em compras de mercadorias é calculada. Se o valor líquido é uma obrigação fiscal, uma entrada de diário de nota fiscal do fornecedor pode ser criada. O valor de imposto sobre vendas devido à autoridade fiscal é paga. Para pagar impostos, uma avaliação de imposto relacionado é criada. A avaliação de imposto coleta informações de transações para o tempo correto, dependendo requisitos de imposto. ** ** Avaliação de imposto na página, marque os impostos para trabalhar. ** Pagamento de impostos ** na página, você gera o pagamento de imposto relacionado. Dependendo do requisito de cobrança, há duas maneiras de criar o pagamento de impostos:

-   ** Criar previsto ** – coletam e pagos mensal de impostos sobre vendas, de acordo com as regras liquidadas pela autoridade fiscal.
-   ** Outros débitos ** – coletam e pagar um determinado valor de imposto no processo normal quando a autoridade de imposto sobre vendas requer o pagamento.

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
<li><strong>Recorrente</strong> – Crie um pagamento periódico mensal (normal). Todas as transações de impostos sobre vendas gerados de notas fiscais, e todos ajustes de transação (geral ou por documento fiscal) em que a configurações especiais do débito de ajuste não é marcada, estão resumidas para gerar pagamento periódico.</li>
<li><strong>Outros débitos</strong> – Faça um pagamento específico ICMS fora de processo normal, como o pagamento é solicitado por lei. Exemplos incluem diferencial % do ICMS e importam mercadorias. Todas as transações de ajuste marcadas como <strong>Outro pagamento de débito</strong> em configuração são resumidas para gerar um pagamento.</li>
</ul></td>
</tr>
<tr class="even">
<td>Data</td>
<td>A data de pagamento.</td>
</tr>
<tr class="odd">
<td>Código do ICMS a recolher</td>
<td>O ICMS de pagamento o código que as autoridades fiscais empresa. Este campo está disponível apenas para impostos ICMS, ICMS-ST e de, ICMS-DIF de. As opções a seguir estão disponíveis:
<ul>
<li>000: ICMS a cobrança</li>
<li>003: Antecipação de parte diferencial de alíquota</li>
<li>004: Antecipação de mercadorias de importação</li>
<li>005: Antecipa impostos</li>
<li>006: Antecipação ICMS adicional</li>
<li>090: Outras obrigações</li>
</ul></td>
</tr>
<tr class="even">
<td>Código de Receita</td>
<td>A classificação de pagamento, como definido pelas autoridades do imposto estadual. O programa deve oferecer o código do a receita que é usado nas transações anteriores. Os códigos de Receita varia, dependendo do tipo de pagamento. Se selecionar <strong>Outros débitos</strong> como o tipo de pagamento, o código de receita será inserido automaticamente as transações de ajuste, desde que as transações de ajuste possuem um código padrão de receita.</td>
</tr>
<tr class="odd">
<td>Data de Vencimento</td>
<td>A data de vencimento. Se <strong>Condições de pagamento</strong> o campo estiver em branco, você deve inserir um valor neste campo. Caso contrário, o valor é definido como a data de vencimento que é gerada com base em condições de pagamento. Depois que a integração do razão é ativada, a data de vencimento da transação do razão será inserida.</td>
</tr>
<tr class="even">
<td>Valor do imposto</td>
<td>A quantidade total de ICMS para liquidação. O valor é calculado com base no tipo de pagamento.</td>
</tr>
<tr class="odd">
<td>Valor dos juros</td>
<td>O valor dos juros no evento de tardios pagamentos.</td>
</tr>
<tr class="even">
<td>Valor da multa</td>
<td>O valor de multas o evento de tardios pagamentos.</td>
</tr>
<tr class="odd">
<td>Valor</td>
<td>A soma do valor do imposto, o valor dos juros, e o valor da multa.</td>
</tr>
<tr class="even">
<td>Mês de referência</td>
<td>Mês de referência para este pagamento de imposto ICMS, como <strong>012017</strong>.</td>
</tr>
<tr class="odd">
<td>Comprovante</td>
<td>O número do comprovante. Esse número é atribuído automaticamente quando o pagamento é lançado e a integração do razão for ativada.</td>
</tr>
</tbody>
</table>

#### <a name="general"></a>Geral

| Campo                     | descrição                                                                                                                                                                                             |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| descrição               | Insira uma descrição dos pagamentos de impostos.                                                                                                                                                         |
| Autoridade fiscal                 | Selecione a autoridade fiscal na avaliação de imposto for criada. A autoridade de impostos define um número de conta de fornecedor usada para transferir pagamentos de impostos ao fornecedor para o pagamento. |
| Condições de pagamento          | As condições de pagamento usadas para determinar a data de vencimento de um pagamento de impostos. As que você selecionar aqui será usado para a nota fiscal de fornecedor.                                     |
| Empresa                   | A entidade legal que a transação de pagamento de imposto será lançada se a integração do razão for ativada.                                                                                                   |
| Revertido                  | Uma opção marcada indica que o pagamento do imposto foi revertido.                                                                                                                                          |
| Número de rastreamento              | O número de rastreamento para a liquidação revertida.                                                                                                                                                              |
| Número do processo referenciado | O número de processo referenciada.                                                                                                                                                                          |
| Agência                    | Agência o processo referenciado pertence.                                                                                                                                                      |
| descrição               | A descrição de processo referenciada.                                                                                                                                                              |

#### <a name="tax-payments"></a> Pagamentos de imposto

Estes pagamentos de impostos podem ser efetuados ** pagamento de impostos ** na página (** livros fiscais ** &gt; ** comum ** &gt; ** período de registro ** &gt; ** avaliação **):

-   Apuração de imposto ICMS e ICMS-ST de
-   Pagamento de imposto IPI
-   Pagamento de impostos igual ICMS-DIF
-   Pagamento de imposto DE ISS
-   Pagamento de OS impostos PIS e COFINS – é feita uma liquidação para impostos PIS, e outro pagamento é feito para impostos COFINS. Regime o tipo de PIS e COFINS é mostrado ** ** visão geral na seção de pagamento de impostos. Pode ser um pagamento relacionado a regime cumulativo, não cumulativo regime a, ou a ambos os regimes.

## <a name="reversing-tax-payments"></a>Revertendo pagamentos de impostos
Você pode reverter a transação para um pagamento de impostos que será lançado se o pagamento de impostos e clicando ** ** transação. O processo de reversão de transação reverte a transação original e todas as transações relacionadas criadas quando a transação original foi lançada. A sequência numérica para as referências de número do estorno e de rastreamento da transação nas sequências numéricas devem ser configuradas para permitir o registro de estornos. Os pagamentos de impostos existentes podem ser revertidos nas seguintes condições:

-   Integração do razão com livros fiscais é ativada ** integração do razão ** na página.
-   Passivo que é gerada quando o pagamento do imposto foi lançado ainda está em abrir. Adicionalmente, o saldo da conta de fornecedor da autoridade de imposto deve ser maior ou menor de 0.00

Quando um pagamento de impostos é estornada, o status da transação original está definido reverso ** **, e o número de sequência é relacionado inserido ** número de rastreamento ** o campo.

## <a name="deleting-tax-payments"></a>Excluindo pagamentos de impostos
Você pode excluir pagamentos de impostos se o número de comprovante não estiver em branco quando a transação de liquidação foi lançada.


