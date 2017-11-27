---
title: "Visão geral da transferência de crédito SEPA"
description: "Este artigo fornece informações gerais sobre as transferências de crédito ISO 20022, que incluem transferências de crédito da Área Única de Pagamentos em Euros (SEPA) e quaisquer outros pagamentos eletrônicos para fornecedores. Uma transferência de crédito de SEPA é um tipo específico de pagamento de uma empresa ou pessoa para outra empresa ou pessoa. O tópico também explica como configurar e transmitir um arquivo de pagamento de transferência de crédito."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1335d95c8bf02d5c571d37d78eca0ee7eae32bad
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="sepa-credit-transfer-overview"></a>Visão geral da transferência de crédito SEPA

[!include[banner](../includes/banner.md)]


Este artigo fornece informações gerais sobre as transferências de crédito ISO 20022, que incluem transferências de crédito da Área Única de Pagamentos em Euros (SEPA) e quaisquer outros pagamentos eletrônicos para fornecedores. Uma transferência de crédito de SEPA é um tipo específico de pagamento de uma empresa ou pessoa para outra empresa ou pessoa. O tópico também explica como configurar e transmitir um arquivo de pagamento de transferência de crédito.

## <a name="what-is-a-credit-transfer-message"></a>O que é uma mensagem de transferência de crédito?
A mensagem de transferência de crédito é uma solicitação que um participante iniciante (empresa) envia para mover fundos da conta a um credor. Há muitas implementações específicas de país/região e banco de mensagens de transferência de crédito. Algumas são utilizadas dentro de um país/região, e outras estão se tornando padrão. Um padrão global bem estabelecido é o ISO 20022 e suas mensagens de iniciação, como a transferência de crédito. A ilustração a seguir mostra as relações e a cobertura para as mensagens de transferência de crédito selecionadas. 
![Transferência de crédito](./media/credit-transfer.jpg) Mensagens de transferência de crédito 

## <a name="what-are-iso-20022-and-sepa-payments"></a>O que são pagamentos SEPA e ISO 20022?
A Área Única de Pagamentos em Euros (SEPA) é configurada pela Comissão Europeia e dita que todos os pagamentos eletrônicos são considerados como domésticos, independentemente do país/região onde o indivíduo, a empresa ou a organização e o banco estão localizados. Não há diferença entre pagamentos nacionais e internacionais. A SEPA inclui os 28 países membros da União Europeia (EU), além de Islândia, Liechtenstein, Noruega, Suíça, Mônaco e São Marinho. A SEPA ajuda a formar um mercado único para transações de pagamento na Área Econômica Europeia (EEA). Por fim, espera-se que a SEPA reduza o número de formatos de pagamento com que bancos, empresas e indivíduos devem trabalhar. A Comissão Europeia estabeleceu a configuração legal para pagamentos de SEPA com a Diretiva de Serviços de Pagamento (PSD). O Conselho Europeu de Pagamentos (EPC) oferece suporte à SEPA com as seguintes atividades:

-   Define os padrões para pagamentos eletrônicos de SEPA usando o formato XML universal do esquema da mensagem da indústria financeira ISO 20022.
-   Ele estabelece regras e diretrizes sobre o processamento de pagamentos em euro.

O EPC, que consiste em bancos europeus, desenvolve as estruturas comerciais e técnicas para instrumentos de pagamento de SEPA. Três tipos de pagamentos de SEPA são usados:

-   Transferência de crédito
-   Débitos diretos
-   Cartões

## <a name="what-is-a-sepa-credit-transfer"></a>O que é uma transferência de crédito de SEPA?
Uma transferência de crédito de SEPA é um pagamento de uma empresa ou pessoa para outra empresa ou pessoa. Os pagamentos devem estar em euros, e devem incluir o número de conta bancária internacional (IBAN) e o código (BIC) do banco para ambas as partes. (BIC também é conhecido como código Society for Worldwide Interbank Financial Telecommunication \[SWIFT\].) Além disso, os custos da transação devem ser compartilhados entre os participantes. As transferências de crédito que ocorrem entre as partes devem usar arquivos XML que estejam de acordo com os padrões de processamento de pagamento ISO 20022 e o formato XML, conforme especificado pelo EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>Como uma transferência de crédito é implementada?
O formato de pagamento de transferência de crédito para países europeus é implementado usando os recursos de relatórios eletrônicos (ER) e métodos de pagamento no Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Alguns formatos de transferência de crédito usados em outras regiões não usam a estrutura de pagamento herdada. Entre muitos outros formatos, existem dize formatos de arquivo de transferência de crédito ISO 20022 disponíveis. Esses formatos de exportação estão em conformidade com o padrão ISO 20022 XML do SEPA. São usados para gerar transferências de pagamento de uma moeda diferente do euro para países/regiões onde são usados e pagamentos em euro conforme especificado na versão 8.2 da Regulamentação do Esquema de Transferência de Crédito do SEPA que a EPC publica. Antes que você possa implementar a transferência de crédito, você deve entrar em contato com o banco para obter o software que é necessário para carregar arquivos eletrônicos da operação bancária. Você usará esse software para transferir os arquivos XML que contém ordens de pagamento para seu banco.

## <a name="what-credit-transfer-formats-are-currently-supported-in-finance-and-operations"></a>Quais formatos de transferência de crédito são suportados atualmente no Finanças e Operações?
Você sempre deve ir para a biblioteca de ativos compartilhados no Microsoft Dynamics Lifecycle Services (LCS) e exibir a lista mais atualizada de arquivos disponíveis que possuem um tipo de ativo de **Configuração GER**. A seção a seguir, "O que eu tenho que configurar?", fornece um link para o tópico que explica como criar uma loja de LCS para revisar as configurações disponíveis e as configurações de importação.

## <a name="what-do-i-have-to-set-up"></a>O que eu tenho que configurar?
-   Antes de criar arquivos de transferência de crédito, pelo menos uma configuração ativa da transferência de crédito deve ser importada para suas configurações eletrônicas. Para obter instruções, consulte [Baixar configurações do Relatório eletrônico no Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).
-   Quando você configurar os métodos de pagamento de Contas a pagar, marque a caixa de seleção **Relatório eletrônico genérico** e selecione o formato de transferência de crédito apropriado (por exemplo, **Transferência de crédito ISO 20022 (AT)**) como uma configuração de formato de exportação.
-   Você também deve configurar a entidade legal e as informações de conta bancária no Finanças e Operações.
-   Os números de conta bancária, IBANs e, ocasionalmente, códigos SWIFT (BICs) ou outras IDs são necessários para criar pagamentos de transferência de crédito válidos. Portanto, você deve configurá-los para a conta bancária de fornecedor e a conta bancária da organização que está solicitando a transferência.
-   Informações adicionais podem ser necessários, como números de imposto sobre valor agregado (IVA) dos participantes que são referidos na mensagem de transferência de crédito. Essas informações devem ser configuradas para fornecedores e para a entidade legal quando solicitadas.
-   Alguns métodos de pagamento de Contas a pagar, em maior parte os métodos de pagamento baseados em ISO 20022, podem exibir configuração adicional para **Conjuntos de código de formato de pagamento**, como **Tipo de serviço** = **SLEV**. Esses códigos são usados como marcação adicional para transações de pagamento durante o processamento de pagamento. Os valores padrão dos códigos de pagamento, como **Finalidade de categoria**, **Portador de encargos**, **Instrumento local** e **Nível de serviço** podem ser definidos em dois locais. O primeiro lugar é **Cabeçalho de diário de pagamentos de contas a pagar** e o segundo é **Métodos de contas a pagar para pagamentos**. Após a criação das linhas do diário de pagamento, os valores de código de pagamento definidos no cabeçalho do diário de pagamento são transferidos para uma linha de diário, se não estiver definido, os valores dos métodos de pagamento são usados.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Quais parâmetros estão disponíveis para gerar pagamentos de transferência de crédito?
A lista de parâmetros específicos depende do formato de transferência de crédito. A tabela a seguir mostra os parâmetros disponíveis ao gerar um arquivo de pagamento de transferência de crédito de ISO 20022 para a Alemanha em um diário de pagamentos de fornecedores. Usando as opções disponíveis na guia **Execução em plano de fundo**, é possível executar a geração de pagamento em modo de lotes.

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
<td>Reserva em lote</td>
<td>Marque esta caixa de seleção para incluir a etiqueta do registro de lotes no arquivo XML.</td>
</tr>
<tr class="even">
<td>Data de processamento</td>
<td>Insira a data em que o banco deve processar pagamentos.</td>
</tr>
<tr class="odd">
<td>Formato</td>
<td>Selecione o formato das informações de remessa, dependendo das necessidades do país/região ou banco:
<ul>
<li><strong>Strd</strong> – Selecione esta opção para usar o formato estruturado quando uma linha de pagamento é liquidada com uma fatura. Esta opção não estará disponível para os formatos de exportação específicos de país/região para França, Alemanha ou Holanda.</li>
<li><strong>Ustrd</strong> – Selecione esta opção para usar o formato não estruturado quando o pagamento for liquidado com diversas faturas. Os números de fatura para as faturas liquidadas são concatenados e usados como informação de remessa. Em conformidade com diretrizes de ISO 20022, as informações de remessa não estruturada são limitadas a 140 caracteres.</li>
</ul></td>
</tr>
<tr class="even">
<td>Número de faturas</td>
<td>Insira o número de faturas a partir do qual o relatório de <strong>Conselho de pagamento</strong> é impresso.</td>
</tr>
<tr class="odd">
<td>Número de sequência</td>
<td>Insira um número de sequência para identificar o arquivo. O número de sequência é exibido no relatório <strong>Nota de participação</strong>.</td>
</tr>
<tr class="even">
<td>Imprimir nota de participação</td>
<td>Marque esta caixa de seleção para imprimir o relatório <strong>Nota de participação</strong>.</td>
</tr>
<tr class="odd">
<td>Imprimir relatório de controle</td>
<td>Marque esta caixa de seleção para imprimir um relatório que contém as informações de pagamento.</td>
</tr>
<tr class="even">
<td>Imprimir carta de apresentação</td>
<td>Marque esta caixa de seleção para imprimir o relatório <strong>Aviso de pagamento</strong>.</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>O que são IBANs e BICs?
O Número de Conta Bancária Internacional (IBAN) e o Código Identificador Bancário (BIC) são usados para identificar todas as contas em muitos países/regiões ao redor do mundo. Esses incluem os 34 países/regiões do SEPA. Insira o BIC no campo **Código SWIFT** e o IBAN no campo **IBAN**. Para a conta bancária do credor e a conta bancária do cliente, esses campos ficam localizados na Guia Rápida **Identificação adicional** na guia **Conta bancária** da página **Contas bancárias**. O uso do BIC para pagamentos do SEPA não é imposto.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Como transmitir um arquivo de pagamento para o banco?
Ao gerar pagamentos, o arquivo de pagamento é gerado, e será solicitado que você salve-o de seu navegador web em qualquer lugar disponível. A próxima etapa é enviar o arquivo XML para o banco. Esse processo é diferente de banco para banco. Siga as instruções do banco para enviar arquivos ao banco para processamento.




