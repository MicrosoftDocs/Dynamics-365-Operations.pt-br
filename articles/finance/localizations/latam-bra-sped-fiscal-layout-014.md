---
title: SPED fiscal ICMS-IPI layout 014
description: Este tópico explica como configurar e gerar o layout de demonstrativo 014 do SPED fiscal.
author: sndray
manager: AnnBe
ms.date: 01/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: f986fb232f1aee3a5c4ce7876739d211afc567eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408431"
---
# <a name="sped-fiscal-icms-ipi-layout-014"></a>SPED fiscal ICMS-IPI layout 014 

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar e gerar o layout de demonstrativo 014 do SPED fiscal. Este layout é aplicável a partir de janeiro de 2020, no guia prático, **EFD-ICMS/IPI – versão 3.0.3**.

Para exibir o novo layout, vá para **Livros fiscais** \> **Configuração** \> **Parâmetros das extensões de obrigações fiscais** \> **SPED Fiscal** \> **Parâmetros do SPED Fiscal** \> **Versão do layout**.

## <a name="record-0002-classification-of-fiscal-establishment"></a>Registro 0002: classificação do estabelecimento fiscal

O registro 0002 é gerado quando o campo **IND\_ATIV** do registro 0000 é definido como **0** (zero) e a classificação do estabelecimento fiscal é configurada e atribuída. Para configurar a classificação e atribuí-la ao estabelecimento fiscal, vá para **Livros fiscais** \> **Configuração** \> **Parâmetros das extensões de obrigações fiscais** \> **SPED fiscal** \> **Parâmetros do SPED Fiscal** \> **Classificação**.

Se mais de um tipo de classificação se aplicar ao estabelecimento fiscal, selecione a classificação mais relevante.

## <a name="record-c500-incoming-fiscal-documents"></a>Registro C500: notas fiscais de entrada

O registro C500 é gerado para os modelos de notas fiscais de entrada 6, 66, 29 e 28. Os novos campos a seguir são incluídos como parte do novo layout.

| Número | Campo          | Descrição |
|--------|----------------|-------------|
| 28     | CHV\_DOCe      | Se o modelo da nota fiscal for 66, a chave de acesso da nota fiscal. Caso contrário, esse campo ficará em branco. |
| 29     | FIN\_DOCe      | Se o modelo da nota fiscal for 66, o valor fixo **1**. Caso contrário, esse campo ficará em branco. |
| 30     | CHV\_DOCe\_REF | Se o modelo da nota fiscal for 66, a chave de acesso da nota fiscal referenciada, se existir uma nota fiscal referenciada. Caso contrário, esse campo ficará em branco. |
| 31     | IND\_DEST      | O valor fixo **1**, porque o estabelecimento fiscal é o contribuinte do ICMS. |
| 32     | COD\_MUN\_DEST | O código IBGE do estabelecimento fiscal. |
| 33     | COD\_CTA       | A conta principal de despesa ou ativo lançada para a nota fiscal |

## <a name="complement-and-compensation-of-icms-st-tax"></a>Complemento e compensação de imposto ICMS-ST

A autoridade fiscal introduziu os registros C180, C185, 1010 e 1250 para registrar detalhes das operações sujeitas ao imposto ICMS-ST quando a empresa aplica o complemento e a compensação do imposto ICMS-ST. Cada estado abordará a geração desses registros.

### <a name="prerequisites"></a>Pré-requisitos

Antes de habilitar a geração dos registros C180, C185, 1010 e 1250, você deve habilitar o cálculo do imposto presumido. Acesse **Administração da organização** \> **Configuração** \> **Parâmetros brasileiros** \> **Nota fiscal** e ative os seguintes parâmetros:
    
- ICMS-ST  presumido
- Imposto ICMS-ST presumido em livros fiscais

Em seguida, siga as etapas abaixo para configurar a regra que permitirá a geração dos registros. A regra deve ser configurada para cada estado.

1. Vá para **Livros fiscais** \> **Configurar** \> **Parâmetros de livros fiscais por estado**.
2. Selecione o estado relacionado. Por exemplo, para o estado de São Paulo, selecione **SP**.
3. Defina a opção **Habilitar registro C180 e C185** como **Sim** para gerar os registros relacionados. Além disso, também serão geradas instâncias do registro H030 com o campo **MOT\_INV** definido como **06**, H005, 1010, 1250 e 1255.
4. No campo **Algoritmo de cálculo de impostos presumidos do SPED**, selecione o método de cálculo. Os valores calculados no processo de imposto presumido serão relatados no registro C185.
    
![Página Parâmetros de livros fiscais por estado](media/bra-sped-Fiscal014-Setup.png)   

### <a name="table-57--reason-code-table-for-complement-and-restitution"></a>Tabela 5.7 – Tabela de códigos de motivo para complemento e restituição

A Tabela 5.7 representa a classificação para complemento e restituição (remuneração) dos valores do ICMS-ST. Essa tabela é implementada por cada estado. Para configurá-la, vá para **Livros fiscais** \> **Configuração** \> **Código de motivo para complemento e restituição**.

![Página Código de motivo para complemento e restituição](media/bra-sped-fiscal014-table57-setup.png)

Depois de concluir a configuração da tabela de códigos de motivo (tabela 5.7), acesse **Livros fiscais** \> **Configuração** \> **Determinação da Tabela 5.7** e configure a determinação usando os seguintes critérios:

- Código do item
- Código CFOP
- Código de tributação

![Página Determinação da Tabela 5.7](media/bra-sped-fiscal014-table57-determination-setup.png)

### <a name="record-c180"></a>Registro C180

O registro C180 é um novo registro. Ele apresenta informações complementares para os modelos de notas fiscais de entrada 01, 1B, 04 e 55 para transações que incluem o tipo de imposto ICMS-ST. Esse registro é gerado com base nos seguintes critérios:

- Na página **Parâmetros de livros fiscais por estado**, a opção **Habilitar registro C180 e C185** é definida como **Sim**.
- As transações fiscais de nota fiscal têm código de tributação 10, 30, 60 ou 70.

Os campos a seguir estão incluídos.

| Número | Campo                        | Descrição |
|--------|------------------------------|-------------|
| 1      | REG                          | O valor fixo **C180**. |
| 2      | COD\_RESP\_RET               | Um código que indica a pessoa responsável pela retenção do ICMS-ST: **1-Remetente direto**, **2-Remetente indireto** ou **3-Próprio declarante**. Essa classificação está disponível na linha da nota fiscal. |
| 3      | QUANT\_CONV                  | A quantidade da nota fiscal de entrada. |
| 4      | UNID                         | A unidade de medida do campo **QUANT\_CONV**. |
| 5      | VL\_UNIT\_CONV               | O valor da linha por unidade, com base na unidade de medida usada para o campo **QUANT\_CONV** da nota fiscal de entrada. |
| 6      | VL\_UNIT\_ICMS\_OP\_CONV     | O valor do ICMS por unidade da operação própria que o estabelecimento fiscal tem direito a recuperar (crédito), com base na unidade de medida usada no campo **QUANT\_CONV**. A transação de imposto ICMS deve ser definida usando a taxa de impostos interna. |
| 7      | VL\_UNIT\_BC\_ICMS\_ST\_CONV | O valor base do ICMS-ST por unidade, com base na unidade de medida usada no campo **QUANT\_CONV**. |
| 8      | VL\_UNIT\_ICMS\_ST\_CONV     | O imposto presumido de ICMS-ST ou ICMS-ST, incluindo FCP, com base na unidade de medida usada para o campo **QUANT\_CONV**. |
| 9      | VL\_UNIT\_FCP\_ST\_CONV      | O ICMS-ST ou ICMS-ST presumiu o valor de FCP por unidade. |
| 10     | COD\_DA                      | O tipo de documento de coleção: **0-Documento do estado da coleta** ou **1-GNRE**. Essa classificação está disponível na linha da nota fiscal. |
| 11     | NUM\_DA                      | O número do documento de coleção de estado. Essa classificação está disponível na linha da nota fiscal. |

### <a name="record-c185"></a>Registro C185

O registro C185 é um novo registro. Ele apresenta informações complementares para os modelos de notas fiscais de saída 01, 1B, 04 e 55 para transações que incluem o tipo de imposto ICMS-ST. Esse registro é gerado com base nos seguintes critérios:

- Na página **Parâmetros de livros fiscais por estado**, a opção **Habilitar registro C180 e C185** é definida como **Sim**.
- As transações fiscais de nota fiscal têm código de tributação 10, 30, 60 ou 70.

Os campos a seguir estão incluídos.

| Número | Campo                                  | Descrição |
|--------|----------------------------------------|-------------|
| 1      | REG                                    | O valor fixo **C185**. |
| 2      | NUM\_ITEM                              | O número de sequência da linha do item da nota fiscal. |
| 3      | COD\_ITEM                              | O código do item da linha da nota fiscal. |
| 4      | CST\_ICMS                              | O código de tributação do ICMS. |
| 5      | CFOP                                   | Identificação da CFOP. |
| 6      | COD\_MOT\_REST\_COMPL                  | O código de motivo para restituição ou complemento, conforme a tabela 5.7. |
| 7      | QUANT\_CONV                            | A quantidade de itens. |
| 8      | UNID                                   | A unidade de medida. |
| 9      | VL\_UNIT\_CONV                         | O valor de mercadorias por unidade. |
| 10     | VL\_UNIT\_ICMS\_NA\_OPERACAO\_CONV     | O valor do ICMS por unidade. |
| 11     | VL\_UNIT\_ICMS\_OP\_CONV               | O ICMS-ST presumiu o valor por unidade da nota fiscal de entrada. |
| 12     | VL\_UNIT\_ICMS\_OP\_ESTOQUE\_CONV      | O valor médio do imposto ICMS por unidade no estoque, com base na unidade de medida usada no campo **QUANT\_CONV**. |
| 13     | VL\_UNIT\_ICMS\_ST\_ESTOQUE\_CONV      | O valor médio do imposto ICMS-ST, incluindo FCP ST, das mercadorias em estoque, com base na unidade de medida usada no campo **QUANT\_CONV**. |
| 14     | VL\_UNIT\_FCP\_ICMS\_ST\_ESTOQUE\_CONV | A média do ICMS-ST FCP por unidade de mercadorias em estoque, com base na unidade de medida usada no campo **QUANT\_CONV**. |
| 15     | VL\_UNIT\_ICMS\_ST\_CONV\_REST         | O valor do ICMS-ST, incluindo o FCP ST, que será reembolsado. |
| 16     | VL\_UNIT\_FCP\_ST\_CONV\_REST          | O valor do ICMS-ST FCP que compõe o campo **VL\_UNIT\_ICMS\_ST\_CONV\_REST**, com base na unidade de medida usada para o campo **QUANT\_CONV**. |
| 17     | VL\_UNIT\_ICMS\_ST\_CONV\_COMPL        | O complemento do valor do ICMS, incluindo FCP ST, com base na unidade de medida usada no campo **QUANT\_CONV**. |
| 18     | VL\_UNIT\_FCP\_ST\_CONV\_COMPL         | O valor do ICMS-ST FCP que compõe o campo **VL\_UNIT\_ICMS\_ST\_CONV\_COMPL**, com base na unidade de medida usada para o campo **QUANT\_CONV**. |

> [!NOTE]
> Os valores dos campos 10 a 18 são recuperados com base no cálculo do imposto presumido do ICMS-ST na apuração do imposto ICMS-ST.

### <a name="record-1010"></a>Registro 1010

O novo campo a seguir é incluído como parte do novo layout.

| Número | Campo                           | Descrição |
|--------|---------------------------------|-------------|
| 14     | IND\_REST\_RESSARC\_COMPL\_ICMS | O valor fixo **S** se os registros gerados, C180 e C185, estiverem habilitados na página **Parâmetros de livros fiscais por estado**. Caso contrário, esse campo será definido como **N**. |

### <a name="record-1250"></a>Registro 1250

O registro 1250 é gerado para consolidar informações sobre o saldo do complemento ou restituição do ICMS e do ICMS-ST. Os campos a seguir estão incluídos.

<table>
<tr>
<th>Número</th>
<th>Campo</th>
<th>Descrição</th>
</tr>
<tr>
<td>1</td>
<td>REG</td>
<td>O texto fixo <strong>1250</strong>.</td>
</tr>
<tr>
<td>2</td>
<td>VL_CREDITO_ICMS_OP</td>
<td>A soma das instâncias do registro 1255 no campo <strong>VL_CREDITO_ICMS_OP_MOT</strong>.</td>
</tr>
<tr>
<td>3</td>
<td>VL_ICMS_ST_REST</td>
<td>A soma das instâncias do registro 1255 no campo <strong>VL_ICMS_ST_REST_MOT</strong>.</td>
</tr>
<tr>
<td>4</td>
<td>VL_FCP_ST_REST</td>
<td>A soma das instâncias do registro 1255 no campo <strong>VL_ICMS_FCP_REST_MOT</strong>.</td>
</tr>
<tr>
<td>5</td>
<td>VL_ICMS_ST_COMPL</td>
<td>A soma das instâncias do registro 1255 no campo <strong>VL_ICMS_ST_COMPL_MOT</strong>.</td>
</tr>
<tr>
<td>6</td>
<td>VL_FCP_ST_COMPL</td>
<td>A soma das instâncias do registro 1255 no campo <strong>VL_FCP_ST_COMPL_MOT</strong>.</td>
</tr>   
</table>


### <a name="record-1255"></a>Registro 1255

O registro 1255 é gerado para consolidar informações sobre o saldo do complemento ou restituição do ICMS por código de motivo (tabela 5.7). Os campos a seguir estão incluídos.

| Número | Campo                      | Descrição |
|--------|----------------------------|-------------|
| 1      | REG                        | O texto fixo **1255**. |
| 2      | COD\_MOT\_REST\_COMPL      | O código de motivo para o complemento ou a restituição, conforme a tabela 5.7. |
| 3      | VL\_CREDITO\_ICMS\_OP\_MOT | A soma do registro C185 no campo **VL\_UNIT\_ICMS\_OP\_CONV** × a quantidade no campo **QUANT\_CONV**. |
| 4      | VL\_ICMS\_ST\_REST\_MOT    | A soma do registro C185 no campo **VL\_UNIT\_ICMS\_ST\_CONV\_REST** × a quantidade no campo **QUANT\_CONV**. |
| 5      | VL\_FCP\_ST\_REST\_MOT     | A soma do registro C185 no campo **VL\_UNIT\_FCP\_ST\_CONV\_REST** × a quantidade no campo **QUANT\_CONV**. |
| 6      | VL\_ICMS\_ST\_COMPL\_MOT   | A soma do registro C185 no campo **VL\_UNIT\_ICMS\_ST\_CONV\_COMPL** × a quantidade no campo **QUANT\_CONV**. |
| 7      | VL\_FCP\_ST\_COMPL\_MOT    | A soma do registro C185 no campo **VL\_UNIT\_FCP\_ST\_CONV\_COMPL** × a quantidade no campo **QUANT\_CONV**. |

### <a name="record-h030"></a>Registro H030

O registro H030 é gerado juntamente com os registros H005 e H010 se o controle do complemento ou da restituição do imposto ICMS-ST foi habilitado por meio da definição da opção **Habilitar registro C180 e C185** como **Yes** na página **Parâmetros de livros fiscais por estado**.

Quando o registro H005 é gerado, o campo **MOT\_INV** é definido como **6**. O registro H010 é gerado da mesma maneira se o campo **MOT\_INV** não estiver definido como **6**. 

| Número | Campo            | Descrição |
|--------|------------------|-------------|
| 1      | REG              | O texto fixo **H030**. |
| 2      | VL\_ICMS\_OP     | O valor médio por unidade de operações do ICMS. |
| 3      | VL\_BC\_ICMS\_ST | O valor médio por unidade da base do ICMS-ST. |
| 4      | VL\_ICMS\_ST     | O valor médio por unidade do imposto ICMS-ST, incluindo o FCP. |
| 5      | VL\_FCP          | O valor médio POR UNIDADE do FCP do imposto ICMS-ST. |

## <a name="record-g130"></a>Registro G130

O registro G130 é gerado para identificar a nota fiscal das operações CIAP. O novo campo a seguir é incluído como parte do novo layout.

| Número | Campo   | Descrição |
|--------|---------|-------------|
| 9      | NUM\_DA | O número do documento de coleção de estado. Essa classificação está disponível na linha da nota fiscal. |

## <a name="record-g140"></a>Registro G140

O registro G140 é gerado para identificar a nota fiscal das operações CIAP. Os novos campos a seguir são incluídos como parte do novo layout.

| Número | Campo                   | Descrição |
|--------|-------------------------|-------------|
| 4      | QTDE                    | A quantidade que foi aplicada ao item. Essa quantidade é expressa na mesma unidade que a nota fiscal de entrada. |
| 5      | UNID                    | A unidade de medida da nota fiscal de entrada. |
| 6      | VL\_ICMS\_OP\_APLICADO  | O valor do ICMS da nota fiscal de entrada. Esse valor vem da coluna **ICMS** da apuração do CIAP. |
| 7      | VL\_ICMS\_ST\_APLICADO  | O valor do ICMS-ST da nota fiscal de entrada. Esse valor vem da coluna **ICMS-ST** da apuração do CIAP. |
| 8      | VL\_ICMS\_FRT\_APLICADO | O valor do ICMS da nota fiscal de entrada. Esse valor vem da coluna **ICMS no frete** da apuração do CIAP. |
| 9      | VL\_ICMS\_DIF\_APLICADO | O valor do ICMS-DIF da nota fiscal de entrada. Esse valor vem da coluna **ICMS-DIF** da apuração do CIAP. |
