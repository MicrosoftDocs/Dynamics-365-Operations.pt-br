---
title: Definir contribuições SPED EFD
description: Este tópico explica como configurar parâmetros e gerar o SPED EFD — demonstrativo de contribuições para o Brasil.
author: sndray
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 89c389c522a0ccc6889cc43cbdc669f136a4f53704d96e06bdec0177916471b3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721703"
---
# <a name="set-sped-efd-contributions"></a>Definir contribuições SPED EFD

[!include [banner](../includes/banner.md)]

O SPED EFD — declaração de contribuições é gerado no módulo **Livros fiscais**. Ele reúne informações sobre o imposto de contribuição social sobre a receita bruta do PIS (programa de integração social) e a contribuição para financiamento de seguridade social (COFINS).

Siga estas etapas para configurar os requisitos para os arquivos de texto do SPED EFD – Contribuições.

1. Selecione **Livros fiscais** \> **Configuração** \> **Parâmetros das extensões de obrigações fiscais**.
2. Selecione **EFD - Contribuições** e, em seguida, na Guia Rápida **Parâmetros de configuração**, selecione **Abrir**.

    A página **Parâmetros da EFD - Contribuições** será exibida, na qual você pode inserir as informações necessárias dos arquivos de texto do SPED EFD – Contribuições.

3. No campo **Tipo de atividade**, selecione o tipo de atividade:

    - Industrial ou equivalente
    - Prestador de serviços
    - Retail
    - Atividade financeira
    - Atividade imobiliária
    - Outros(as)

4. Defina a opção **Empresa grande** como **Sim** para identificar o tamanho da empresa. Esta opção é usada nas instruções SPED Reinf.
5. No campo **Versão de layout**, selecione a versão do layout SPED EFD. 
6. No campo **Tipo de entidade legal**, selecione o tipo de entidade legal.
7. No campo **Tipo de empresa**, selecione o tipo de empresa:

    - PJ em geral
    - PJ componente do sistema financeiro
    - Sociedades seguradoras ou de capitalização ou fundos de pensão complementares abertos

8. No campo **Natureza legal** , insira o código da natureza legal, de acordo com a tabela do SPED EFD.
9. Definir a opção **CPRB** como **Sim** para habilitar a apuração do imposto CPRB. Esta opção é usada nas instruções SPED Reinf.
10. No campo **Código de classificação de imposto** , selecione o código de classificação de imposto. Este campo é usado nas instruções SPED Reinf.
11. Defina a opção **Acordo internacional para a isenção de multas** como **Sim**.
12. No campo **Regime de apuração**, selecione o esquema de apuração usado para SPED EFD – Contribuições:

    - **Não cumulativo** – Calcula as apurações com base em faturamentos ou débitos e compras e deduções e créditos.
    - **Cumulativo** – Calcula as apurações com base em faturamentos que não tenham deduções ou créditos.
    - **Ambos** – Calcula as apurações com base em regimes **Não cumulativo** e **Cumulativo** .

13. No campo , **Critério de escrituração e apuração**, selecione os critérios a serem usados para registrar o crédito fiscal.
14. No campo **Tipo de contribuição apurada** , selecione o tipo de contribuição apurada.
15. No campo **Método de apropriação de créditos**, selecione o método de alocação de crédito:

    - Direto
    - Distribuição proporcional

    Este campo está disponível somente se você selecionou **Não cumulativo** ou **Ambos** no campo **Regime de apuração** .

16. No campo **Opções de NFe e ECF**, selecione a opção de relatório para transações de NFe:

    - **Consolidado** – Consolida todas as transações de NF-e em um registro no relatório fiscal C18X.
    - **Detalhado** Lista todas as transações individuais no relatório fiscal.

17. Na Guia Rápida **Estabelecimento fiscal** , insira as informações necessárias de SPED ECD.
18. Na guia **Regra para código de tributação**, selecione o código de tributação e o valor fiscal para evitar que os registros C100 e D100 sejam gerados.

## <a name="special-requirements-for-layout-version-006-and-later"></a>Requisitos especiais para a versão de layout 006 e posterior

### <a name="record-0900"></a>Registro 0900

O registro 0900 nos arquivos de texto SPED EFD - contribuições é gerado automaticamente para fornecer detalhes sobre a composição de receita para o período de reserva especificado. A geração deste registro é obrigatória quando o arquivo do SPED EFD - contribuições original é transmitido após o período de entrega regular (isto é, após o décimo dia útil do segundo mês do período de reserva).

O registro gerado está disponível no layout versão 006 e posterior. Selecione esta opção quando o arquivo SPED EFD - Contribuições for executado.

### <a name="m410-pis-and-m810-cofins"></a>M410 (PIS) e M810 (COFINS)

Os registros M410 e M810 nos arquivos de texto do SPED EFD - contribuições são gerados automaticamente para transações de receita nas quais um valor fiscal é definido como **2:Isento** ou **3:sem débito/crédito**.

A implementação do layout versão 006 altera a forma como o campo 02 (**NAT\_REC**) é determinado. Nessa versão de layout, será usada uma configuração adicional. Nas versões de layout anteriores, foram usados valores fixos específicos.

## <a name="prerequisites"></a>Pré-requisitos

Antes de gerar as avaliações de imposto PIS e COFINS e habilitar a geração de registros M410 e M810 que têm a determinação da fonte de receita correta, Acesse **Livros fiscais** \> **Configuração** \> **Tabelas de PIS e COFINS** \> **Código de fontes de receita** e selecione os seguintes parâmetros.

<table>
<thead>
<tr>
<th>Campo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr>
<td>Tipo da fonte de receita</td>
<td>Selecione o tipo de fonte de receita, de acordo com o relacionamento incluído nas tabelas que fornecem detalhes sobre a natureza da receita por situação fiscal (por exemplo, tabelas 4.3.10 e 4.3.11). Essas tabelas são publicadas pela autoridade fiscal.</td>
</tr>
<tr>
<td>Código da fonte de receita</td>
<td>Insira o código para a fonte de receita.</td>
</tr>
<tr>
<td>Descrição</td>
<td>Inserir uma descrição do código da fonte de receita.</td>
</tr>
<tr>
<td>Data inicial e final de validade</td>
<td>Insira as datas em que a fonte de receita é aplicável.</td>
</tr>
</tbody>
</table>

Acesse **Livros fiscais** \> **Configuração** \> **Tabelas de PIS e COFINS** \> **Fonte de receita por item** para configurar a determinação da fonte de receita.

<table>
<thead>
<tr>
<th>Campo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr>
<td>Código do item</td>
<td>Especifique se a determinação da fonte de receita se aplica a um código de item, um grupo de itens ou todos os itens:
<ul>
<li><strong>Tabela</strong> – a receita de origem se aplica a um único código de item. Se você selecionar esta opção, selecione o código de item, no campo <strong>Relação de item</strong>.</li>
<li><strong>Grupo</strong> – a receita de origem se aplica a um grupo de itens. Se você selecionar esta opção, selecione o grupo de itens, no campo <strong>Relação de item</strong>.</li>
<li><strong>Tudo</strong> – a receita de origem se aplica a todos os itens. Se você selecionar essa opção, deixe o campo <strong>Relação de item</strong> em branco.</li>
</ul>
</td>
</tr>
<tr>
<td>Relação de item</td>
<td>Se você selecionou <strong>Tabela</strong> no campo <strong>Código de item</strong>, selecione o código de item associado à fonte de receita. Se você selecionou <strong>Grupo</strong>, escolha um grupo de itens. Se selecionou <strong>Todos</strong>, deixe este campo em branco.</td>
</tr>
</tbody>
</table>

## <a name="generate-a-sped-efd---contributions-text-file"></a>Gerar um arquivo de texto SPED EFD - Contribuições

1. Acesse **Livros fiscais** \> **Comum** \> **Período de reserva**.
2. Selecione o período de reserva relacionado e selecione **Obrigações fiscais** \> **Contribuições EFD** \> **Executar**.
3. No campo **Tipo de situação**, selecione o tipo de situação.
4. No campo **Tipo de arquivo**, selecione **Original** ou **Substituto**.
5. No campo **Versão do layout**, selecione a última versão disponível.
6. No campo **Motivo da identificação**, selecione a identificação relacionada.
7. Defina a opção **Envio atrasado** como **Sim** para gerar o registro 0900.

> [!NOTE]
> Para usar o processamento em lotes, selecione **Lote** e especifique as opções para a execução do processamento em lotes. Você poderá usar o processamento em lotes se o arquivo precisar ser gerado posteriormente ou se precisar ser gerado em um servidor, e não no computador.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]