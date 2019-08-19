---
title: Membros estatísticos de dimensões e modelos de fornecedores de medições estatísticas
description: Este tópico fornece informações sobre membros da dimensão estatística e modelos de provedores de medidas estatísticas. Os membros da dimensão estatística podem ser utilizados como base de alocação em políticas como distribuição de custos e alocação de custos. Eles também podem ser usados ​​para relatar o consumo de custos não monetários.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerSourceEntryProvider, CAMStatisticalDimension, CAMAXStatisticalMeasureProviderTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 15c4ca5284121e1b384111f10e2d4cb06a5c7575
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841456"
---
# <a name="statistical-dimension-members-and-statistical-measure-provider-templates"></a>Membros estatísticos de dimensões e modelos de fornecedores de medições estatísticas

[!include [banner](../includes/banner.md)]

Uma dimensão estatística e seus membros são usados ​​para registrar e controlar entradas não monetárias na contabilidade de custos. Os membros da dimensão estatística podem ser utilizados para duas finalidades:

- Como base de alocação em políticas como distribuição de custos ou alocação de custos
- Para relatar o consumo não monetário

## <a name="statistical-dimension"></a>Dimensão estatística

Uma dimensão estatística tem um nome exclusivo e um conjunto de membros de dimensão única. A dimensão estatística é atribuída a uma identificação contábil de cálculo de custos. Esta relação vincula todos os membros de dimensão estatística correspondentes ao livro de contabilidade de custos. Portanto, todas as entradas estatísticas serão criadas no contexto do livro de contabilidade de custos.

> [!NOTE]
> Uma dimensão estatística pode ser atribuída a mais de um contabilidade contábil de custo.

Veja aqui um exemplo de uma dimensão estatística.

| Nome                        | Conector de dados para membros de dimensões |
|-----------------------------|--------------------------------------|
| Elementos estatísticos compartilhados | Membros de dimensão importados           |

Veja aqui um exemplo de uma dimensão estatística que foi atribuída a um livro de contabilidade de custos.

| Nome                  | Moeda contábil | Tipo de taxa de câmbio | Calendário fiscal | Dimensão do elemento de custo | Dimensão estatística       |
|-----------------------|---------------------|--------------------|-----------------|------------------------|-----------------------------|
| Contabilidade gerencial | USD                 | Moeda constante  | Período fiscal   | Elementos de custo compartilhado   | Elementos estatísticos compartilhados |

## <a name="statistical-dimension-members"></a>Membros de dimensão estatística

Um membro de dimensão estatística representa uma entidade para a qual você deseja registrar medidas não monetárias. Essas medidas podem ser usadas como base de alocação ou apenas para relatar valores não monetários.

Os membros da dimensão estatística podem ser criados manualmente. Alternativamente, eles podem ser importados de um arquivo usando a ferramenta de importação/exportação de gerenciamento de dados.

Um membro de dimensão estatística torna-se automaticamente uma base de alocação predefinida. Ele pode ser usado como uma base de alocação em políticas ou como entrada em outros tipos de bases de alocação.

Aqui estão alguns exemplos de membros típicos da dimensão estatística.

| Nome da dimensão estatística  | Elementos estatísticos | descrição             | Unidade |
|-----------------------------|----------------------|-------------------------|------|
| Elementos estatísticos compartilhados | FTE                  | Funcionários em horário integral     | Cada  |
| Elementos estatísticos compartilhados | eletricidade          | Consumo de eletricidade | kWh  |
| Elementos estatísticos compartilhados | CC de blocos              | Centro de custo de embalagem   | Hrs. |

## <a name="statistical-measure-provider-template"></a>Modelo de provedor de medidas estatísticas

As medidas estatísticas podem ser originárias de vários tipos de fontes. O Microsoft Dynamics 365 for Finance and Operations é uma grande fonte de extração de estatísticas de medição. Você pode usar um modelo de provador de medidas estatísticas para configurar facilmente as medidas estatísticas que deseja extrair.

A definição de modelo de fornecedor de medida estatística é genérica e pode ser reutilizada em vários membros de dimensão estatística.

> [!NOTE]
> Todas as tabelas que contêm dimensões financeiras podem ser usadas como fontes para medidas estatísticas.

**Exemplo: Contagem dos funcionários por centro de custos**

A contagem de funcionários por centro de custo é uma medida estatística que pode ser usada para vários fins que fornecem informações administrativas:

- Uma medida de relatório estatístico por centro de custo
- Uma base de alocação para vários tipos de despesas
- Taxas de custo interno pelo centro de custo:

    - Custo por funcionário
    - Receita por funcionário

A tabela HcmEmployment contém uma lista de todos os funcionários na instância. Esta tabela é uma tabela global. Portanto, os registros não estão relacionados a uma identificação de área de dados específica.

Aqui está um exemplo de funcionários na tabela HcmEmployment.

| Nome       | Centro de custos | descrição   | Tipo de trabalhador |
|------------|-------------|----|-------------|
| Funcionário 1 | CC001       | RH | Funcionário    |
| Funcionário 2 | CC002       | FI | Funcionário    |
| Funcionário 3 | CC002       | FI | Funcionário    |
| Funcionário 4 | CC003       | TE | Funcionário    |
| Funcionário 5 | CC003       | TE | Funcionário    |
| Funcionário 6 | CC002       | FI | Prestador de Serviço  |

Ao criar uma registro **Medição estatísticas do fornecedor**, você deve decidir qual função usar:

- **Contagem** – Uma contagem de registros por objeto de custo previsto é transferida.
- **Soma** – Uma soma dos registros por objeto de custo previsto é transferida. (O campo **Soma** e **Data** são necessários.)

## <a name="using-the-count-function"></a>Usando a função de contagem

Por exemplo, uma medida estatística do fornecedor pode ser configurada da seguinte forma.

| Nome  | Função | Tabela de origem  | Campo Soma      | Campo de data     |
|-------|----------|---------------|----------------|----------------|
| FTEs  | Contagem    | HcmEmployment | Não Aplicável | Não Aplicável |

Você também pode adicionar um ou vários intervalos para refinar as medidas da tabela de origem.

Neste exemplo, se você quiser apenas uma contagem de todos os funcionários em tempo integral (FTEs), você pode adicionar um intervalo no campo **Tipo de trabalho**. No campo **Critérios**, selecione **Funcionário** para delimitar as saídas conforme a seguir.

**Intervalos**

| Tabela de origem  | Campo       | Critérios |
|---------------|-------------|----------|
| HcmEmployment | Tipo de trabalhador | Funcionário |

Antes de poder obter medidas estatísticas em Contabilidade de custos, você deve estabelecer a relação entre o modelo do provedor de medidas estatísticas e o membro da dimensão estatística. Esta relação é criada por Razão e versão de contabilidade de custos. A relação consiste em um conector de dados e um provedor de dados. Você pode ter vários conectores de dados e provedores de dados por membro de dimensão estatística.

> [!NOTE]
> Neste exemplo, criaremos uma relação apenas para **Versão atual**.

Vá para **Razão da contabilização de custo** \> **Versão atual** \> **Gerenciar** \> **Medidas estatísticas** para estabelecer a relação. Para esse cenário, selecione o conector de dados **Dynamics 365 for Finance and Operations - Medidas estatísticas**, pois desejamos extrair dados do Finance and Operations.

**Fonte de dados**

| Nome        | Conector de dados                                                                     | Membro de dimensão estatística |
|-------------|------------------------------------------------------------------------------------|------------------------------|
| FTEs D365FO | Dynamics 365 for Finance and Operations - Medidas estatísticas | FTEs                         |

**Configuração do provedor de dados**

| Nome do modelo estatístico |
|---------------------------|
| FTEs                      |

Depois que os dados de origem para a medida estatística forem processados, as seguintes entradas estatísticas serão criadas em Contabilidade de custos.

**Diário**

| Diário | Tipo de diário                       | Período do calendário fiscal | Ano   |  Período  |  Versão | Entradas de origem do conector de dados|
|---------|------------------------------------|------------------------|--------|----------|----------|------------------------------|
| 00001   | Diário de transferência de entradas de estatísticas | fiscal                 | 2017   | Período 1 | CA razão USMF | FTEs                   |

**Entradas de diários de transferência de entradas de estatísticas**

| Data contábil | Magnitude | Elemento estatístico |   descrição       | Centro de custos |
|-----------------|-----------|---------------------|---------------------|-------------|
| 31/01/2017      | 1.00      | FTEs                | Funcionários em horário integral | CC001       |
| 31/01/2017      | 2.00      | FTEs                | Funcionários em horário integral | CC002       |
| 31/01/2017      | 2.00      | FTEs                | Funcionários em horário integral | CC003       |

**Entradas estatísticas**

| Objeto de custo |    | Data contábil | Membro de dimensão estatística |  descrição        | Magnitude |
|-------------|----|-----------------|------------------------------|---------------------|-----------|
| CC001       | RH | 31/01/2017      | FTEs                         | Funcionários em horário integral | 1.00      |
| CC002       | FI | 31/01/2017      | FTEs                         | Funcionários em horário integral | 2.00      |
| CC003       | TE | 31/01/2017      | FTEs                         | Funcionários em horário integral | 2.00      |

Se a base de atribuição de membros de dimensão predefinida do FTE for atribuída como uma base de alocação em uma regra de distribuição de custos, o custo será distribuído usando o seguinte fator de alocação.

| Objeto de custo | descrição    | Magnitude | Fator de alocação |
|-------------|----|-----------|-------------------|
| CC001       | RH | 1.00      | (1/5) × valor    |
| CC002       | FI | 2.00      | (2/5) × valor    |
| CC003       | TE | 2.00      | (2/5) × valor    |

## <a name="using-the-sum-function"></a>Usando a função de soma

Um centro de custo de produção, CC010 (Embalagem), é responsável pela embalagem dos produtos antes de serem enviados aos clientes. O custo direto da mão-de-obra é adicionado aos produtos através da lista de materiais (BOM) e rota. O custo indireto da execução do centro de custo também deve ser alocado aos produtos produzidos. Muitas vezes, a melhor medida estatística para tal alocação é o número de horas de produção registradas por produto dentro do período determinado.

A tabela ProdRouteTrans mantém todas as transações trabalhistas de produção por entidade legal DataAreadID.

Veja aqui um exemplo da tabela ProdRouteTrans.

| Demonstrativo        | Número | Operação | Tipo | Hora  | Data física | Grupo de produtos (dimensão financeira) | Pessoa jurídica em geral |
|------------------|--------|-----------|------|-------|---------------|-------------------------------------|--------------|
| Ordem de Produção | P0001  | Embalagem | Hora | 8,00  | 01/01/2017    | Suco laranja B2B                    | USMF         |
| Ordem de Produção | P0001  | Embalagem | Hora | 8,00  | 02/01/2017    | Suco laranja B2B                    | USMF         |
| Ordem de Produção | P0002  | Embalagem | Hora | 4,00  | 03/01/2017    | Consumo de suco de laranja               | USMF         |
| Ordem de Produção | P0003  | Embalagem | Hora | 4,00  | 03/01/2017    | Consumo de suco de laranja               | USMF         |
| Ordem de Produção | P0004  | Reconst.  | Hora | 10,00 | 03/01/2017    | Consumo de suco de laranja               | USMF         |

Ao criar uma registro **Medição estatísticas do fornecedor**, você deve decidir qual função usar:

- **Contagem** – Uma contagem de registros por objeto de custo previsto é transferida.
- **Soma** – Uma soma dos registros por objeto de custo previsto é transferida. (O campo **Soma** e **Data** são necessários.)

O modelo de fornecedor de medida estatística pode ser configurada da seguinte forma.

| Nome    | Função | Tabela de origem   | Campo Soma | Campo de data    |
|---------|----------|----------------|-----------|---------------|
| CC de blocos | Soma      | ProdRouteTrans | Horas     | Data física |

Você também pode adicionar intervalos para reduzir as medidas da tabela de origem.

Neste exemplo, se você quiser apenas a soma de horas relacionadas ao centro de custo da embalagem CC010, você pode adicionar um intervalo no campo **Operação**. No campo **Critérios**, selecione **Embalagem** para delimitar o intervalo de saídas.

**Intervalos**

| Tabela de origem   | Campo     | Critérios  |
|----------------|-----------|-----------|
| ProdRouteTrans | Operação | Embalagem |

Antes de poder obter medidas estatísticas em Contabilidade de custos, você deve estabelecer a relação entre o modelo do provedor de medidas estatísticas e o membro da dimensão estatística. Esta relação é criada por Razão e versão de contabilidade de custos. A relação consiste em um conector de dados e um provedor de dados. Você pode ter vários conectores de dados e provedores de dados por membro de dimensão estatística.

> [!NOTE]
> Neste exemplo, criaremos uma relação apenas para **Versão atual**.

Vá para **Razão da contabilização de custo** \> **Versão atual** \> **Gerenciar** \> **Medidas estatísticas** para estabelecer a relação. Para esse cenário, selecione o conector de dados **Dynamics 365 for Finance and Operations - Medidas estatísticas**, pois desejamos extrair dados do Finance and Operations.

**Fonte de dados**

| Nome           | Conector de dados                                                                     | Membro de dimensão estatística |
|----------------|------------------------------------------------------------------------------------|------------------------------|
| Pacote CC D365FO | Dynamics 365 for Finance and Operations - Medidas estatísticas | Pacote CC                      |

O sistema reconhece que ProdRouteTrans é uma tabela em que cada registro pertence a uma entidade legal separada. Portanto, você será solicitado a selecionar a entidade legal de onde as transações devem ser importadas.

**Configuração do provedor de dados**

| Nome do modelo estatístico | Pessoa jurídica em geral |
|---------------------------|--------------|
| Pacote CC                   | USMF         |

Depois que os dados de origem para a medida estatística forem processados, as seguintes entradas estatísticas serão criadas em Contabilidade de custos.

**Diário**

| Diário | Tipo de diário                     | Período do calendário fiscal | Ano   | Período | Versão   |   Entradas de origem do conector de dados  |
|---------|----------------------------------|------------------------|--------|---------|----------------|---------|
| 00002   | Diário de transferência de entradas de estatísticas | fiscal               | 2017    | Período 1  | CA razão USMF | Pacote CC |

**Entradas de diários de transferência de entradas de estatísticas**

| Data contábil | Magnitude | Elemento estatístico |  descrição          | Grupo de produtos         |
|-----------------|-----------|---------------------|-----------------------|-----------------------|
| 31/01/2017      | 16,00     | Pacote CC             | Centro de custo de embalagem | Suco laranja B2B      |
| 31/01/2017      | 8,00      | Pacote CC             | Centro de custo de embalagem | Consumo de suco de laranja |

**Entradas de estatísticas**

| Objeto de custo           | Data contábil | Membro de dimensão estatística |    descrição        | Magnitude |
|-----------------------|-----------------|------------------------------|-----------------------|-----------|
| Suco laranja B2B      | 31/01/2017      | Pacote CC                      | Centro de custo de embalagem | 16,00     |
| Consumo de suco de laranja | 31/01/2017      | Pacote CC                      | Centro de custo de embalagem | 8,00      |

Se a base de atribuição de membros de dimensão predefinida do pacote CC for atribuída como uma base de alocação em uma regra de distribuição de custos, o custo será distribuído usando o seguinte fator de alocação.

| Objeto de custo           | Magnitude | Fator de alocação  |
|-----------------------|-----------|--------------------|
| Suco laranja B2B      | 16,00     | (16 ÷ 24) × valor |
| Consumo de suco de laranja | 8,00      | (8 ÷ 24) × valor  |

## <a name="imported-statistical-measures"></a>Medidas estatísticas importadas

Você pode importar medidas estatísticas em Contabilidade de custos usando a ferramenta de importação/exportação de gerenciamento de dados.

A entidade de dados que é usada para a importação é chamada de medidas estatísticas importadas.

> [!NOTE]
> Essa entidade de dados foi projetada para permitir um máximo de cinco valores de dimensão exclusivos por entrada.

O consumo de eletricidade é registrado no Microsoft Excel usando o formato predefinido da entidade de dados. Veja aqui um exemplo.

| Data contábil | Nome do membro da dimensão 1 | Nome do membro da dimensão 2 | Nome do membro da dimensão 5 | Magnitude  | Identificador de origem |
|-----------------|------------------------|------------------------|------------------------|------------|-------------------|
| 31/01/2017      | CC001                  |                        |                        | 2,450.00   | eletricidade       |
| 31/01/2017      | CC002                  |                        |                        | 4,100.00   | eletricidade       |
| 31/01/2017      | CC003                  |                        |                        | 15,000.00  | eletricidade       |

Se você importou seus dados através do gerenciamento de dados, os dados serão armazenados em uma tabela de teste de contabilidade de custos. Portanto, os dados importados podem ser usados em múltiplos livros de contabilidade. Não é necessário recarregar os dados.

Para importar dados, vá para **Dados importados** \> **Entidade de dados** \> **Medidas estatísticas importadas**.

| Identificador de origem | Data contábil | Magnitude  | Nome do membro da dimensão 1 | Nome do membro da dimensão 2 | Nome do membro da dimensão 5 |
|-------------------|-----------------|------------|------------------------|------------------------|------------------------|
| eletricidade       | 31/01/2017      | 2,450.00   | CC001                  |                        |                        |
| eletricidade       | 31/01/2017      | 4,100.00   | CC002                  |                        |                        |
| eletricidade       | 31/01/2017      | 15,000.00  | CC003                  |                        |                        |

Antes de poder obter medidas estatísticas em Contabilidade de custos, você deve estabelecer a relação entre o identificador de origem e o membro da dimensão estatística. Esta relação é criada por Razão e versão de contabilidade de custos. A relação consiste em um conector de dados e um provedor de dados. Você pode ter vários conectores de dados e provedores de dados por membro de dimensão estatística.

> [!NOTE]
> Neste exemplo, criaremos uma relação apenas para **Versão atual**.

Vá para **Razão da contabilização de custo** \> **Versão atual** \> **Gerenciar** \> **Medidas estatísticas** para estabelecer a relação. Para este cenário, selecione o conector de dados **Medidas estatísticas importadas**, porque os dados foram importados de um sistema de terceiros para a contabilidade de custos via Excel.

**Origem de dados**

| Nome        | Conector de dados                | Membro de dimensão estatística |
|-------------|-------------------------------|------------------------------|
| eletricidade | Medidas estatísticas importadas | eletricidade                  |

**Configuração do provedor de dados**

| Importar identificador de origem | Função | Dimensão 1   | Dimensão 2 | Dimensão 5 |
|--------------------------|----------|--------------|------------|------------|
| eletricidade              | Soma      | Centros de custos |            |            |

> [!NOTE]
> Quando você definir a configuração do provedor de dados, você deve especificar quais as dimensões do objeto de custo para corresponder às transações importadas. Depois que os dados de origem para a medida estatística forem processados, as seguintes entradas estatísticas serão criadas em Contabilidade de custos.

**Diário**

| Diário | Tipo de diário                       | Período do calendário fiscal | Ano  | Perid  |Versão      |Entradas de origem do conector de dados |
|---------|------------------------------------|------------------------|-------|--------|---------------|-------------|
| 00002   | Diário de transferência de entradas de estatísticas | fiscal                 | 2017  | Período 1 | CA razão USMF | eletricidade |

**Entradas de diários de transferência de entradas de estatísticas**

| Data contábil | Magnitude  | Elemento de custo |   descrição           | Centro de custos |
|-----------------|------------|--------------|-------------------------|-------------|
| 31/01/2017      | 2,450.00   | eletricidade  | Consumo de eletricidade | CC001       |
| 31/01/2017      | 4,100.00   | eletricidade  | Consumo de eletricidade | CC002       |
| 31/01/2017      | 15,000.00  | eletricidade  | Consumo de eletricidade | CC003       |

**Entradas estatísticas**

| Objeto de custo |    | Data contábil | Membro de dimensão estatística |      descrição                   | Magnitude  |
|-------------|----|-----------------|------------------------------|-------------------------|------------|
| CC001       | RH | 31/01/2017      | eletricidade                  | Consumo de eletricidade | 2,450.00   |
| CC002       | FI | 31/01/2017      | eletricidade                  | Consumo de eletricidade | 4,100.00   |
| CC003       | TE | 31/01/2017      | eletricidade                  | Consumo de eletricidade | 15,000.00  |

Se a base de atribuição de membros de dimensão predefinida de eletricidade for atribuída como uma base de alocação em uma regra de distribuição de custos, o custo será distribuído usando o seguinte fator de alocação.

| Objeto de custo |    | Magnitude | Fator de alocação          |
|-------------|----|-----------|----------------------------|
| CC001       | RH | 2,450.00  | (2.450 ÷ 21.550) × valor  |
| CC002       | FI | 4,100.00  | (4.100 ÷ 21.550) × valor  |
| CC003       | TE | 15,000.00 | (15.000 ÷ 21.550) × valor |

## <a name="additional-resources"></a>Recursos adicionais

[Bases de alocação](allocation-bases.md)
