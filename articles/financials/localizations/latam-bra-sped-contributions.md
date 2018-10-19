---
title: "Configurar parâmetros de SPED EFD"
description: "Este tópico explica como configurar parâmetros do SPED EFD para o Brasil."
author: ShylaThompson
manager: AnnBe
ms.date: 08/27/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: shylaw
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 965826f5fddc2f53f33157434929eb265979376e
ms.openlocfilehash: f7d079b1dd63286911fd7a6ea4da459fa3168740
ms.contentlocale: pt-br
ms.lasthandoff: 09/17/2018

---

# <a name="set-up-parameters-for-sped-efd---contributions"></a>Configurar parâmetros para SPED EFD - Contribuições

[!include [banner](../includes/banner.md)]

Este tópico explica como especificar parâmetros para arquivos de texto SPED EFD - Contribuições usando o formulário **Parâmetros da EFD - Contribuições**.

Os arquivos de texto SPED EFD - Contribuições são gerados por entidades legais que já têm a obrigação de emitir o SPED de Contabilidade e Fiscal. Os arquivos de texto incluem as transações que representam a receita tributável e não tributável do Programa de Integração Social (PIS) e da Contribuição para o Financiamento da Seguridade Social (COFINS), e o custo ou despesas que têm um crédito de PIS e COFINS.

## <a name="set-up-requirements-for-sped-efd---contributions"></a>Configurar requisitos para SPED EFD - Contribuições

Para configurar os requisitos para os arquivos de texto de SPED EFD – Contribuições, siga estas etapas.

1.  Selecione **Livros fiscais** \> **Configuração** \> **Parâmetros das extensões de obrigações fiscais**.
2.  Selecione **EFD - Contribuições** e, em seguida, na Guia Rápida **Parâmetros de configuração**, selecione **Abrir**.

    A página **Parâmetros da EFD - Contribuições** será exibida, na qual você pode inserir as informações necessárias dos arquivos de texto do SPED EFD – Contribuições.

3.  No campo **Local do arquivo**, insira o local no qual os arquivos de texto de SPED EFD - Contribuições devem ser salvos.
4.  No campo **Tipo de atividade**, selecione o tipo de atividade:

    - Industrial ou equivalente
    - Prestador de serviços
    - Retail
    - Atividade financeira
    - Atividade imobiliária
    - Diversas

5.  No campo **Versão de layout**, selecione a versão do layout SPED EFD – Contribuições.
6.  No campo **Tipo de entidade legal**, selecione o tipo de entidade legal.
7.  No campo **Tipo de empresa**, selecione o tipo de empresa:

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

## <a name="record-0111"></a>Registro 0111

Registro em 0111 SPED EFD - Os arquivos de texto das contribuições são gerados automaticamente quando o método de alocação de crédito for definido como **Distribuição proporcional**.

O registro é gerado com base em transações de imposto que satisfaçam aos seguintes critérios.

<table>
<thead>
<tr>
<th>Conceito</th>
<th>Critérios</th>
</tr>
</thead>
<tbody>
<tr>
<td>Receita tributável</td>
<td><ul>
<li><strong>Regime - não cumulativo</strong> – Transações de impostos que têm uma taxa de impostos não cumulativa e uma taxa de imposto específica.</li>
<li><strong>Valor fiscal</strong> – Transações de impostos em que um valor fiscal é 1 (com débito).</li>
<li><strong>CFOP</strong> – Transações de impostos nas quais o Código Fiscal de Operações e de Prestações (CFOP) começa com 5 ou 6.</li>
</ul></td>
</tr>
<tr>
<td>Receita não tributável</td>
<td><strong>Valor fiscal</strong> – Transações de impostos em que um valor fiscal é 2 (isenção) ou 3 (outros não tributáveis).</td>
</tr>
<tr>
<td>Receita estrangeira</td>
<td><ul>
<li><strong>Valor fiscal</strong> – Transações de impostos em que um valor fiscal é 1 (tributável).</li>
<li><strong>CFOP</strong> – Transações de impostos em que CFOP começa com 7.</li>
</ul></td>
</tr>
<tr>
<td>Sem receita</td>
<td>Todas as transações de impostos nas quais o código de tributação é 49 ou 99.</td>
</tr>
</tbody>
</table>

