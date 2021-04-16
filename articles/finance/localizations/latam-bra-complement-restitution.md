---
title: Processo e declaração de complemento e restituição do ICMS-ST para os Estados do RS, de SC e SP
description: Este tópico fornece informações sobre o processo de cálculo e relatório da compensação e restituição de valores do ICMS-ST em operações internas para consumidores finais quando os bens são adquiridos de acordo com o regime de substituição tributária (ICMS-ST). .
author: sndray
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 270254
ms.assetid: 92223189-69a8-4a40-b867-ef9b4f14c23d
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e3bbba8ce49e6e95fe5c63a454e5f03b6a47d887
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814006"
---
# <a name="icms-st-complement-and-restitution-process-and-declaration-for-rs-sc-and-sp-states"></a>Processo e declaração de complemento e restituição do ICMS-ST para os Estados do RS, de SC e SP

[!include [banner](../includes/banner.md)]

Os Estados do Rio Grande do Sul (RS), São Paulo (SP) e Santa Catarina (SC) definiram e implementaram um novo processo para calcular e relatar a compensação e a restituição dos valores do ICMS-ST em operações internas para os consumidores finais quando os bens são adquiridos de acordo com o regime de substituição tributária (ICMS-ST). Este processo se aplica a empresas de varejo e atacado.

O contribuinte deve, como regra geral, determinar mensalmente a diferença entre o valor do ICMS-ST calculado em notas fiscais de entrada e o valor do ICMS-ST calculado em notas fiscais de saída para o consumidor final. Exceções e regras específicas podem ser aplicáveis, de acordo com as leis estaduais.

A diferença entre os valores de entrada e saída é conhecida como *ajuste do ICMS-ST*, pois a correção pode ser positiva (+) ou negativa (-) e deve ser informada no SPED Fiscal ou outros demonstrativos de imposto relacionados.

- Os contribuintes precisam determinar o valor do ICMS-ST a receber dos bens sujeitos ao ICMS-ST
- O valor calculado do ICMS-ST deve ser comparado ao valor do ICMS-ST na compra
- Dependendo do resultado, os contribuintes precisam registrar o ajuste positivo ou negativo
- Determine o ICMS-ST a ser complementado ou restituído

## <a name="high-level-example"></a>Exemplo de alto nível

Compra – Valor base do ICMS-ST da nota fiscal de entrada = 80,00

ICMS-ST calculado =\> 80,00 × 18% = R\$ 14,00

Vendas – Valor base da nota fiscal de saída = 90,00

ICMS-ST efetivo = 90,00 × 18% = R\$ 16,20

**Valor do ICMS-ST a ser complementado** = (R\$ 16,20 (ICMS-ST efetivo) – R\$ 14,00) – (ICMS-ST de compra) = **R\$ 2,20** (\> 0,00)

–ou–

Compra – Nota fiscal de entrada BC ST = 80,00

ICMS-ST calculado =\> 80,00 × 18% = R\$ 14,00

Vendas – Valor base da nota fiscal de saída = 70,00

ICMS-ST efetivo = 70,00 × 18% = R\$ 12,60

**Valor do ICMS-ST a ser restituído** = (R\$ 12,60 (ICMS-ST efetivo) – R\$ 14,00) – (ICMS-ST de compra) = **R\$ 1,40** (\< 0,00)

## <a name="so-paulo-state-implementation"></a>Implementação do Estado de São Paulo

Um novo demonstrativo de imposto, CAT 1219, foi introduzido no Estado de SP. Este demonstrativo de imposto exige que as empresas enviem uma declaração de imposto ICMS-ST para os valores de ICMS-ST complementar e de restituição.

O arquivo de demonstrativo é gerado com base na versão 1.1.0 do documento de layout de diretrizes.

### <a name="scope"></a>Escopo

As tabelas a seguir apresentam informações sobre os registros gerados por meio do uso do demonstrativo CAT 1218.

#### <a name="record-0000--statement-opening-and-taxpayer-identification-and-participant-identification"></a>Registro 0000 – Abertura do demonstrativo, identificação do contribuinte e identificação do participante

| Número | Campo | Descrição                                                                                                                    |
|------------|-----------|------------------------------------------------------------------------------------------------------------------------------------|
| 01         | REG       | Texto fixo definido como **0000**                                                                                                 |
| 02         | PERÍODO   | Período do relatório                                                                                                               |
| 03         | NOME      | O nome comercial da entidade                                                                                                    |
| 04         | CNPJ      | O número de inscrição no CNPJ                                            |
| 05         | IE        | O número de Inscrição Estadual (IE) da entidade.                                                                                   |
| 06         | COD_NUM   | O código do Instituto Brasileiro de Geografia e Estatística (IBGE)                                                                   |
| 07         | COD_VER   | O código da versão do layout. Este campo é preenchido manualmente ao executar os relatórios.                                  |
| 08         | COD_FIN   | O código do objetivo do arquivo. Este campo é preenchido manualmente ao executar o relatório. Os valores a seguir estão disponíveis: |

-  **00** – Entrega normal de arquivo
-  **01** – Entrega de arquivo necessário pela autoridade fiscal
-  **02** – Entrega de arquivo para a substituição de um arquivo carregado anteriormente

#### <a name="record-0150--participant-table"></a>Registro 0150 – Tabela de participantes

Somente os usuários com transações no período de escrituração informado foram incluídos nesse registro. Há um registro por usuário.

| Número | Campo | Descrição                                                                  |
|------------|-----------|----------------------------------------------------------------------------------|
| 01         | REG       | Texto fixo definido como **0150**                                               |
| 02         | COD_PART  | O código de identificação do participante                                       |
| 03         | NOME      | A equipe ou o nome comercial do participante                                 |
| 04         | COD_PAIS  | O código de país/região do participante                                       |
| 05         | CNPJ      | O número de registro do participante no CNPJ                           |
| 06         | CPF       | O número de registro do participante no Cadastro de Pessoas Físicas (CPF) |
| 07         | IE        | O número de Inscrição Estadual do participante                                 |
| 08         | COD_MUN   | O código do IBGE.                                                                    |

#### <a name="record-0200--item-identification-table"></a>Registro 0200 – Tabela de identificação do item

Somente os itens com transações no período de escrituração informado foram incluídos nesse registro. Há um registro por item.

| Número | Campo  | Descrição                                               |
|------------|------------|---------------------------------------------------------------|
| 01         | REG        | Texto fixo definido como **0200**                            |
| 02         | COD_ITEM   | O código do item                                                 |
| 03         | DESCR_ITEM | A descrição do item                                   |
| 04         | COD_BARRA  | O código de barras do produto                                          |
| 05         | UNID_INV   | A unidade de medida do estoque                                 |
| 06         | COD_NCM    | O código de classificação fiscal                                |
| 07         | ALIQ_ICMS  | A taxa de ICMS aplicável ao item em operações internas |
| 08         | CEST       | O Código Especificador da Substituição Tributária (CEST)                    |

#### <a name="record-1050--balance"></a>Registro 1050 – Saldo

Esse relatório informa o valor total (posição de estoque inicial e posição de estoque final) de 1.100 registros. Há um registro por item. As informações são coletadas da funcionalidade **Saldos tributados presumidos** na apuração do imposto ICMS-ST.

| Número | Campo    | Descrição                                                                                                                              |
|------------|--------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| 01         | REG          | Texto fixo definido como **1050**                                                                                                           |
| 02         | COD_ITEM     | O código do item de acordo com o registro 0200                                                                                                       |
| 03         | QTD_INI      | A quantidade inicial de itens no início do período                                                                                     |
| 04         | ICMS_TOT_INI | O valor inicial acumulado do ICM total suportado pelo contribuinte e calculado para o item no início do período |
| 05         | QTD_FIM      | A quantidade final de itens no final do período                                                                                                |
| 06         | ICSM_TOT_FIM | O valor final acumulado do ICM total suportado pelo contribuinte e calculado para o item no final do período         |

#### <a name="record-1100--balance-details-record"></a>Registro 1100 – Registro de detalhes do saldo

Este registro informa os detalhes de documentos fiscais eletrônicos. Essas informações são coletadas das informações armazenadas nas guias **Saída** e **Entrada** da página **Impostos presumidos**.

| Número | Campo | Descrição                                                                                                                                     |
|------------|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| 01         | REG       | Texto fixo definido como **1100**                                                                                                                  |
| 02         | CHV_DOC   | O valor **ACCESSKEY** da nota fiscal eletrônica                                                                                                |
| 03         | DADOS      | A data da nota fiscal                                                                                                                            |
| 04         | NUM_ITEM  | O número sequencial do item na nota fiscal eletrônica                                                                                 |
| 05         | IND_OPER  | Um valor que indica o tipo de operação:                                                                                                          |
| 06         | COD_ITEM  | O código do item de acordo com o registro 0200                                                                                                              |
| 07         | CFOP      | O Código Fiscal de Operações e Prestações (CFOP)                                                                                                   |
| 08         | QTD.      | A quantidade de itens. Nenhum valor negativo é usado para devoluções. Os valores são sempre positivos.                                                         |
| 09         | ICMS_TOT  | O valor total do ICMS suportado pelo contribuinte em notas fiscais de entrada                                                              |
| 10         | VL_CONFR  | Os valores de ICMS e ICMS-ST para notas fiscais de saída                                                                                           |
| 11         | COD_LEGAL | O código de estrutura jurídica para a hipótese de restituição ou complemento do ICMS-ST. Para obter descrições dos códigos, consulte a tabela a seguir. |

-   **0** – Entrada

-   **1** – Saída:

A tabela a seguir descreve os códigos para a hipótese de restituição ou complemento de ICMS-ST.

| Código | Hipótese de restituição ou complemento ou ICMS-ST                                                                         | Observação                                                                                             |
|----------|--------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| 1        | Operação onde a restituição ou o complemento do ICM-ST é aplicável na hipótese do Item I do Artigo 269 do RICMS | Nota fiscal de saída para consumidores finais com o código do tipo de imposto ICMS-ST e tributação = 60                    |
| 2        | Operação onde a restituição do ICM-ST é aplicável na hipótese do Item II do Artigo 269 do RICMS              | Nota fiscal de saída para a redução de estoque CFOP 5.927/outros com o código do tipo de imposto ICMS e tributação = 90 |
| 3        | Operação onde a restituição do ICM-ST é aplicável na hipótese do Item III do Artigo 269 do RICMS             | Nota fiscal de saída – ICMS-CST [30] (isento ou não tributado)                                              |
| 4        | Operação onde a restituição do ICM-ST é aplicável na hipótese do Item IV do Artigo 269 do RICMS              | Nota fiscal de saída para outro Estado – ICMS-ST [60] (Interestaduais)                                         |
| 0        | Operação onde a restituição ou o complemento do ICMS-ST não é aplicável                                                      | Outras notas fiscais de saída com o código do tipo de imposto ICMS-ST e tributação \<\> 60                             |

## <a name="rio-grande-do-sul-state-implementation"></a>Implementação do Estado do Rio Grande do Sul

Através do Decreto 54308/2018, o Estado do RS estabeleceu o procedimento para calcular e reportar o complemento ou a restituição de valores do imposto ICMS-ST para colaboradores (varejistas e atacadistas) que realizam atividades que incluam bens sujeitos ao regime de substituição tributária (ICMS-ST).

O Estado definiu dois processos, um para empresas de varejo e outro para empresas de atacado.

### <a name="scope"></a>Escopo

O valor do ICMS-ST é calculado para complemento e restituição e é informado no ICMS-ST do SPED Fiscal no registro 1900 e registros de ajuste relacionados, como os registros 1921 e 1923, pois o Estado considera que esse processo é uma subapuração do ICMS-ST.

#### <a name="non-retailer-companies"></a>Empresas de atacado

| Gravar | Nível | Descrição                         | Comentário                                                                                                                                                                                                                                                                                                                            | Parâmetros do Estado do RS                                                                            |
|------------|-----------|-----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| 1001       | 1         | Abrir Bloco 1                         |                                                                                                                                                                                                                                                                                                                                         | A opção **Bloco 1900** é definida como **Sim**.                                                            |
| 1900       | 2         | Indicador de subapuração de imposto ICMS-ST |                                                                                                                                                                                                                                                                                                                                         | Os campos **Indicador de subapuração de imposto** e **Descrição da subapuração de imposto**                      |
| 1910       | 3         | Período de escrituração                          |                                                                                                                                                                                                                                                                                                                                         |                                                                                                         |
| 1920       | 4         | Valores TOTAIS                          | Resumo do registro 1921                                                                                                                                                                                                                                                                                                  |                                                                                                         |
| 1921       | 5         | RS001920                                | A transação de ajuste que resume todos os valores efetivos do ICMS de: notas fiscais de saída para consumidores finais (CFOP 5\*), onde CST = 60 e tipo de imposto = ICMS e/ou ICMS-ST                                                                                                                                                 | O código de ajuste selecionado no campo **Débito de notas fiscais de saída**              |
| 1923       | 6         | 1:N registros                             | Detalhes de notas fiscais de saída por item ou consolidadas por nota fiscal                                                                                                                                                                                                                                                        | A opção **Consolidar registro 1923**                                                                  |
| 1921       | 5         | RS021922                                | A transação de ajuste que resume o valor do ICMS-ST ou quando não houver o ICMS-ST, o valor presumido do ICMS de notas fiscais de entrada onde ICMS-ST = 60 e estão relacionados à nota fiscal de saída mencionada anteriormente. **Nota:** as notas fiscais de entrada dos itens são informadas somente no registro 1921-RS001920. | O código de ajuste selecionado no campo **Crédito de notas fiscais de entrada**             |
| 1923       | 6         | 1:N registros                             | Detalhes de notas fiscais de entrada por item ou consolidadas por nota fiscal                                                                                                                                                                                                                                                        | A opção **Consolidar registro 1923**                                                                  |
| 1921       | 4         | RS041921 ou RS011921                    | A transação de ajuste do complemento ou da restituição                                                                                                                                                                                                                                                                                 | O código de transação selecionado no campo **Complemento (reverso)** ou **Restituição (reversa)** |
| E220       |           | RS101921                                | A transação de ajuste criada para o relatório no registro E220                                                                                                                                                                                                                                                                     | O código de ajuste selecionado no campo **Complemento (E210-E220)**                            |
| E111       |           | RS011021                                | A transação de ajuste criada para o relatório no registro E111                                                                                                                                                                                                                                                                     | O código de ajuste selecionado no campo **Restituição (E111)**                                |

#### <a name="retail-companies"></a>Empresas de varejo

| Gravar | Nível | Descrição                         | Comentários                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Parâmetros do Estado do RS                                                                            |
|------------|-----------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| 1001       | 1         | Abrir Bloco 1                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | A opção **Bloco 1900** é definida como **Sim**.                                                            |
| 1900       | 2         | Indicador de subapuração de imposto ICMS-ST |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Os campos **Indicador de subapuração de imposto** e **Descrição da subapuração de imposto**                      |
| 1910       | 3         | Período de escrituração                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                         |
| 1920       | 4         | Valores TOTAIS                          | Resumo do registro 1921                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                         |
| 1921       | 5         | RS021921                                | **Crédito:** a transação de ajuste que resume o valor do ICMS-ST ou, quando não houver ICMS-ST, o imposto presumido do ICMS de todas as notas fiscais de entrada recebidas durante o período. Se a nota fiscal de entrada não tiver uma nota fiscal de saída no período, essas transações não serão consideradas no resumo                                                                                                 | O código de ajuste selecionado no campo **Crédito de notas fiscais de entrada**             |
| 1923       | 6         | 1:N registros                             | Detalhes de notas fiscais de entrada por item ou consolidadas por nota fiscal                                                                                                                                                                                                                                                                                                                                                                                                         | A opção **Consolidar registro 1923**                                                                  |
| 1921       | 5         | RS021920                                | **Crédito do estoque:** a transação de ajuste usada para registrar o crédito do estoque. Este valor é calculado em **Opção de saldo de imposto presumido** disponível no formulário **Apuração de imposto ICMS-ST,** em relação ao saldo inicial de estoque. Como esse ajuste deve ser informado em três parcelas, o campo **DESCR_COMPL_AJ** do registro 1921 contém o seguinte texto: "Valor adjudicado nos termos do RICMS, Livro III, art. 25-A, I, nota 05, 1/3" | O código de ajuste selecionado no campo **Crédito do estoque**                               |
| 1921       | 5         | RS011920                                | **Estorno de crédito:** a transação de ajuste que resumo o imposto ICMS da nota fiscal de saída para um consumidor não final, onde o código de tributação = 60 e/ou para um consumidor final, onde ICMS = código isento ou tributação não tributável \<\> 60                                                                                                                                                                                                                                    | O código de ajuste selecionado no campo **Estorno de crédito**                                   |
| 1921       | 5         | RS001920                                | **Débito:** A transação de ajuste que resume as notas fiscais de saída de ICMS efetivo (CFOP 5\*) para um consumidor final, onde código de tributação = 60                                                                                                                                                                                                                                                                                                                           | O código de ajuste selecionado no campo **Débito de notas fiscais de saída**              |
| 1923       | 6         | 1:N registros                             | Detalhes de notas fiscais de saída por item ou consolidadas por nota fiscal                                                                                                                                                                                                                                                                                                                                                                                                         | A opção **Consolidar registro 1923**                                                                  |
| 1921       | 5         | RS041921                                | A transação de ajuste do complemento ou da restituição                                                                                                                                                                                                                                                                                                                                                                                                                                  | O código de transação selecionado no campo **Complemento (reverso)** ou **Restituição (reversa)** |
| 1926       | 5         | ICMS-ST do pagamento                         | Equivalente a E250. Esse registro é gerado quando houver um valor a ser cobrado e houver um pagamento na apuração do imposto ICMS-ST (compensação).                                                                                                                                                                                                                                                                                                                                           |                                                                                                         |
| E220       |           | RS101921                                | A transação de ajuste criada para o relatório no registro E220                                                                                                                                                                                                                                                                                                                                                                                                                      | O código de ajuste selecionado no campo **Complemento (E210-E220)**                            |
| E111       |           | RS011021                                | A transação de ajuste criada para o relatório no registro E111                                                                                                                                                                                                                                                                                                                                                                                                                      | O código de ajuste selecionado no campo **Restituição (E111)**                                |

## <a name="santa-catarina-state-implementation"></a>Implementação do Estado de Santa Catarina

Na Portaria SEF Nº 396/2018, o Estado de SC estabeleceu o procedimento para calcular e reportar o complemento ou a restituição dos valores do ICMS-ST para colaboradores (varejistas e atacadistas) que realizam atividades que incluam bens sujeitos ao regime de substituição tributária (ICMS-ST).

### <a name="scope"></a>Escopo

| Bloquear | Nível | Registros | Descrição                                                                                                              |
|-----------|-----------|-------------|-------------------------------------------------------------------------------------------------------------------------------|
| 0         | 0         | 0000        | Abrir arquivo                                                                                                                  |
|           | 1         | 0001        | Abrir bloco 0                                                                                                               |
|           | 2         | 0005        | Informações complementares da entidade legal                                                                                     |
|           | 2         | 0100        | Informações do contador                                                                                                        |
|           | 2         | 0190        | Identificação da unidade de medida                                                                                                |
|           | 2         | 0200        | Identificação de bens e serviços                                                                                             |
|           | 2         | 0220        | Conversão de unidade de medida                                                                                                    |
|           | 2         | 0990        | Fechar bloco 0                                                                                                               |
| H         | 1         | H001        | Abrir bloco H                                                                                                               |
|           | 2         | H005        | Totais de estoque                                                                                                              |
|           | 2         | H010        | Posição de estoque                                                                                                            |
|           | 1         | H990        | Fechar bloco H                                                                                                               |
| 2         | 2         | 2001        | Abrir bloco 2                                                                                                               |
|           | 2         | 2100        | Apuração mensal - totais do complemento e da restituição de bens sujeitos ao tipo de imposto ICMS-ST                                |
|           | 3         | 2110        | Apuração mensal - totais de complemento e restituição detalhados por produto                                                   |
|           | 4         | 2113        | Modelo da nota fiscal 55 de venda/devolução de bens identificados no registro 2110                                                   |
|           | 5         | 2114        | Complemento da nota fiscal referenciada na devolução de vendas                                                                      |
|           | 5         | 2115        | Nota fiscal complementar de venda                                                                                           |
|           | 4         | 2120        | Média ponderada mensal unitária da base de cálculo do imposto ICMS-ST em relação à própria operação e ICMS-ST do recebimento de bens |
|           | 5         | 2130        | Modelo 55 da nota fiscal do recebimento de bens com o tipo de imposto ICMS-ST identificado no registro 2110 e devoluções relacionadas                 |
|           | 6         | 2132        | Complemento da nota fiscal referenciada nas devoluções de compras                                                                  |
|           | 6         | 2136        | Notas fiscais complementares de compra                                                                                       |
|           | 1         | 2990        | Fechar bloco 2                                                                                                               |
| 9         | 1         | 9001        | Abrir bloco 9                                                                                                               |
|           | 2         | 9900        | Registros de arquivos                                                                                                                  |
|           | 1         | 9990        | Fechar bloco 9                                                                                                               |
|           | 0         | 9999        | Fechar arquivo                                                                                                                  |

Os registros a seguir fazem parte do escopo: 2112 (notas fiscais de saída geradas pela impressora fiscal ECF) e 2131.

### <a name="setup"></a>Configurar

1. Vá para **Administração da organização** \> **Configuração** \> **Parâmetros brasileiros**.
2. Na guia **Nota fiscal** , na seção **ICMS-ST** , defina as opções **Sim**:

    -  **Impostos presumidos do ICMS-ST** – Habilite esse processo para gerar marcas relacionadas no formato XML quando uma NF-e for emitida para autoridades fiscais.
    -  **Livros fiscais de imposto presumido do ICMS-ST** – Habilite este processo para calcular valores de restituição e compensação do ICMS-ST e gerar relatórios relacionados, de acordo com o Estado onde o estabelecimento fiscal tem o registro do ICMS-ST (SC, SP ou RS).

    ![Página de parâmetros brasileiros, seção ISMS-ST](media/brazil-icms-01.png)

3. Vá para **Livros fiscais** \> **Configuração** \> **Parâmetros de livros fiscais por Estado**, selecione o Estado adequado (**SP**, **SC**, ou **RS**).

### <a name="presumed-tax"></a>Imposto presumido

No FastTab **Impostos presumidos** da página **Parâmetros de livros fiscais por Estado**, defina os seguintes parâmetros:

-  **Algoritmo de cálculo de impostos presumidos** – Selecione o método usado para calcular os impostos presumidos do ICMS-ST quando as notas fiscais de saída para consumidores finais e não finais não forem gerados e lançados no Dynamics 365 Finance. Esse parâmetro é usado para preencher as marcas relacionadas ao modelo de nota fiscal NF-e.

    -  **Última compra** – Usa as informações das notas fiscais de entrada mais recentes lançadas durante o período.

-  **Algoritmo de cálculo de impostos presumidos do SPED** – Selecione o método usado para calcular o ICMS-ST presumido das apurações de impostos ICMS-ST no módulo **Livros fiscais**:

    -  **Média** – Calcule o valor médio de notas fiscais de entrada. Este método deve ser selecionado para o Estado de SP ou SC.
    -  **Última compra** – Usa as informações das notas fiscais de entrada mais recentes lançadas durante o período. Este método deve ser selecionado para o Estado de RS.

  ![Página de parâmetros de livros fiscais por Estado, FastTab de imposto presumido](media/brazil-icms-02.png)

### <a name="icms-st-sub-tax-assessment-in-rs-state"></a>subapuração do imposto ICMS-ST no Estado do RS

Para o Estado do RS, como os valores e os detalhes do cálculo das compensações e restituição do ICMS-ST são informados no SPED Fiscal no registro 1900 e outros registros relacionados, a configuração adicional é obrigatória para criar automaticamente as transações de ajuste estabelecidas pelo Decreto 54308/2018.

Vá para **Livros fiscais** \> **Configuração** \> **Parâmetros de livros fiscais por Estado**, selecione o Estado **RS** e, em seguida, no FastTab **Parâmetros do ICMS-ST da subapuração**, configure os parâmetros a seguir:

-  **Bloco 1900** – Defina esta opção como **Sim** para gerar os registros de subapuração de imposto ICMS-ST detalhados na sessão do escopo.
-  **Indicador de subapuração de imposto** – Selecione o tipo de indicador usado para identificar a subapuração de imposto.
-  **Descrição da subapuração de imposto** – Insira uma descrição da subapuração de imposto que é informada no campo **03 DESCR_COMPL_OUT_APUR** do registro 1900.
-  **Nome do diário para ajuste de restituição/complemento** – Selecione o diário usado para criar e lançar a apuração de imposto de compensação e restituição.
-  **Crédito de notas fiscais de entrada** – Selecione o código de ajuste relacionado para este tipo de ajuste.
-  a **Débito de notas fiscais de saída** – Selecione o código de ajuste relacionado a este tipo de ajuste.
-  **Empresa de varejo** – Define esta opção como **Sim** se a atividade comercial principal nesse estado for de varejo. Caso contrário, defina a opção como **Não**.
-  **Estorno de crédito** – Selecione o código de ajuste relacionado a este tipo de ajuste.
-  **Crédito de estoque** – Selecione o código de ajuste relacionado a este tipo de ajuste.
-  **Estorno de crédito** – Selecione o código de ajuste relacionado a este tipo de ajuste.
-  **Restituição (reversa)** – Selecione o código de ajuste relacionado a este tipo de ajuste.
-  **Complemento (E210-E220)** – Selecione o código de ajuste relacionado a este tipo de ajuste. Quando esse ajuste for criado, a apuração de imposto ICMS-ST será atualizada.
-  **Restituição (E111)** – Selecione o código de ajuste relacionado a este tipo de ajuste. Quando esse ajuste é criado, a apuração de imposto ICMS será atualizada porque somente os créditos são permitidos na apuração de imposto ICMS.
-  **Consolidar registro 1923** – Defina esta opção como **Sim** para consolidar ou o relatório no registro 1923 por nota fiscal (nenhum item será detalhado). O campo **08 COD_ITEM** permanecerá em branco.

  ![Página de parâmetros de livros fiscais por Estado, FastTab de parâmetros do ICMS-ST da subapuração](media/brazil-icms-03.png)

## <a name="repro-steps"></a>Etapas de reprodução

### <a name="icms-st-tax-assessment"></a>Apuração de imposto ICMS-ST

Antes de gerar um demonstrativo para cada Estado, é necessário criar um período fiscal de escrituração para o mês, criar a subapuração do ICMS-ST para o Estado e calcular os saldos aplicáveis ao Estado. Se deseja criar um ajuste de crédito relacionado à posição de estoque, marque como **Sim** a caixa de seleção **Ajuste do estoque de crédito** no formulário de subapuração do ICMS-ST antes de confirmar.

> [!NOTE]
> O ajuste de crédito relacionado à posição do estoque é aplicável somente para os Estados do RS e de SC.

![Página de apuração do imposto ICMS-ST](media/brazil-icms-04.png)

1. Vá para **Livros fiscais** \> **Comum** \> **Apuração de imposto** \> **ICMS-ST**.
2. Na página **ICMS-ST**, no Painel de Ações, na guia **Geral**, no grupo **Exibir**, selecione **Saldo de impostos presumidos**.

    ![Página ICMS-ST, guia Geral no Painel de Ações](media/brazil-icms-05.png)

A página **Saldo de impostos presumidos** inclui os campos obrigatórios para fins de relatório. Veja alguns exemplos desses campos:

  - Código do item
  - Nome do produto
  - ID de Dimensão
  - Valores de dimensão do estoque
  - Unidade de medida do estoque
  - Quantidades
  - Taxa de imposto ICMS e valores de base do ICMS-ST
  - Valor por unidade de estoque e totais em estoque

  ![Página de saldo de impostos presumidos](media/brazil-icms-06.png)

No Painel de Ação, na guia **Geral**, no grupo **Cálculos**, selecione **Calcular saldos de estoque**. O sistema calcula o saldo inicial e final e exibe os valores por número do item.

Veja como a função do cálculo de saldo inicial funciona:

1. Valide se existe o saldo de imposto presumido para o período anterior. Se nenhum saldo for encontrado, o cálculo será iniciado. Se o saldo for encontrado, o procedimento considera os valores do período anterior.
2. Selecione todos os itens no estoque disponível com transações realizadas antes do período atual.
3. Calcule a quantidade de cada item selecionado no primeiro dia do período.
4. Localize a última compra de cada item com transação de imposto ICMS-ST.
5. Ao usar os valores de imposto da última compra e converter a unidade de compra para a unidade de estoque, calcule os valores de ICMS e ICMS-ST para a quantidade de estoque disponível.

Veja como a função do cálculo de saldo final funciona. Esta função é aplicável somente ao Estado do SP.

1. Exclua os saldos de impostos presumidos para o período, salvo aqueles usados para o período seguinte. Esses valores serão atualizados e todos os demais valores recalculados.
2. Selecione todos os itens no estoque disponível com transações durante o período.
3. Procure o imposto presumido de cada item.
4. Calcule o saldo nos períodos anteriores para obter a quantidade de saldo inicial. Se não houver saldo nos períodos anteriores, a quantidade do saldo inicial será zero (0).
5. Selecione todas as notas fiscais de entrada no período, faça um resumo dos valores de impostos ICMS e ICMS-ST e das quantidades dos itens.
6. Calcule o valor médio por unidade ao resumir os totais dos valores do ICMS e ICMS-ST em todas as notas fiscais de entrada e dividi-los pela quantidade resumida nesses documentos.
7. Selecione todas as notas fiscais de saída e resuma as suas quantidades. Em seguida, calcule os valores de impostos ICMS e ICMS-ST usando o valor médio calculado na etapa 6.
8. Calcule os valores de saldo final e as quantidades usando os valores dos períodos anteriores e as somas de notas fiscais de entrada e saída do período atual. Essas somas foram calculadas nas etapas 5 e 7, respectivamente.

#### <a name="presumed-tax-calculation"></a>Cálculo imposto presumido

Depois que os saldos forem calculados pela primeira vez, abra a página **Impostos presumidos** e selecione **Calcular imposto presumido**.

![Página de impostos presumidos](media/brazil-icms-07.png)

A página inclui campos obrigatórios para fins de relatório. As guias mostram as notas fiscais relacionadas aplicáveis para compensação e restituição de acordo com os critérios estabelecidos pela lei estadual.

> [!NOTE]
> A guia **Estorno de crédito** é aplicável somente ao Estado do RS e esta guia exibe as notas fiscais para consumidores não finais, onde código de tributação = 60 e/ou para consumidores finais, onde ICMS = código de tributação isento ou não tributável \<\> 60.

A parte inferior da página mostra os valores totais.

![Valores totais exibidos na página Imposto presumido](media/brazil-icms-08.png)

Veja como o algoritmo da média para o cálculo de imposto presumido funciona:

1. Selecione todas as linhas de todas as notas fiscais de saída no período atual.
2. Para cada item dessas linhas, selecione todas as linhas de todas as notas fiscais de entrada com o mesmo código de item no período atual. Em seguida, calcule os valores médios dos impostos ICMS e ICMS-ST.
3. Se não houver notas fiscais de entrada no período, considere o registro correspondente nos saldos de imposto presumido.

> [!NOTE]
> Para o Estado de SP, os valores médios de notas fiscais complementares de vendas e ordens de compra não são calculados. Somente os valores das notas fiscais originais são considerados.

#### <a name="generate-adjustments"></a>Gerar ajustes

Para o Estado de RS, use o botão **Gerar ajustes** para gerar o ajuste de imposto relacionado a ser informado no SPED Fiscal.

Dependendo do tipo de negócio da empresa (varejo ou atacado), o Finance gera os ajustes relacionados:

  - Débito para notas fiscais de saída.
  - Crédito para notas fiscais de entrada.
  - Crédito da posição de estoque (saldo inicial). Este ajuste de imposto é criado uma vez e dividido em três prestações.
  - Estorno de crédito.
  - Compensação e restituição (estorno).
  - Compensação no registro E220.
  - Restituição no registro E111.

> [!NOTE]
> Após selecionar **Gerar ajustes**, não há como reverter o estado inicial. Para gerar um relatório do registro E220 ou E111, reverta manualmente a transação de ajuste criada durante a execução da função Gerar ajustes. Os outros ajustes relacionados a débito, crédito, crédito do estoque e estorno de crédito são criados somente para fins do SPED Fiscal. Não será possível visualizar essas transações, pois elas são salvas em uma tabela temporária.

### <a name="generate-a-statement"></a>Gere um demonstrativo

#### <a name="sp-state"></a>Estado de SP

1. Vá para **Livros fiscais** \> **Comum** \> **Período de escrituração** e, em seguida, na guia **Demonstrativos de imposto**, selecione **CAT 4218 SP**. Este demonstrativo também está disponível na apuração de imposto ICMS-ST do Estado de SP.
2. No campo **Nome do arquivo**, insira o caminho completo no qual o arquivo de texto deve ser salvo. Incluir o nome do arquivo.
3. No campo **Versão do layout**, selecione a versão.
4. No campo **Tipo de arquivo**, selecione o tipo de arquivo:

    - Regular (início no primeiro dia do ano)
    - Indicação específica
    - Substituto

O arquivo de texto gerado deve ser validado primeiro usando o aplicativo de autoridade fiscal Após o arquivo ser aprovado, é possível enviar as informações para as autoridades fiscais.

#### <a name="rs-state"></a>Estado do RS

1. Vá para **Livros fiscais** \> **Comum** \> **Período de escrituração** e, em seguida, na guia **Demonstrativos de imposto**, selecione **SPED fiscal**. Este demonstrativo também está disponível na apuração do imposto ICMS-ST do Estado do RS.
2. Defina os parâmetros geralmente configurados para gerar o demonstrativo do SPED Fiscal. Para gerar o registro 1900 e outros registros relacionados, é necessário definir os parâmetros obrigatórios para gerar o demonstrativo do SPED Fiscal. Para configurar esses parâmetros, siga as etapas:
3. Crie e sincronize o período de escrituração relacionado.
4. Sincronize o estoque. Se aplicável, use o crédito do saldo inicial do estoque.
5. Crie ou atualize a apuração de imposto ICMS-ST para o Estado do RS.
6. Calcule os saldos de imposto presumido (se aplicável).
7. Calcule o imposto presumido.
8. Gere ajustes.
9. Execute as demais etapas relacionadas à apuração de imposto ICMS-ST.
10. Gere o demonstrativo do SPED Fiscal como de costume.

#### <a name="sc-state"></a>Estado de SC

1. Vá para **Livros fiscais \> Configuração \> Parâmetros de demonstrativos de imposto** e selecione **SPED DRCST**.
2. Na FastTab **Parâmetros de configuração**, adicione o endereço na internet e o endereço do cabeçalho da solicitação, para que o arquivo XML relacionado possa ser enviado para as autoridades fiscais do governo.

    ![Página de parâmetros de demonstrativo de imposto, FastTab de parâmetros de configuração](media/brazil-icms-09.png)

3. Vá para **Administração da organização \> Configuração \> Parâmetros brasileiros**.
4.  Na guia **Nota fiscal**, na seção, **ICMS-ST**, defina as opções como **Sim** para habilitar a funcionalidade para calcular impostos presumidos no processo de emissão de NF-e e na apuração de imposto ICMS-ST do SPED Fiscal:

    - ICMS-ST presumido
    - Imposto ICMS-ST presumido em livros fiscais

5. Vá para **Livros fiscais** \> **Comum** \> **Período de escrituração** e, em seguida, na guia **Demonstrativos de imposto**, selecione **SPED DRCST**. Este demonstrativo também está disponível na apuração de imposto ICMS-ST do Estado de SC.
6.  No campo **Nome do arquivo**, insira o caminho completo no qual o arquivo de texto deve ser salvo. Inclua o nome do arquivo.
7.  No campo **Tipo de arquivo**, selecione o tipo de arquivo.

O arquivo é enviado usando os serviços web. É obrigatório ter um certificado. Após a mensagem de devolução ser recebida com o resultado da validação do governo, a resposta é salva no mesmo local onde o arquivo foi gerado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]