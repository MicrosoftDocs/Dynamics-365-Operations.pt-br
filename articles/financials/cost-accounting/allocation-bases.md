---
title: "Bases de alocação"
description: "Este tópico fornece informações sobre bases de alocação. As bases de alocação são componentes-chave na contabilização de custo e são mais usadas para alocar custos gerais indiretos."
author: AndersGirke
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 63f39a6c06a0c6b5df901f7aa4235aab3c4ac06e
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="allocation-bases"></a>Bases de alocação 

[!include [banner](../includes/banner.md)]

Uma base de alocação é a base na qual a contabilização de custo aloca custos gerais indiretos. Uma base de alocação pode ser uma quantidade, como as horas de máquina usadas, as horas de quilowatt (kWh) que são consumidos ou a, área que está ocupada. As bases de alocação são muito usadas para atribuir custos gerais indiretos ao estoque produzido. Por exemplo, um departamento de TI aloca as despesas de acordo com o número de computadores que cada departamento usa.

Há três tipos de bases de alocação na contabilização de custos:

- Bases de alocação de membro de dimensão predefinido
- Bases de alocação de hierarquia
- Bases de alocação de fórmulas

## <a name="predefined-dimension-member-allocation-bases"></a>Bases de alocação de membro de dimensão predefinido

As bases de alocação do membro da dimensão predefinidas serão criadas automaticamente quando um membro da dimensão de um dos seguintes tipos for criado:

- Membros de dimensão estatística
- Membros de dimensão do elemento de custo

> [!NOTE]
> As bases de alocação do membro da dimensão predefinida são baseadas em um membro de dimensão do elemento de custo que considera os valores somente do provedor da fonte de dados, como a contabilidade ou o orçamento.

### <a name="example-1-use-a-cost-element-dimension-member-as-the-allocation-base"></a>Exemplo 1: Use um membro de dimensão do elemento de custo previsto como a base de alocação
Esse exemplo mostra como criar uma regra de alocação de custo para alocar o elemento de custo (10002 seguro de funcionário) ao saldo registrado no elemento de custo 10001 (Salários). A regra de alocação é definida com base na taxa de salários de cada departamento para o total de salários. (Revisão necessária)

Na contabilidade, o plano de contas será definido como segue.

| Plano de contas | Conta principal | descrição        | Tipo de conta principal |
|------------------|--------------|--------------------|-------------------|
| Compartilhado           | 10001        | Salários           | Despesa           |
| Compartilhado           | 10002        | Seguro de funcionário | Despesa           |

Defina a dimensão de um elemento de custo e configura o conector de dados. Depois que dados são importados, as seguintes entradas são criadas na contabilização de custo.

**Membros de dimensão do elemento de custo**

| Nome da dimensão do elemento de custo | Elemento de custo |  descrição       | Tipo    |
|-----------------------------|--------------|--------------------|---------|
| Elementos de custo               | 10001        | Salários           | Principal |
| Elementos de custo               | 10002        | Seguro de funcionário | Principal |

**Bases de alocação de membro de dimensão predefinido** 

| Nome  | descrição        | Dimensão do elemento de custo |
|-------|--------------------|------------------------|
| 10001 | Salários           | Elementos de custo          |
| 10002 | Seguro de funcionário | Elementos de custo          |

Na contabilidade, as seguintes entradas foram lançadas:

- As entradas que mostram a conta principal de salários vem do sistema da Folha de pagamentos e são lançadas para os centros de custos.
- A despesa do seguro de funcionário é lançada manualmente em um centro de custos padrão.

| Data contábil | Centro de custos |  descrição        | Conta principal |  descrição       | Valor em moeda contábil |
|-----------------|-------------|---------------------|--------------|--------------------|-------------------------------|
| 03/01/2017      | CC001       | RH                  | 10001        | Salários           | 2.000,00                      |
| 03/01/2017      | CC002       | FI                  | 10001        | Salários           | 5.000,00                      |
| 03/01/2017      | CC003       | TE                  | 10001        | Salários           | 3.000,00                      |
| 03/01/2017      | CC099       | Centro de custos padrão | 10002        | Seguro de funcionário | 1.000,00                      |

Depois que dados de origem da contabilidade forem processados, as seguintes entradas serão criadas na contabilização de custo.

**Entradas de custo**

| Objeto de custo |  descrição        | Elemento de custo  |  descrição       | Comportamento de custo   |Valor|Data contábil|
|-------------|---------------------|---------------|--------------------|-----------------|------|---------------|
| CC001       | RH                  | 10001         | Salários           | Não classificado    |2.000,00|  03/01/2017    |
| CC002       | FI                  | 10001         | Salários           | Não classificado    |5.000,00|     03/01/2017         |
| CC003       | TE                  | 10001         | Salários           | Não classificado    |3.000,00|      03/01/2017        |
| CC099       | Centro de custos padrão | 10002         | Seguro de funcionário | Não classificado    |1.000,00|      03/01/2017       |

Neste exemplo simplificado, uma regra de alocação de custo é criada para alocar o elemento de custo 10002 (seguro de funcionário) relativo ao saldo registrado no elemento de custo 10001 (Salários).

**Regras de distribuição de custo**

| Nó de hierarquia da dimensão de objeto de custo | Nó de hierarquia da dimensão de elemento de custo | Comportamento de custo | Base de alocação |
|--------------------------------------|---------------------------------------|---------------|-----------------|
| CC099                                | 10002                                 | Não classificado  | 10001           |

**Executar cálculo de custos indiretos**

Depois que o elemento de custo 10001 (Salários) for aplicado como a base de alocação, o resultado de cálculo de custos indiretos será o seguinte.

| Objeto de custo | descrição | Magnitude |   Fator de alocação         | Valor |
|-------------|-------------|-----------|-----------------------------|--------|
| CC001       | RH          | 2.000     | (2.000 ÷ 10.000) × 1.000,00 | 200,00 |
| CC002       | FI          | 5.000     | (5.000 ÷ 10.000) × 1.000,00 | 500,00 |
| CC003       | TE          | 3.000     | (3.000 ÷ 10.000) × 1.000,00 | 300,00 |

**Diário**

| Diário | Tipo de diário                          | Período do calendário fiscal | Ano | Período   | Versão                                                                 |
|---------|---------------------------------------|------------------------|------|----------|-------------------------------------------------------------------------|
| 00001   | Diário de cálculo de distribuição de custo | fiscal                 | 2017 | Período 1 | Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1 |

**Entradas de diário para saldo do objeto de custo**

| Data contábil | Objeto de custo | descrição         | Elemento de custo | descrição        | Comportamento de custo |  Valor  |
|-----------------|-------------|---------------------|--------------|--------------------|---------------|----------|
| 31/01/2017      | CC099       | Centro de custos padrão | 10002        | Seguro de funcionário | Não classificado  | 1.000,00 |

**Entradas de custo**

| Objeto de custo |  descrição        | Elemento de custo |    descrição     | Comportamento de custo | Valor    | Data contábil |
|-------------|---------------------|--------------|--------------------|---------------|-----------|-----------------|
| CC099       | Centro de custos padrão | 10002        | Seguro de funcionário | Não classificado  | -1.000,00 | 31/01/2017      |
| CC001       | RH                  | 10002        | Seguro de funcionário | Não classificado  | 200,00    | 31/01/2017      |
| CC002       | FI                  | 10002        | Seguro de funcionário | Não classificado  | 500,00    | 31/01/2017      |
| CC099       | TE                  | 10002        | Seguro de funcionário | Não classificado  | 300,00    | 31/01/2017      |

### <a name="example-2-use-a-statistical-dimension-member-as-the-allocation-base"></a>Exemplo 2: Use um membro de dimensão estatística como a base de alocação

Os membros de dimensão estatística podem ser usados como bases de alocação para definir políticas ou relatar o consumo não monetário por objetos de custo. Você pode criar manualmente membros da dimensão estatística ou importá-los de um arquivo usando a ferramenta de exportação/importação de gerenciamento de dados.

**Membros de dimensão estatística**

| Nome da dimensão estatística | Elemento estatístico | descrição               | Unidade |
|----------------------------|---------------------|---------------------------|------|
| Elementos estatísticos       | FTE                 | Funcionários em horário integral       | Cada   |
| Elementos estatísticos       | eletricidade         | Consumo de eletricidade   | kWh  |

Quando um membro estatístico de dimensão é salvo, um registro correspondente é criado nas bases de alocação do membro da dimensão predefinida.

**Bases de alocação de membro de dimensão predefinido**

| Nome        | descrição             | Dimensão de elemento estatístico |
|-------------|-------------------------|-------------------------------|
| FTE         | Funcionários em horário integral     | Elementos estatísticos          |
| eletricidade | Consumo de eletricidade | Elementos estatísticos          |

As medições estatísticas podem vir de várias origens:

- O consumo de eletricidade pode ser medido por metros que são instalados em diferentes áreas da empresa.
- As tabelas retêm as medições estatísticas. Por exemplo, a tabela HcmEmployment retém uma lista de todos os funcionários e os centros de custo nos quais eles trabalham.

| Nome       | Centro de custos |  descrição  | Tipo de trabalhador |
|------------|-------------|----|-------------|
| Funcionário A | CC001       | RH | Funcionário    |
| Funcionário B | CC002       | FI | Funcionário    |
| Funcionário C | CC002       | FI | Funcionário    |
| Funcionário D | CC003       | TE | Funcionário    |
| Funcionário F | CC003       | TE | Funcionário    |

> [!NOTE]
> Todas as tabelas que contêm dimensões financeiras podem ser usadas como fontes para medidas estatísticas.

A contabilização de custo suporta uma coleção de medições estatísticas usando as seguintes conexões de dados:

- Ferramenta de Importação/exportação do gerenciamento de dados
- Medidas estatísticas

Para obter as medições estatísticas do sistema, um modelo do provedor de medidas estatísticas é necessário. Para obter mais informações, consulte o modelo do provedor de medidas estatísticas. (Adicionará um link após este tópico ser gravado.)

**Modelos de provedor de medidas estatísticas**

| Nome  | Função | Tabela de origem  | Campo Soma      | Campo de data     |
|-------|----------|---------------|----------------|----------------|
| FTE | Contagem    | HcmEmployment | Não Aplicável | Não Aplicável |

Depois que os dados de origem estatísticos forem processados, as seguintes entradas serão criadas na Contabilidade de custos.

**Entradas de estatísticas**

| Objeto de custo | descrição      | Data contábil | Membro de dimensão estatística | descrição         | Magnitude |
|-------------|------------------|-----------------|------------------------------|---------------------|-----------|
| CC001       | RH               | 31/01/2017      | FTE                        | Funcionários em horário integral | 1.00      |
| CC002       | FI               | 31/01/2017      | FTE                        | Funcionários em horário integral | 2.00      |
| CC003       | TE               | 31/01/2017      | FTE                        | Funcionários em horário integral | 2.00      |

Aqui está um exemplo de uma regra de distribuição de custo se a base de alocação do membro de dimensão predefinida de FTE é atribuída como a base de alocação nela.

| Objeto de custo | descrição  | Magnitude | Fator de alocação |
|-------------|------|-----------|-------------------|
| CC001       | RH   | 1.00      | (1/5) × valor    |
| CC002       | FI   | 2.00      | (2/5) × valor    |
| CC003       | TE   | 2.00      | (2/5) × valor    |

Você pode usar a entidade de dados das medições estatísticas importadas para importar as medições estatísticas na contabilização de custo. Você também pode usar a ferramenta de importação/exportação de gerenciamento de dados. No Excel, o consumo de eletricidade é registrado como a seguir.

| Data contábil | Membro de dimensão | Magnitude | Identificador de origem |
|-----------------|------------------|-----------|-------------------|
| 31/01/2017      | CC001            | 2,450.00  | eletricidade       |
| 31/01/2017      | CC002            | 4,100.00  | eletricidade       |
| 31/01/2017      | CC003            | 15,000.00 | eletricidade       |

Depois que os dados de origem estatísticos forem processados, as seguintes entradas serão criadas na Contabilidade de custos.

**Entradas de estatísticas**

| Objeto de custo |    | Data contábil | Membro de dimensão estatística |    descrição          | Magnitude |
|-------------|----|-----------------|------------------------------|-------------------------|-----------|
| CC001       | RH | 31/01/2017      | eletricidade                  | Consumo de eletricidade | 2,450.00  |
| CC002       | FI | 31/01/2017      | eletricidade                  | Consumo de eletricidade | 4,100.00  |
| CC003       | TE | 31/01/2017      | eletricidade                  | Consumo de eletricidade | 15,000.00 |

Aqui está um exemplo de uma regra de distribuição de custo se a base de alocação do membro de dimensão predefinida de Eletricidade for atribuída como a base de alocação nela.

| Objeto de custo | descrição  | Magnitude | Fator de alocação          |
|-------------|------|-----------|----------------------------|
| CC001       | RH   | 2,450.00  | (2.450 ÷ 21.550) × valor  |
| CC002       | FI   | 4,100.00  | (4.100 ÷ 21.550) × valor  |
| CC003       | TE   | 15,000.00 | (15.000 ÷ 21.550) × valor |

## <a name="hierarchy-allocation-bases"></a>Bases de alocação de hierarquia

Os contadores de custo podem criar manualmente as bases de alocação de hierarquia aplicando um nó da hierarquia de dimensão do objeto de custo a uma base de alocação existente. Assim, você pode limitar a faixa de base de alocação do membro de dimensão predefinida original. Uma base de alocação do membro de dimensão predefinida pode ser usada para criar várias bases de alocação da hierarquia. Os intervalos podem ser mantidos na hierarquia de dimensão de objeto de custo associados às bases de alocação da hierarquia.

### <a name="example-hierarchy-allocation-bases-that-are-based-on-full-time-employees-in-the-organization"></a>Exemplo: Bases de alocação da hierarquia com base em funcionários em tempo integral na organização
Aqui está um exemplo de uma hierarquia de dimensões de objetos de custo que pode ser criada para descrever uma organização simplificada.

| Nome da hierarquia | Nó de nível 0 | Nó de nível 1 | Nó de nível 2 | Membros de dimensão |
|----------------|--------------|--------------|--------------|-------------------|
| Organização   | CEO          | CFO          | FICO         | CC001             |
| Organização   | CEO          | CFO          | RH           | CC002             |
| Organização   | CEO          | CIO          | TE           | CC003             |

A base de alocação do membro de dimensão predefinida do FTE criada em seção anterior retém as seguintes entradas.

**Entradas de estatísticas**

| Objeto de custo | descrição  | Data contábil | Membro de dimensão estatística | descrição | Magnitude |
|-------------|------|-----------------|------------------------------|---------------------|-----------|
| CC001       | RH   | 31/01/2017      | FTE                        | Funcionários em horário integral | 1.00      |
| CC002       | FI   | 31/01/2017      | FTE                        | Funcionários em horário integral | 2.00      |
| CC003       | TE   | 31/01/2017      | FTE                        | Funcionários em horário integral | 2.00      |

Um custo deve ser distribuído entre os centros de custo que se reportam ao diretor financeiro da organização. É confirmado que o índice de alocação correta é o número de funcionários em tempo integral (FTEs) por centro de custos.

**Bases de alocação de hierarquia**

| Nome                  | Base de alocação | Hierarquia da dimensão de objeto de custo | Nó de hierarquia da dimensão de objeto de custo |
|-----------------------|-----------------|---------------------------------|--------------------------------------|
| Número de FTEs no CFO | FTE           | Organização                    | CFO                                  |

Uma função de exibição permite validar a base de alocação da hierarquia criada, com base nas entradas estatísticas no sistema.

**Detalhes da base de alocação**

| Objeto de custo | descrição  |  Magnitude |
|-------------|------|------------|
| CC001       | RH   | 1.00       |
| CC002       | FI   | 2.00       |

Aqui está um exemplo de uma regra de distribuição de custo, se o Número de FTEs na base de alocação da hierarquia de CFO for atribuído como a base de alocação nela.

| Objeto de custo | descrição  | Magnitude | Fator de alocação |
|-------------|------|-----------|-------------------|
| CC001       | RH   | 1.00      | (1/3) × valor    |
| CC002       | FI   | 2.00      | (2/3) × valor    |

## <a name="formula-allocation-bases"></a>Bases de alocação de fórmulas

As bases de alocação da fórmula permitem definir fórmulas avançados para obter a base de alocação correta. Você pode criar manualmente bases de alocação da fórmula.

Quando você cria uma base de alocação da fórmula, você seleciona qual dimensão estatística e dimensão do elemento de custo deve ser a base da fórmula. Todas as bases de alocação que vêm dimensões anteriormente selecionadas podem ser usadas em uma base de alocação da fórmula.

> [!NOTE]
> As bases de alocação da fórmula definida anteriormente podem ser usadas para definir uma nova base de alocação da fórmula.

Em fatores de base de alocação da fórmula, você cria um apelido e o associa a uma base de alocação ou a uma constante. Os apelidos são usados para definir a fórmula.

Você pode usar os seguintes operadores para definir sua fórmula.

| Símbolos | Texto           |
|---------|----------------|
| ( )     | Parênteses    |
| \<      | Menor que   |
| \>      | Maior que    |
| +       | Adição       |
| –       | Subtração    |
| \*      | Multiplicação |

As instruções tradicionais **IF** não são suportadas. Porém, você pode criar instruções e validar se elas são verdadeiras.

| Demonstrativo | Validação | Resultado |
|-----------|------------|--------|
| a \> b    | Verdadeiro       | 1      |
| a \> b    | Falso      | 0      |

### <a name="example-1-a-simple-formula"></a>Exemplo 1: Uma fórmula simples

As contas de eletricidade geralmente consistem em duas partes:

- Uma taxa fixa a ser conectada à grade
- Um custo que associado ao consumo por kWh

A base de alocação do membro de dimensão predefinida de eletricidade já foi definida e mantém esses valores.

**Entradas de estatísticas**

| Objeto de custo | Nome | Data contábil | Membro de dimensão estatística | descrição             | Magnitude |
|-------------|------|-----------------|------------------------------|-------------------------|-----------|
| CC001       | RH   | 31/01/2017      | eletricidade                  | Consumo de eletricidade | 2,450.00  |
| CC002       | FI   | 31/01/2017      | eletricidade                  | Consumo de eletricidade | 4,100.00  |
| CC003       | TE   | 31/01/2017      | eletricidade                  | Consumo de eletricidade | 15,000.00 |

Se a taxa fixa tiver que ser difundida igualmente agora sobre objetos de custo que consomem a eletricidade, você tem duas opções para alocar os custos:

- Crie uma nova base de alocação predefinida, eletricidade fixa, e aplique uma medida estatística de 1.00 para cada objeto de custo que consumiu a eletricidade.
- Crie uma base de alocação da fórmula, a eletricidade fixa, que tem a vantagem da base de alocação predefinida de eletricidade que já foi definida no sistema. O benefício desta opção é que os dados devem ser carregados para a Contabilidade de custo somente para um membro de dimensão estatística de eletricidade.

**Base de alocação de fórmulas** 

| Nome              | Dimensão do elemento de custo | Dimensão estatística | Fórmula |
|-------------------|------------------------|-----------------------|---------|
| Eletricidade fixa |                        | Elementos estatísticos  |         |

Antes que o campo **Fórmula** seja preenchido, especifique o apelido que deve ser usado na fórmula.

**Fatores base de alocação de fórmula**

| Apelido | Constante | Base de alocação |
|-------|----------|-----------------|
| a     |          | eletricidade     |
| b     | 0.01     |                 |

Observe que 0 (zero) não será suportado como uma constante.

**Base de alocação de fórmulas**

| Nome              | Dimensão do elemento de custo | Dimensão estatística | Fórmula |
|-------------------|------------------------|-----------------------|---------|
| Eletricidade fixa |                        | Elementos estatísticos  | a \> b  |

Uma função de Visualização permite validar a base de alocação da fórmula criada, com base nas entradas estatísticas no sistema.

**Detalhes da base de alocação**

| Objeto de custo | descrição  | Fórmula           | Magnitude |
|-------------|------|-------------------|-----------|
| CC001       | RH   | 2.450,00 \> 0,01  | 1.00      |
| CC002       | FI   | 4.100,00 \> 0,01  | 1.00      |
| CC003       | TE   | 15.000,00 \> 0,01 | 1.00      |

Aqui está um exemplo de uma regra de distribuição de custo, se a base de alocação da fórmula Eletricidade for atribuída como a base de alocação nela.

**Fator de alocação de magnitude do objeto de custo**

| Objeto de custo | Nome | Magnitude |  Fator de alocação |
|-------------|------|-----------|--------------------|
| CC001       | RH   | 1.00      | (1/3) × valor     |
| CC002       | FI   | 1.00      | (1/3) × valor     |
| CC003       | TE   | 1.00      | (1/3) × valor     |

### <a name="example-2-an-advanced-formula"></a>Exemplo 2: Uma fórmula avançada
Para este exemplo, os custos de eletricidade não devem apenas seguir a eletricidade real que é consumida em kWh. O gerenciamento quer incorporar o incentivo para reduzir o uso da eletricidade. 

| Regra              | Taxa | 
|-------------------|------|
| a <= 10000.00 kWh | 0.75 |
| a > 10000.00 kWh  | 1.15 |

Uma nova base de alocação da fórmula, uso de eletricidade, foi criada.

**Base de alocação de fórmulas**

| Nome              | Dimensão do elemento de custo | Dimensão estatística | Fórmula |
|-------------------|------------------------|-----------------------|---------|
| Uso de eletricidade |                        | Elementos estatísticos  |         |

Antes que o campo **Fórmula** seja preenchido, especifique o apelido que deve ser usado na fórmula.

**Fatores base de alocação de fórmula**

| Apelido | Constante  | Base de alocação |
|-------|-----------|-----------------|
| a     |           | eletricidade     |
| b     | 10,000.00 |                 |
| c     | 0.75      |                 |
| d     | 1.15      |                 |

**Base de alocação de fórmulas**

| Nome              | Dimensão do elemento de custo | Dimensão estatística | Fórmula                                                    |
|-------------------|------------------------|-----------------------|------------------------------------------------------------|
| Eletricidade fixa |                        | Elementos estatísticos  | ((a \> b) × ((b × c) + (a – b) × d)) + ((a \<= b] × a × c) |

Uma função de Visualização permite validar a base de alocação da fórmula criada, com base nas entradas estatísticas no sistema.

**Detalhes da base de alocação**

| Objeto de custo |    | Fórmula                                                                                                                             | Magnitude |
|-------------|----|-------------------------------------------------------------------------------------------------------------------------------------|-----------|
| CC001       | RH | ((2.450,00 \> 10.000,00) × ((10.000,00 × 0,75) + (2.450,00 – 10.000,00) × 1,15)) + ((2.450,00 \<= 10.000,00) × 2.450,00 × 0,75)     | 1,837.50  |
| CC002       | FI | ((4.100,00 \> 10.000,00) × ((10.000,00 × 0,75) + (4.100,00 – 10.000,00) × 1,15)) + ((4.100,00 \<= 10.000,00) × 4.100,00 × 0,75)     | 3,075.00  |
| CC003       | TE | ((15.000,00 \> 10.000,00) × ((10.000,00 × 0,75) + (15.000,00 – 10.000,00) × 1,15)) + ((15.000,00 \<= 10.000,00) × 15.000,00 × 0,75) | 1,3250.00 |

Aqui está uma análise atenta da fórmula para CC003 (TI):

((15.000,00 \> 10.000,00) × ((10.000,00 × 0,75) + (15.000,00 – 10.000,00) × 1,15)) + ((15.000,00 \<= 10.000,00) × 15.000,00 × 0,75) = 13.250,00

(1 × (7.500,00 + 5.000,00 × 1,15)) + (0 × 15.000,00 × 0,75)            

1 × 7.500,00 + 5.750,00 + 0 

Aqui está um exemplo de uma regra de distribuição de custo, se a base de alocação da fórmula fixa Eletricidade for atribuída como a base de alocação nela.


| Objeto de custo | descrição | Magnitude |        Fator de alocação         |
|-------------|-------------|-----------|----------------------------------|
|    CC001    |     RH      | 1,837.50  | (1.837,50 ÷ 18.162,50) × valor  |
|    CC002    |     FI      | 3,075.00  | (3.075,00 ÷ 18.162,50) × valor  |
|    CC003    |     TE      | 13,250.00 | (13.250,00 ÷ 18.162,50) × valor |


