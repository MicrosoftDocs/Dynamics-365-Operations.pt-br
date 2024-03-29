---
title: Notas fiscais de transferência ou apropriação de imposto ICMS para o Brasil
description: Este artigo explica o conceito de notas fiscais de transferência ou apropriação de imposto e descreve os requisitos para gerá-las.
author: AdamTrukawka
ms.date: 08/08/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 269524
ms.search.form: TaxFiscalDocument_BR, TaxFiscalDocumentCancel_BR, TaxFiscalDocumentListPage_BR, TaxFiscalDocumentPost_BR
ms.openlocfilehash: 369f71e46367046f4da972ed1dec478a3973b75a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283017"
---
# <a name="icms-tax-fiscal-documents-for-brazil"></a>Notas fiscais de transferência ou apropriação de imposto ICMS para o Brasil

[!include [banner](../includes/banner.md)]

Este artigo explica o conceito de notas fiscais de transferência ou apropriação de imposto e descreve os requisitos para gerá-las.

No Brasil, alguns tipos de notas fiscais não têm efeito em fornecedores, clientes ou saldos de estoque. Esses documentos fiscais permitem que entidades legais insiram ajustes fiscais, transfiram entre outras subsidiárias e recuperem impostos em prestações durante um período. Para registrar essas operações na entidade legal, notas fiscais específicas devem ser geradas que afetam o relatório de Contabilidade e os livros fiscais.

## <a name="imposto-sobre-circulao-de-mercadorias-e-servios-icms-tax-transfers-between-subsidiaries"></a>Transferências do Imposto sobre Circulação de Mercadorias e Serviços (ICMS) entre subsidiárias
Esse tipo de imposto é considerado um imposto recuperável. As regulamentações de imposto de renda corporativo não permitem que o imposto ICMS seja deduzido. Os créditos acumulados do ICMS não podem ser usados para reduzir o valor tributável para avaliação de impostos sobre rendimento corporativo (IRPJ e CSSL). Os modos de acumular créditos de ICMS incluem:

-   Exportação – isenção de ICMS
-   Diferimentos
-   Taxa reduzida
-   Créditos presumidos

Há várias opções para gerenciar como os créditos acumulados de ICMS são usados quando o saldo devido é maior do que o débito/crédito acumulado. O crédito de imposto ICMS acumulado pode ser transferido nestas situações:

-   Transferir o crédito de ICMS para outras subsidiárias que têm um maior volume de transações onde o ICMS é devido. O crédito de imposto só pode ser transferido para subsidiárias localizadas no mesmo estado.
-   Transferir o crédito de ICMS para pagar contas de fornecedor em operações de compra por material bruto e secundário, pacotes de equipamento e, equipamento industrial.
-   Transferir o crédito de ICMS para outras subsidiárias. Até 30% de cada operação de ativo fixo que é destinada para ativos fixos permanentes pode ser transferido.
-   Pagamento de aquisição de chassi do caminhão com novo motor, ou combustível, feito pelo estabelecimento de transporte rodoviário.
-   Transferir o crédito de ICMS de uma empresa que fabrique álcool etílico a empresa que cooperativa centraliza vendas. Até 30 dos impostos cobrados na remessa desse produto podem ser transferidos.
-   Transferir o crédito de ICMS para o estabelecimento industrial de óleo bruto.

Nessas situações, o valor que uma empresa pode obter do ICMS acumulado depende de regras específicas estabelecidas pelo governo. O valor não é aplicável sempre a 100% do valor de ICMS acumulado. Os créditos de ICMS são transferidos pela emissão de uma nota fiscal que é conhecida como nota fiscal de transferência ou apropriação de imposto. Esse documento deve incluir informações específicas que refletem a operação. O contribuinte também pode emitir uma nota fiscal eletrônica (NF-e) para transferir o crédito de ICMS acumulado para outra subsidiária.

## <a name="recovering-icms-tax-in-installments"></a>Recuperando ICMS em parcelas
De acordo com a lei brasileira nº 102/2000, a partir de 1º de janeiro de 2001, os créditos de ICMS decorrentes da compra de ativos fixos que são usados especificamente na atividade relacionada à tributação do ICMS pode ser apropriados em 1/48 por mês. O crédito de ICMS não pode ser totalmente recuperado quando o usuário registra a compra. Em vez disso, o crédito de ICMS deve ser recuperado em 48 parcelas ao longo do tempo. Veja a seguir um exemplo:

-   Valor de aquisição de ativo: R$ 100.000, 00
-   Valor do ICMS: R$ 12.000,00
-   Cálculo de IVA recuperável com a finalidade de distribuição em contas de ativos atuais e de contas a receber a long prazo:
    -   Ativo atual:
        1.  R$ 12.000, 00 ÷ 48 meses = R$ 250,00
        2.  R$ 250,00 × 12 meses (1 ano) = R$ 3.000, 00
    -   Ativo a longo prazo:
        1.  R$ 12.000, 00 ÷ 48 meses = R$ 250,00
        2.  R$ 250,00 × 36 meses (1 ano) = R$ 9.000, 00

No Dynamics 365 Finance, as entradas são as seguintes:

**Compra de Ativo Fixo** **Microsoft Dynamics 365 Finance: Fatura de Compra do Ativo de Recebimento**

**Ajuste de ICMS do ano** **Finance: Comprovante de diário manual** **(R$ 12.000,00 / 48 parcelas) \* 12 (meses)**

ICMS recuperável **longo prazo** (conta diferida)

*R$ 12.000,00 D*

ICMS recuperável **curto prazo** (conta diferida)

R$ 3.000,00 D

Ativo Fixo

R$ 88.000, 00 C

ICMS recuperável, longo prazo (conta diferida)

*R$ 3.000,00 C*

**Saldo de Ativo de longo prazo** (conta diferida): R$ 9.000,00

**Ajuste de ICMS do mês** **finanças e operações: emissão de uma Nota fiscal de entrada**

Conta de ICMS recuperável

R$ 250,00 D

ICMS recuperável curto prazo (conta diferida)

*R$ 250,00 C*

Na página **Todas as notas fiscais de transferência ou apropriação de imposto**, você pode fazer o seguinte:

-   Crie e lance uma nota fiscal de transferência ou apropriação de imposto ICMS para transferir o valor do imposto ICMS para um cliente ou fornecedor.
-   Crie e lance uma nota fiscal de transferência ou apropriação de imposto ICMS para restituir o valor do imposto ICMS em parcelas para a compra de ativos fixos por uma entidade legal.
-   Adicionar texto da nota fiscal a uma nota fiscal de transferência ou apropriação de imposto ICMS.
-   Exibir as transações de comprovante que estão relacionadas a uma nota fiscal de transferência ou apropriação de imposto ICMS na página **Transações de comprovante**.
-   Cancelar uma nota fiscal de transferência ou apropriação de imposto ICMS lançada e gerar uma transação de comprovante cancelada. O valor da fatura da transação do comprovante cancelado é igual ao valor da fatura original, mas o valor da fatura é negativo.
-   Lançar a fatura cancelada e exibir as transações de comprovante originais e canceladas na página **Transações de comprovante**.
-   Imprimir uma nota fiscal de transferência ou apropriação de imposto ICMS da Contabilidade. O texto do rodapé na página **Configuração de gerenciamento de impressão** não é impresso nas notas fiscais de transferência ou apropriação de imposto ICMS.

Quando uma nova nota fiscal de transferência ou apropriação de imposto é criada, as seguintes opções ficam disponíveis:

-   Transferência de imposto ICMS
-   Parcela de ICMS para utilizar o crédito de ativos fixos (CIAP)

## <a name="prerequisites"></a>Pré-requisitos
Os seguintes pré-requisitos devem ser configurados antes de você criar e lançar notas fiscais de transferência ou apropriação de imposto. Os parâmetros determinam como os dados serão exibidos em notas fiscais, e todos são necessários. Parâmetros ausentes podem causar inconsistências ou validações incorretas durante o processo de lançamento.

-   **Parâmetros brasileiros:** Defina o item e os códigos de imposto **PIS** e **COFINS** que são usados para esses tipos de documentos fiscais.
-   **Grupos de lançamento contábil na Contabilidade**: Define a conta contábil **Imposto a receber a curto prazo**.

## <a name="example"></a>Exemplo
**Notas fiscais de saída**

-   Notas fiscais de saída para transferência de crédito de ICMS de outras entidades legais, ou uma subsidiária da mesma empresa, destinadas para a compensação do saldo de débito de ICMS (CFOP: 5.601 e 5.602)

**Notas fiscais de entrada**

-   Notas fiscais de entrada para transferência de crédito de ICMS de outras entidades legais ou subsidiárias da mesma empresa destinadas para a compensação do saldo de débito de ICMS (CFOP: 1.601 e 1.602)
-   Notas fiscais de entrada para utilizar 1/48 de crédito de ICMS (CFOP: 1.604) (CIAP)


Para obter mais informações, consulte os seguintes tópicos:

[Configurar códigos de ajuste para o imposto ICMS (Brasil)](tasks/br-10001-1-set-up-adjustment-codes-icms-tax.md)

[Configurar códigos de ajuste para o imposto ICMS em notas fiscais (Brasil)](tasks/br-10001-2-set-up-adjustment-codes-icms-taxes-fiscal-documents.md)

[Inserir e lançar transações de ajuste de imposto (Brasil)](tasks/br-10001-3-enter-post-tax-adjustment-transactions.md)

[Criar uma apuração de imposto – ICMS (Brasil)](tasks/br-10001-4-create-tax-assessment-icms.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
