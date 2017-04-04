---
title: "Visão geral da transferência de crédito SEPA"
description: "Este artigo fornece informações gerais sobre o 20022 transferências ISO de crédito, incluindo transferências de crédito (SEPA) da área de pagamento única em Euros e outros pagamentos eletrônicos para fornecedores. Uma transferência de crédito do SEPA é um tipo específico de pagamento em euro de uma empresa ou pessoa de outra empresa ou pessoa. O tópico também explica como configurar e aprovar um arquivo de pagamento transferência de crédito."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 848df5e3898f37284d7746c59bff8b38d35ac883
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-credit-transfer-overview"></a>Visão geral da transferência de crédito SEPA

Este artigo fornece informações gerais sobre o 20022 transferências ISO de crédito, incluindo transferências de crédito (SEPA) da área de pagamento única em Euros e outros pagamentos eletrônicos para fornecedores. Uma transferência de crédito do SEPA é um tipo específico de pagamento em euro de uma empresa ou pessoa de outra empresa ou pessoa. O tópico também explica como configurar e aprovar um arquivo de pagamento transferência de crédito.

## <a name="what-is-a-credit-transfer-message"></a>É que uma mensagem de transferência de crédito?
A mensagem de transferência de crédito é uma solicitação de um participante iniciando (empresa) envie os fundos de movimento da conta a um credor. Há um país/região implementações específicas e banco- específicas de mensagens da transferência de crédito. Algumas são usados em um país/região e, por padrão. são desenvolvimento Um padrão global não é conhecido ISO 20022 e de suas mensagens de iniciação, como transferência de crédito. A ilustração a seguir mostra as relações e a cobertura para mensagens entre a transferência de crédito. 
mensagens\[/caption\]a transferência de crédito do](./media/credit-transfer.jpg) tansfer de crédito do![ 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Com pagamentos ISO 20022 e do SEPA?
A Área Única de Pagamentos em Euros (SEPA) é configurada pela Comissão Europeia e dita que todos os pagamentos eletrônicos são considerados como domésticos, independentemente do país/região onde o indivíduo, a empresa ou a organização e o banco estão localizados. Não há diferença entre pagamentos nacionais e pagamentos internacionais. O SEPA inclui os 28 da União europeia (EU), além Islândia, Liechtenstein, Noruega Suíça, e Mônaco san Marino. A SEPA ajuda a formar um mercado único para transações de pagamento na Área Econômica Europeia (EEA). Por fim, espera-se que a SEPA reduza o número de formatos de pagamento com que bancos, empresas e indivíduos devem trabalhar. A Comissão Europeia estabeleceu a configuração legal para pagamentos de SEPA com a Diretiva de Serviços de Pagamento (PSD). O Conselho Europeu de Pagamentos (EPC) oferece suporte à SEPA com as seguintes atividades:

-   Define os padrões para pagamentos eletrônicos de SEPA usando o formato XML universal do esquema da mensagem da indústria financeira ISO 20022.
-   Ele estabelece regras e diretrizes sobre o processamento de pagamentos em euro.

O EPC, que consiste em bancos europeus, desenvolve as estruturas comerciais e técnicas para instrumentos de pagamento de SEPA. Três tipos de pagamentos de SEPA são usados:

-   Transferência de crédito
-   Débitos diretos
-   Cartões

## <a name="what-is-a-sepa-credit-transfer"></a>O que é uma transferência de crédito de SEPA?
Uma transferência de crédito de SEPA é um pagamento de uma empresa ou pessoa para outra empresa ou pessoa. Os pagamentos devem estar em euros, e devem incluir o número de conta bancária internacional (IBAN) e o código (BIC) do banco para ambas as partes. (BIC é conhecido como society for worldwide o código SWIFT \[\] partir inter-bank financial telecommunication). Adicionalmente, o custo de transação devem ser compartilhados entre os participantes. As transferências de crédito que ocorrem entre as partes devem usar arquivos XML que estejam de acordo com os padrões de processamento de pagamento ISO 20022 e o formato XML, conforme especificado pelo EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>Como uma transferência de crédito foi implementada?
O formato de pagamento de transferência de crédito de países europeus foi implementado usando (ER) e métodos para eletrônicos de funcionalidade de liquidação em dynamics 365 para as operações. Alguns formatos de transferência de crédito usados em outras regiões não usam a estrutura herdado de pagamento. Insira outros vários formatos, há a ISO doze 20022 formatos de arquivo de transferência de crédito disponíveis. Esses formatos de exportação estejam de acordo com o padrão ISO de XML do SEPA 20022. São usados para gerar transferências de pagamento não Euro para países/regiões onde são usados e euro pagamentos como especificado na versão 8.2 de regulamentação de esquema de transferência de crédito do SEPA o EPC liberar. Antes que você possa implementar transferências de crédito, você deve contatar seu banco para obter o software necessários para carregar eletrônicos arquivos de banco eletrônico. Você usará esse software para transferir os arquivos XML contendo ordens de pagamento ao banco.

## <a name="what-credit-transfer-formats-are-currently-supported-in-dynamics-365-for-operations"></a>Transferência de crédito que é atualmente formata suportada em dynamics 365 para operações?
Você sempre deve ir para biblioteca de ativo compartilhado em serviços (LCS) do Microsoft Dynamics lifecycle e exiba a lista a mais atualizado de arquivos disponíveis tenha um tipo de ativo ** configuração de GER **. A seção a seguir, “que eu tenho que configurar? ”, fornece um link para o tópico que explica como criar uma loja de LCS para revisar as configurações disponíveis e configurações de importação.

## <a name="what-do-i-have-to-set-up"></a>O que eu tenho que configurar?
-   Antes de criar arquivos de transferência de crédito, pelo menos uma configuração ativa de transferência de crédito deve ser importada nas configurações de ER. Para obter instruções, consulte [eletrônicas configurações de relatório de download serviços] do ciclo de vida (https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).
-   Ao configurar métodos de contas a pagar de pagamento, marque ** relatório eletrônico genérica ** a caixa de seleção, e selecione o formato adequado de transferência de crédito (por exemplo, ** transferência de crédito de 20022 (EM ISO) **) como uma configuração de formato.
-   Você também deve configurar informações da entidade legal e do banco em dynamics 365 para as operações.
-   Os números de conta bancária, IBANs e, ocasionalmente códigos SWIFT (BICs) ou outros itens são necessários para criar pagamentos de transferência válidos de crédito. Portanto, você deve configurar para a conta bancária de fornecedor e a conta bancária da organização que está emprestando a transferência.
-   Informações adicionais pode ser necessário, como números (VAT) de impostos sobre valor agregado dos participantes que são referidos na mensagem de transferência de crédito. Esta informação deve ser configurada para fornecedores e para a entidade legal quando solicitada.
-   Alguns métodos de contas a pagar do pagamento, a maioria ISO 20022 com métodos de pagamento, podem exigir de instalação adicional para ** conjuntos de código de formato de pagamento ** **, como tipo de serviço SLEV ** = ** **. Esses códigos são usados como marcar adicional para transações de pagamento durante o processamento de pagamento. Os valores padrão de código de pagamento, como ** finalidade de categoria **, ** portador de encargos **, ** instrumento local ** e ** ** nível de serviço podem ser definidos em dois locais. O primeiro está local ** cabeçalho de diário de pagamentos de contas a pagar ** e o segundo for ** métodos de contas a pagar para pagamentos **. Após o diário de pagamento da criação, valores de código de pagamento definidos no cabeçalho de diário de pagamento são transferidos para uma linha de diário, se definida, não os valores dos métodos de pagamento são usados.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Os parâmetros disponíveis para gerar pagamentos de transferência de crédito?
A lista de parâmetros específicos depende formato de transferência de crédito. A tabela mostra os parâmetros disponíveis quando você gera um arquivo de pagamento transferência de crédito 20022 ISO para Alemanha em um diário de pagamento de fornecedor. Usando as opções disponíveis ** executar o plano de fundo ** na guia, é possível executar geração de pagamento no modo de lote.

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
<li><strong>Strd</strong> – Selecione esta opção para usar o formato estruturada quando uma linha de pagamento é liquidado contra uma nota fiscal. Esta opção não estará disponível para o país/formatos específicos de exportação para a Alemanha, França, ou Países Baixos.</li>
<li><strong>Ustrd</strong> – Selecione esta opção para usar o formato não estruturado quando o pagamento for liquidado com diversas faturas. Os números de fatura para as faturas liquidadas são concatenados e usados como informação de remessa. Em conformidade com a ISO 20022 diretrizes, informações não estruturada de remessa são limitadas a 140 caracteres.</li>
</ul></td>
</tr>
<tr class="even">
<td>Número de faturas</td>
<td>Insira o número de notas fiscais do relatório é impresso.</td>
</tr>
<tr class="odd">
<td>Número de sequência</td>
<td>Insira um número de sequência para identificar o arquivo. O número de sequência é <strong>A observação atendendo</strong> exibido no relatório.</td>
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
O número de conta bancária internacional (IBAN) (BIC) e o código do banco são usados para identificar do mundo todo qualquer conta em muitos países/regiões. Esses incluem os 34 países/regiões do SEPA. Insira BIC ** no código SWIFT ** campo IBAN ** e IBAN ** no campo. Para a conta bancária do credor e a conta bancária do cliente, esses campos ficam localizadas ** identificação ** em FastTab ** ** conta bancária na guia ** contas bancárias ** de página. Uso de BIC para pagamentos do SEPA é imposta não.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Como transmitir um arquivo de pagamento para o banco?
Quando você gera pagamentos, o arquivo de pagamento é gerada, e você seja solicitado para poupar do navegador a qualquer local disponível. A próxima etapa é enviar o arquivo XML para o banco. Esse processo é diferente de banco para banco. Siga as instruções do banco para enviar arquivos ao banco para processamento.


