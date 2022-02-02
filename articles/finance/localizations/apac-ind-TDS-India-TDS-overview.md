---
title: Visão geral do Imposto Deduzido na Origem (TDS) da Índia
description: Este tópico fornece informações detalhadas sobre o Imposto Deduzido na Origem (TDS) da Índia. A documentação do TDS aborda a funcionalidade desse recurso.
author: kailiang
ms.date: 03/19/2021
ms.topic: overview
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d33faaff8be4821005b8772875eb91f0afe26cb0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983894"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a>Visão geral do Imposto Deduzido na Origem (TDS) da Índia

[!include [banner](../includes/banner.md)]

Este tópico fornece informações detalhadas sobre o Imposto Deduzido na Origem (TDS) da Índia.

A documentação do TDS aborda a funcionalidade desse recurso. Também explica como fazer a configuração básica do TDS, calcular o TDS nas transações, concluir o processo de liquidação do TDS, registrar os números dos certificados do TDS e gerar consultas do TDS, declarações do TDS e certificados do TDS. A documentação inclui os seguintes tópicos:

- [Configuração básica do TDS](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [Designer de fórmulas e funcionalidade de limite usada para cálculo do TDS](apac-ind-TDS-Formula-designer.md)
- [Cálculo do TDS em faturas, pagamentos, notas promissórias e transações entre empresas](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [Processo de liquidação de TDS periódico e liquidação de valores de TDS para fornecedores de autoridade TDS](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [Registro e atualização de números e datas de certificados de TDS](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a>Introdução ao TDS

De acordo com a Lei do Imposto de Renda de 1961, o imposto de renda é deduzido na fonte pelo destinatário do serviço no momento do pagamento antecipado ou da contabilidade do crédito, o que ocorrer primeiro. Quem efetua o pagamento deve deduzir o valor do imposto e pagar somente o saldo líquido ao prestador do serviço. O TDS é aplicado em serviços que o governo especifica e o imposto é deduzido usando as taxas que o governo especifica para um período. A taxa de dedução é baseada no status da entidade que recebe o pagamento ou fornece o serviço. Os status incluem **Individual**, **Família indivisa hindu** (**HUF**), **Empresa**, **Firma**, **Associação de pessoas** (**AOP**), **Corpo de indivíduos** (**BOI**) e **Autoridade local**.

As seções a seguir listam os serviços aos quais o TDS é aplicado, conforme especificado pelo Governo da Índia.

**Residentes**

- Renda de salários (na seção 192)
- Renda de juros sobre valores (na seção 193)
- Renda por dividendos (na seção 194)
- Renda por juros (na seção 194A)
- Renda por loterias ou jogos (na seção 194B)
- Ganhos com corridas de cavalos etc. (na seção 194BB)
- Prestadores de serviço e subcontratados (na seção 194C)
- Comissão de seguro (na seção 194D)
- Renda por depósito no esquema de poupança nacional (na seção 194EE)
- Renda por fundo mútuo ou UTI (na seção 194F)
- Comissão, remuneração, prêmio etc., à venda ou loteria (na seção 194G)
- Pagamento de comissão ou corretora (na seção 194H)
- Aluguel (na seção 194I)
- Serviço profissional (na seção 194J)
- Renda por unidades (na seção 194K)
- Pagamento de compensação na aquisição de certos bens imóveis (na seção 194LA)

**Não residentes**

- Pagamentos a esportistas não residentes ou associações esportivas (na secção 194E)
- Outras somas (na seção 195)
- Renda em relação a unidades de não residentes (na seção 196A)

    - Renda por títulos em moeda estrangeira ou ações da empresa indiana (na seção 196C)
    - Receitas de investidores institucionais estrangeiros de valores (na seção 196D)
    - Salário e todas as outras rendas positivas em qualquer categoria de renda (na seção 192)
    - Juros sobre valores (na seção 193)
    - Juros que não sejam juros sobre valores (na seção 194A)
    - Pagamentos a prestadores de serviço e subcontratados (na seção 194C)
    - Ganhos com loteria ou palavras cruzadas (na seção 194B)
    - Ganhos com corridas de cavalos (na seção 194BB)
    - Comissão de seguros cobrindo todos os pagamentos para aquisição de negócios de seguros (na seção 194D)
    - Quaisquer juros, exceto juros sobre valores a pagar a não residentes que não sejam uma empresa ou a uma empresa estrangeira (na seção 195)
    - Pagamento a esportista não residente, incluindo atleta ou associação ou instituição esportiva. No caso de esportista não residente, pagamentos relativos a anúncios, bem como artigos sobre qualquer jogo/esporte na Índia em jornais, revistas etc. está incluído (seção 194E)
    - Pagamento em relação a depósitos no NSS \[esquema de poupança nacional\] (seção 194EE)
    - Pagamento por conta de recompra de unidades por fundo mútuo ou UTI (seção 194F)
    - Pagamento de comissão ou corretora (seção 194H)
    - Pagamento de aluguel (seção 194I)
    - Pagamento de taxas por serviços profissionais ou técnicos (seção 194J)
    - Comissão para Stockiest, distribuidores, compradores e vendedores de bilhetes de loteria, incluindo remuneração ou prêmio em tais bilhetes (seção 194G)
    - Renda por unidades compradas em moeda estrangeira ou ganho de capital de longo prazo decorrente da transferência de tais unidades compradas em moeda estrangeira (seção 196B)
    - Pagamento de qualquer renda a não residentes a respeito de juros ou dividendos sobre valores e ações (seção 196C)

O TDS é calculado sobre compras, vendas, devoluções de vendas, notas de crédito, aquisições de ativos fixos, pré-pagamentos, pagamentos antecipados, notas promissórias, imposto de obra e transações entre empresas.

> [!NOTE]
> No cenário fiscal atual da Índia, o TDS não é calculado sobre as transações de vendas. Contudo, o sistema inclui uma provisão para calcular o TDS recuperável em transações de vendas, especialmente para transações entre empresas.

O cálculo do TDS sempre considera o limite e o limite de exceção que são definidos para o componente TDS.

O processo de liquidação de TDS periódico deve ser executado e os pagamentos de TDS devem ser liquidados para fornecedores de autoridade TDS.

Os números e datas dos certificados de TDS recebidos de fornecedores ou clientes podem ser registrados e atualizados. Além disso, as declarações trimestrais do Formulário 26Q e do Formulário 27Q e o certificado do Formulário 16A para TDS podem ser gerados no Finance.

## <a name="setting-up-and-working-with-tds"></a>Configuração e trabalho com TDS

Aqui está uma visão geral do processo para configurar e trabalhar com o TDS:

1. **Configuração de TDS:**

    - Configuração de parâmetros:

        - Em Parâmetros da contabilidade, ative os parâmetros relacionados ao TDS.
        - Em Parâmetros da contabilidade, configure a sequência numérica para pagamentos de impostos retidos na fonte.
        - Configure parâmetros em Contas a pagar e em Contas a receber.

    - Configuração básica:

        - Configure os números de registro do TDS para uma empresa, clientes e fornecedores.
        - Configure grupos de componentes de TDS.
        - Configure os componentes do TDS, anexe grupos de componentes do TDS a eles e defina o limite e o limite de exceção para eles.
        - Configure autoridades TDS.
        - Configure os períodos de liquidação do TDS.
        - Configure os códigos de imposto do TDS e anexe os componentes do TDS a eles.
        - Configure grupos de impostos TDS e anexe códigos de impostos TDS a eles.
        - No designer de fórmulas, defina uma fórmula para calcular o TDS para um grupo de TDS.
        - Registre os números dos certificados de concessão de TDS.

    - Contas contábeis e configuração da empresa:

        - Configure contas contábeis a pagar e a receber de TDS.
        - Configure um número de conta de cobrança e dedução de imposto (TAN) e uma categoria de tipo de dedutor para a empresa.

    - Outra configuração:

        - Configure uma programação de pagamento que inclua a alocação de TDS.
        - Configure um tipo de taxa de pagamento para pagamentos à autoridade TDS.
        - Configure informações sobre grupos TDS, números de contas permanentes (PANs) e TANs para fornecedores e clientes.

2. **Cálculo do TDS nas transações:**

    - Faturas e pagamentos
    - Notas Promissórias
    - Pagamentos antecipados
    - Pagamentos Antecipados

3. **Liquidação de TDS:**

    - Processo de liquidação de TDS periódico
    - Liquidação de pagamentos de TDS para fornecedores da autoridade TDS e criação de challan TDS

4. **Consultas, declarações e certificado de TDS:**

    - Registre e atualize os números e datas dos certificados de TDS.
    - Gere uma consulta de TDS e uma consulta de TDS publicada.
    - Gere o Formulário 27A, o Formulário 26Q e o Formulário 27Q TDS e extratos trimestrais do e-TDS.
    - Gere um certificado Formulário 16A TDS.
