---
title: Resolução do SPED fiscal 13/2019 RJ
description: Este tópico explica como configurar e gerar arquivos de texto do SPED ECD.
author: v-oloski
manager: AnnBe
ms.date: 10/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7
ms.openlocfilehash: 3a3d3b9eb35d380ec26ae38f761ddf4688c96cf1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979620"
---
# <a name="sped-fiscal-resolution-132019-rj"></a>Resolução do SPED fiscal 13/2019 RJ

[!include [banner](../includes/banner.md)]

O estado do Rio de Janeiro (RJ) publicou a Resolução 13/2019. Esta resolução define como uma nota fiscal eletrônica (NF-e) deve ser emitida e como as informações devem ser registradas no EFD-ICMS/IPI quando as seguintes operações forem executadas (Decreto nº. 27.815/01):

- Isenção
- Redução da base de cálculo ou redução da taxa
- Crédito presumido
- Tributação na cobrança, tributação no recebimento ou tributação na saída
- Diferimento
- Inelegibilidade para estorno de crédito
- Reparo fiscal de crédito ou transferência de saldo acumulado de crédito

De acordo com a resolução, as exonerações são registradas como ajustes nas notas fiscais e nos livros fiscais e devem ser relatadas nos arquivos do Sistema Público de Escrituração Digital (SPED).

Os requisitos de resolução afetam a saída das linhas E111, E115, C195, C197 e 0460 no SPED Fiscal.

## <a name="sped-fiscal-records-by-operation"></a>Registros do SPED Fiscal por operação

### <a name="exemption-and-credit-reversal"></a>Isenção e estorno de crédito

Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do Imposto Sobre Operações Relativas à Circulação de Mercadorias e Serviços (ICMS) quando as seguintes condições são atendidas:

- Uma nota fiscal de saída emitida pelo estado do RJ tem um código de tributação de **30** ou **40**.
- Os códigos de benefícios da tabela 5.2 e da tabela 5.3, e também códigos de observação, são atribuídos ao item e ao estado relacionados da nota fiscal. Por exemplo, o código da tabela 5.2 é **RJ801137** e o código da tabela 5.3 é **RJ90980000**.

Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:

- O código de ajuste da tabela 5.2 gera um registro E115:

    \|E115\|RJ801137\|0\|\|

- O código de ajuste da tabela 5.3 gera um registro C197:

    \|C197\|RJ90980000\|RJ801137\|ItemId\|0,00\|0,00\|0,00\|0,88\|

    > [!NOTE]
    > Neste exemplo, o valor base é 3,5, o percentual de ICMS é 18 e a taxa do Fundo de Combate e Erradicação à Pobreza (FCP) é 0,02. Portanto, o valor 0,88 é calculado da seguinte maneira:
    >
    > 3,5 ÷ (1 – \[0,18 + 0,02\]) × (0,18 + 0,02)

- O código de observação atribuído ao item e estado relacionados da nota fiscal gera registros C195 e 0460:

    \|C195\|\<Observation code\>\|\<Observation code description\>\|

    \|0460\|\<Observation code\>\|\<Observation code description\>\|

Para registrar o estorno de crédito, crie um ajuste manual no diário Ajuste geral de imposto/benefício/incentivo e adicione o código da tabela 5.2 ao campo **Descrição**.

Veja um exemplo de uma transação de ajuste criada automaticamente no SPED Fiscal:

\|E111\|RJ18003\|RJ801137\|\<Adjustment amount\>\|

### <a name="reduction-of-tax-base-or-percentage"></a>Redução da base tributária ou percentual

Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do imposto ICMS quando as seguintes condições são atendidas:

- Uma nota fiscal de saída emitida pelo estado do RJ tem um código de tributação de **20** ou **70**.
- Os códigos de benefícios da tabela 5.2 e da tabela 5.3 são atribuídos ao item e ao estado relacionados da nota fiscal. Por exemplo, o código da tabela 5.2 é **RJ802164** e o código da tabela 5.3 é **RJ90980000**.

Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:

- O código de ajuste da tabela 5.2 gera um registro E115:

    \|E115\|RJ802164\|0\|\|

- O código de ajuste da tabela 5.3 gera um registro C197:

    \|C197\|RJ90980000\|RJ802164\|ItemId\|0,00\|0,00\|0,00\|0,20\|

    > [!NOTE]
    > Neste exemplo, o valor base é 3,5, o percentual de ICMS é 12 e a redução de percentual é 41,67. Portanto, o valor 0,20 é calculado da seguinte maneira:
    >
    > 3,5 × (1 – \[0,12 × (1 – 0,4167)\]) ÷ (1 – 0,12) – 3,5

- O código de observação atribuído ao item e estado relacionados da nota fiscal gera registros C195 e 0460:

    \|C195\|\<Observation code\>\|\<Observation code description\>\|

    \|0460\|\<Observation code\>\|\<Observation code description\>\|

### <a name="presumed-credit"></a>Crédito presumido

**Fora do escopo:** o sistema não pode preparar a porcentagem adicional necessária para os registros C197.

Para registrar o estorno de créditos, crie um ajuste manual no diário Ajuste geral de imposto/benefício/incentivo e adicione o código da tabela 5.2 ao campo **Descrição**.

Veja um exemplo de uma transação de ajuste criada automaticamente no SPED Fiscal:

\|E111\|RJ018003\|RJ805289\|\<Adjustment amount\>\|

### <a name="tax-on-total-sales-output-and-billing"></a>Imposto sobre vendas totais, produção e cobrança

Durante o processo de sincronização, um tipo de transação de ajuste é criado na apuração do imposto ICMS quando as seguintes condições são atendidas:

- Os documentos fiscais de saída emitidos pelo estado do RJ têm um código tributário de **00**.
- O código de benefício da tabela 5.2 é atribuído ao item e estado relacionados de uma nota fiscal. O código da tabela 5.3 não está atribuído. Por exemplo, o código da tabela 5.2 é **RJ822371**.

Veja um exemplo de uma transação de ajuste criada automaticamente no SPED Fiscal:

- O código de ajuste da tabela 5.2 gera um registro E115:

    \|E115\|RJ822371\|0\|\|

    > [!NOTE]
    > Como não há código da tabela 5.3, os registros C195, C197 e 0460 não são criados.

Para registrar o estorno de créditos e débitos, crie ajustes manuais no diário Ajuste geral de imposto/benefício/incentivo e adicione o código da tabela 5.2 ao campo **Descrição**.

Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:

\|E111\|RJ18003\|RJ822371\|\<Adjustment amount\>\|

\|E111\|RJ38003\|RJ822371\|\<Adjustment amount\>\|

\|E111\|RJ08006\|RJ822371\|\<Adjustment amount\>\|

### <a name="deferral"></a>Diferimento

Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do imposto ICMS quando as seguintes condições são atendidas:

- Os documentos fiscais de saída emitidos pelo estado do RJ têm um código tributário de **51**.
- Os códigos de benefícios da tabela 5.2 e da tabela 5.3 são atribuídos ao item e ao estado relacionados de uma nota fiscal. Por exemplo, o código da tabela 5.2 é **RJ818317** e o código da tabela 5.3 é **RJ90980001**.

Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:

- O código de ajuste da tabela 5.2 gera um registro E115:

    \|E115\|RJ818317\|0\|\|

- O código de ajuste da tabela 5.3 gera um registro C197:

    \|C197\|RJ90980001\|RJ818317\|ItemId\|0,00\|0,00\|0,00\|6.585,36\|

    > [!NOTE]
    > Neste exemplo, o valor base é 30.000,00. Portanto, o valor 6.585,36 é calculado da seguinte maneira:
    >
    > 30.000,00 ÷ (1 – 0,18) × 0,18

- O código de observação atribuído ao item e estado relacionados da nota fiscal gera registros C195 e 0460:

    \|C195\|\<Observation code\>\|\<Observation code description\>\|

    \|0460\|\<Observation code\>\|\<Observation code description\>\|

### <a name="enforceability-of-credit-reversal"></a>Aplicabilidade do estorno de crédito

Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do imposto ICMS quando as seguintes condições são atendidas:

- Uma nota fiscal de saída emitida pelo estado do RJ tem um código de tributação de **40**.
- Os códigos de benefícios da tabela 5.2 e da tabela 5.3 são atribuídos ao item e ao estado relacionados da nota fiscal. Por exemplo, o código da tabela 5.2 é **RJ801163** e o código da tabela 5.3 é **RJ90980000**.

Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:

- O código de ajuste da tabela 5.2 gera um registro E115:

    \|E115\|RJ801163\|0\|\|

- O código de ajuste da tabela 5.3 gera um registro C197:

    \|C197\|RJ90980000\|RJ801137\|ItemId\|0,00\|0,00\|0,00\|20\|

    > [!NOTE]
    > Neste exemplo, o valor base é 200, o percentual de ICMS é 18 e a taxa do FCP é 0,02. Portanto, o valor 20 é calculado da seguinte maneira:
    >
    > 200 ÷ (1 – \[0,18 + 0,02\]) × (0,18 + 0,02)

- O código de observação atribuído ao item e estado relacionados da nota fiscal gera registros C195 e 0460:

    \|C195\|\<Observation code\>\|\<Observation code description\>\|

    \|0460\|\<Observation code\>\|\<Observation code description\>\|

Para registrar o estorno de créditos, crie ajustes manuais no diário Ajuste geral de imposto/benefício/incentivo e adicione o código da tabela 5.2 ao campo **Descrição**.

Veja um exemplo de uma transação de ajuste criada automaticamente no SPED Fiscal:

\|E111\|RJ18003\|RJ801163\|\<Adjustment amount\>\|

### <a name="pass-on-or-transfer-a-tax-credit"></a>Transmitir ou transferir um crédito tributário

Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do imposto ICMS quando as seguintes condições são atendidas:

- Uma nota fiscal de transferência ou apropriação de imposto de saída emitida pelo estado do RJ tem um código de tributação de **90**.
- Os códigos de benefício das tabelas 5.2 e 5.3 são atribuídos ao item/Código Fiscal de Operações e de Prestações (CFOP) e ao estado da nota fiscal. Por exemplo, o código da tabela 5.2 é **RJ801163** e o código da tabela 5.3 é **RJ90980000**.

Para registrar a reversão de créditos, o sistema cria automaticamente ajustes no diário Ajuste geral de imposto/benefício/incentivo e relaciona a linha do diário à nota fiscal de transferência ou apropriação de imposto.

Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal para um remetente:

\|E115\|RJ821231\|0\|\|

\|C197\|RJ40080001\|RJ821231\|codigoitem\|0.00\|0.00\|\<Tax amount\>\|0.00\|

Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal para um destinatário:

\|E115\|RJ821231\|0\|\|

\|C197\|RJ10080002\|RJ821231\|codigoitem\|0.00\|0.00\|\<Tax amount\>\|0.00\|

## <a name="setup"></a>Configurar

### <a name="fiscal-books-parameters-per-state"></a>Parâmetros de livros fiscais por estado

Siga estas etapas para configurar os parâmetros dos livros fiscais para cada estado.

1. Vá para **Livros fiscais** \> **Configurar** \> **Parâmetros de livros fiscais por estado**.
2. Na Guia Rápida **SPED Fiscal**, na seção **Resolução 13/2019**, defina a opção **Ajuste de nota fiscal** como **Sim**. O sistema agora processará ajustes de notas de acordo com a Resolução 13/2019. Se você não definir esta opção como **Sim**, os requisitos de resolução não serão aplicados.
3. No campo **Nome**, digite o nome do diário Ajuste geral de imposto/benefício/incentivo. O sistema usa esse nome de diário quando um usuário deve realizar uma operação de transferência de ICMS para outro estabelecimento fiscal.

## <a name="benefit-code-per-item-or-state"></a>Código de benefício por item ou estado

1. Vá para **Imposto** \> **Configurar** \> **Imposto** \> **Código de benefício por item/estado**.
2. Configure **Código de ajuste 5.2**, **Código de ajuste 5.3** e **Código de observação**, conforme necessário.

Essas configurações ajudam a garantir que você obtenha um SPED Fiscal correto de acordo com a resolução.

Essas configurações são usadas para gerar automaticamente registros de ajuste de ICMS para uma linha de nota fiscal durante o lançamento e durante a operação de sincronização.

## <a name="tax-fiscal-document"></a>Nota fiscal de transferência ou apropriação de imposto

Se a opção **Ajuste de nota fiscal** é definida como **Yes** na página **Parâmetros de livros fiscais por estado**, os usuários podem selecionar apenas um código de imposto sobre vendas que tenha um valor fiscal 3 na linha da nota fiscal. O código de tributação, relacionado ao código do imposto sobre vendas, tem um valor fiscal de 3, sem crédito/débito. 

> [!NOTE]
> Para o lançamento correto, a nota fiscal e o código de imposto selecionado devem ter as seguintes configurações de cálculo:
>
> - **Origem:** percentual do valor líquido
> - **Base marginal:** valor líquido por linha
> - **Método de cálculo:** valor total

Quando você lança uma nota fiscal tributária na qual um código de imposto está anexado à linha, o sistema não cria uma transação de comprovante. Quando você executa a operação de sincronização, o sistema cria e lança um diário Ajuste geral de imposto/benefício/incentivo relacionado à nota fiscal de transferência ou apropriação de imposto lançada para transferência do ICMS para outro estabelecimento fiscal. (Para executar a operação de sincronização, vá para **Livros fiscais** \> **Comum** \> **Período de escrituração** e selecione **Sincronização**.)

O sistema preenche dados nas linhas do diário no perfil de lançamentos do código de ajuste 5.3. Ele preenche o valor da nota fiscal de transferência ou apropriação de imposto.

> [!NOTE]
> Antes de usar essa funcionalidade, configure o código de benefício por item/estado para transferência do ICMS, acessando **Imposto** \> **Configurar** \> **Imposto** \> **Código de benefício por item/estado**. De acordo com a resolução, os seguintes códigos de ajuste devem ser configurados para a transferência do ICMS:
>
> - **Para o remetente:** código de ajuste da tabela 5.2 = RJ821231 e código de ajuste da tabela 5.3 = RJ10080002
> - **Para o destinatário:** código de ajuste da tabela 5.2 = RJ821231 e código de ajuste da tabela 5.3 = RJ10080002
