---
title: Política de acúmulo de custos e cálculo de custos indiretos
description: Este tópico fornece informações sobre como determinar o nível correto de elementos de custo secunDiários e criar regras de acúmulo de custo que se ajustem no relatório da organização e na rastreabilidade de custo.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostRollupRule, CAMDimensionHierarchy
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
ms.openlocfilehash: 1ecba97014d77c32855b5614c1feae8cbfab4cd5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176421"
---
# <a name="cost-rollup-policy-and-overhead-calculation"></a>Política de acúmulo de custos e cálculo de custos indiretos 

[!include [banner](../includes/banner.md)]

A contabilização de custos permite obter informações sobre como o fluxo de custo se relaciona os produtos e serviços fornecidos em uma organização. Para ver a transparência de custo, é importante obter a alocação de custo entre objetos de custo de acordo com uma base adequada à alocação. Por padrão, a alocação de custo é obtida para o elemento de custo previsto principal, que é desejado em algumas situações, mas há algumas implicações que devem ser consideradas.

-   Os objetos de custo auxiliares terminarão com saldo zero para o elemento de custo principal após o cálculo de custos indiretos.

-   O volume de entradas de custos geradas por cálculo de custos indiretos pode ser muito alto.

-   Não é possível rastrear o fluxo de custo entre objetos de custo.

Para evitar estas implicações, a contabilização de custos permite configurar a alocação de custo para ajustar-se nos requisitos de geração de relatórios gerenciais da organização. Este tópico discute como você pode determinar o nível correto de elementos de custo secunDiários e criar regras de acúmulo de custo que se ajustem no relatório da organização e na rastreabilidade de custo.

> [!NOTE]
> Você pode alterar as configurações, se os requisitos de relatórios forem alterados.

## <a name="example-of-cost-rollup-policy-setup"></a>Exemplo de configuração da política de acúmulo de custo

Suponha que uma organização tem a seguinte estrutura com 4 centros de custo.

![Exemplo de uma estrutura organizacional](./media/dimension-hierarchy-org.png)

**Dimensão de objeto de custo**

| Centros de custos | descrição          |
|--------------|-----------|
| CC001        | RH        |
| CC002        | Finanças   |
| CC003        | Montagem  |
| CC004        | Embalagem |

**Dimensão do elemento de custo**

| Elementos de custo | descrição | Tipo    |
|---------------|-------------|---------|
| 1001          | eletricidade | Principal |
| 1002          | Salários    | Principal |
| 1003          | Publicidade | Principal |

Uma hierarquia de dimensões que atende aos requisitos de relatórios da organização pode ser configurada como segue.

**Detalhes de hierarquias de dimensão**

| Nome de hierarquia de dimensões | Dimensão    | Nome do tipo de hierarquia de dimensões      | Acessar hierarquia de lista |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organização             | Centros de custos | Hierarquia de classificação de dimensões | Não                    |

**Hierarquia de dimensões**

|              | Intervalos de membros de dimensão |                     |
|--------------|-------------------------|---------------------|
| **Nós**        | **Membro da dimensão de origem**   | **Membro da dimensão de destino** |
| Organização |                         |                     |
| &nbsp;&nbsp;Administrador             |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanças              | CC001                   | CC001               |
| &nbsp;&nbsp;&nbsp;&nbsp;RH               | CC002                   | CC002               |
| &nbsp;&nbsp;Produção               |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Embalagem              | CC003                   | CC003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Montagem             | CC004                   | CC004               |

Uma hierarquia de dimensões que atende ao requisito de relatório pode ser configurada como segue.

**Detalhes de hierarquias de dimensão**

| Nome de hierarquia de dimensões | Dimensão     | Nome do tipo de hierarquia de dimensões      |
|--------------------------|---------------|------------------------------------|
| Demonstrativo de lucros e perdas  | Elementos de custo | Hierarquia de classificação de dimensões |

**Hierarquia de dimensões**

|                         | Intervalos de membros de dimensão |                     |
|-------------------------|-------------------------|---------------------|
| Nós                   | Membro da dimensão de origem   | Membro da dimensão de destino |
| Demonstrativo de lucros e perdas |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Custo primário                    | 10001                   | 10003               |

Depois que as entradas da contabilidade são processadas, o saldo de entrada de custo por objeto de custo parece com este.

|                      | **Objeto de custo** |           |           |           | **Total**     |
|----------------------|-----------------|-----------|-----------|-----------|---------------|
| **Elemento de custo**     | **CC001**       | **CC002** | **CC003** | **CC004** |               |
| **1001 Eletricidade** | 100,00          | 200.000    | 6.000,00  | 2.000,00  | **8.300,00**  |
| **1002 Salários**    | 10.000,00       | 10.000,00 | 8.000,00  | 6.500,00  | **34.500,00** |
| **1003 Publicidade** | 0,00            | 4.000,00  | 0,00      | 0,00      | **4.000,00**  |
|                      | 10.100,00       | 14.200,00 | 14.000,00 | 8.500,00  | **46.800,00** |

**Dimensão estatística**

| Elementos estatísticos |    descrição   |
|----------------------|------------------|
| SE-1                 | Serviços de RH      |
| SE-2                 | Serviços financeiros |

O objeto de custo CC001 HR está contribuindo com serviços a vários objetos de custo.

Os serviços de RH são consumidos pela seguinte distribuição de magnitude.

| Objeto de custo | descrição |   Serviços de RH |
|-------------|-------------|----|
| CC002       | Finanças     | 35 |
| CC003       | Montagem    | 55 |
| CC004       | Embalagem   | 10 |

O objeto de custo CC002 Finanças está contribuindo para vários objetos de custo.

Os serviços Financeiros são consumidos pela seguinte distribuição de magnitude.

| Objeto de custo |   descrição    |  Serviços financeiros   |
|-------------|------------------|----|
| CC003       | Montagem         | 65 |
| CC004       | Embalagem        | 35 |

As políticas de alocação de custo podem ser configuradas como segue.

| Nome da política | descrição     | Hierarquia da dimensão de objeto de custo | Dimensão estatística | Dimensão do elemento de custo |
|-------------|-----------------|---------------------------------|-----------------------|------------------------|
| 2017        | Alocação de custos | Organização                    | Elementos estatísticos  | Elementos de custo          |

As regras de alocação de custo podem ser configuradas como segue.

| Nó de hierarquia da dimensão de objeto de custo | Comportamento de custo | Base de alocação        |
|--------------------------------------|---------------|------------------------|
| CC001                                | Total         | **Serviços de RH**        |
| CC002                                | Total         | **Serviços financeiros** |

<a name="brhow-cost-flows-between-cost-centers"></a><br>Como o custo flui entre os centros de custo 
---------------------------------------------------

Se quiser aprender como o custo flui entre os centros de custos na organização, é possível criar elementos de custo do tipo **Secundário** para cada centro de custos. Esses elementos de custo serão usados depois para transferir saldos entre centros de custos durante o cálculo de custos indiretos.

Os membros da dimensão do elemento de custo podem ser configurados como segue.

| Elementos de custo | Tipo          |               |
|---------------|---------------|---------------|
| 1001          | eletricidade   | Principal       |
| 1002          | Salários      | Principal       |
| 1003          | Publicidade   | Principal       |
| **SC-CC001**  | **RH**        | **Secundário** |
| **SC-CC002**  | **Finanças**   | **Secundário** |
| **SC-CC003**  | **Montagem**  | **Secundário** |
| **SC-CC004**  | **Embalagem** | **Secundário** |

A hierarquia de dimensão **Demonstrativo de lucros e perdas** precisa ser atualizada com novas membros da dimensão de forma que a hierarquia de dimensões contenha os dados corretos que podem ser usados para definição do relatório e das políticas.

**Detalhes de hierarquias de dimensão**

| Nome de hierarquia de dimensões | Dimensão     | Nome do tipo de hierarquia de dimensões      |
|--------------------------|---------------|------------------------------------|
| Demonstrativo de lucros e perdas  | Elementos de custo | Hierarquia de classificação de dimensões |

**Hierarquia de dimensões**

|                         | Intervalos de membros de dimensão |                     |
|-------------------------|-------------------------|---------------------|
| Nós                   | Membro da dimensão de origem   | Membro da dimensão de destino |
| Demonstrativo de lucros e perdas |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Custo primário                        | 10001                   | 10003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Custo secundário                         | **SC-CC001**            | **SC-CC004**        |

Crie **Política de acúmulo de custo** na qual cada centro de custos é mapeado para um elemento de custo correspondente do tipo **Secundário**.

**Política de acúmulo de custo**

| Nome da política | descrição | Hierarquia da dimensão de objeto de custo | Hierarquia da dimensão de elemento de custo |
|-------------|-------------|---------------------------------|----------------------------------|
| 2017        | Fluxo de custo   | Organização                    | Demonstrativo de lucros e perdas          |

**Regras de acúmulo de custo**

| Nó de hierarquia da dimensão de objeto de custo | Nó de hierarquia da dimensão de elemento de custo | Elemento de custo secundário |
|--------------------------------------|---------------------------------------|------------------------|
| CC001                                | Demonstrativo de lucros e perdas               | **SC-CC001**           |
| CC002                                | Demonstrativo de lucros e perdas               | **SC-CC002**           |
| CC003                                | Demonstrativo de lucros e perdas               | **SC-CC003**           |
| CC004                                | Demonstrativo de lucros e perdas               | **SC-CC004**           |

## <a name="perform-overhead-calculation"></a>Executar cálculo de custos indiretos

**Diário**

| Diário | Tipo de diário            | Período do calendário fiscal | Ano | Período | Versão       |
|---------|-------------------------|------------------------|------|--------|---------------|
| 00002   | Diário de alocação de custos | fiscal                 | 2017    | Período 1 | Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1 |

O sistema então aplicará **Política de acúmulo de custo** quando criar as **Entradas de diário para saldo do objeto de custo**.

**Entradas de diário para saldo do objeto de custo**

| Data contábil | Objeto de custo | descrição  | Elemento de custo | descrição |  Valor |
|-----------------|-------------|--------------|----------|-----------|-----------|
| 31/01/2017      | CC001       | RH           | SC-CC001 | RH        | 10.100,00 |
| 31/01/2017      | CC002       | Finanças      | SC-CC002 | Finanças   | 17.735,00 |
| 31/01/2017      | CC003       | Montagem     | SC-CC003 | Montagem  | 31.082,75 |
| 31/01/2017      | CC004       | Embalagem    | SC-CC004 | Embalagem | 15.717,25 |

> [!NOTE]
> As entradas de diário são criadas com base nas regras **Política de acúmulo de custo** se existir uma política. O saldo exibido é o saldo de cálculo de custos indiretos.

A página **Detalhes da entrada de diário de saldo de custo do objeto de custo** que é acessada das entradas de diário exibe como o saldo é obtido.

**Exemplo: A entrada de diário para o objeto de custo CC002 Finanças**

**Detalhes da entrada de diário de saldo de custo do objeto de custo**

| Membro de dimensão do elemento de custo | descrição |  Valor   |
|-------------------------------|-------------|-----------|
| 1001                          | eletricidade | 200.000    |
| 1002                          | Salários    | 10.000,00 |
| 1003                          | Publicidade | 4.000,00  |
| SC-CC001                      | RH          | 3.535,00  |

**Entradas de custo geradas por cálculo de custos indiretos**

| Objeto de custo | descrição  | Elemento de custo   | descrição  |        Valor     |       Data contábil     |
|-------------|--------------|----------|-----------------|-------------|------------|
| CC001       | RH           | SC-CC001 | RH              | 10.100,00 de \- | 31/01/2017 |
| CC002       | Finanças      | SC-CC001 | RH              | 3.535,00    | 31/01/2017 |
| CC003       | Montagem     | SC-CC001 | RH              | 5.555,00    | 31/01/2017 |
| CC004       | Embalagem    | SC-CC001 | RH              | 1.010,00    | 31/01/2017 |
| CC002       | Finanças      | SC-CC002 | Finanças         | 17.735,00 de \- | 31/01/2017 |
| CC003       | Montagem     | SC-CC002 | Finanças         | 11.527,75   | 31/01/2017 |
| CC004       | Embalagem    | SC-CC002 | Finanças         | 6.207,25    | 31/01/2017 |

Depois que o **Cálculo de custos indiretos** for concluído, você poderá informar os resultados usando ferramentas como o Microsoft SharePoint Workspace, o Excel ou o Power BI.

## <a name="view-reporting-in-excel"></a>Exibir relatório no Excel 

As hierarquias da dimensão permitem que você exiba os dados em diferentes níveis de agregação.

Este é um exemplo de relatório do Power Pivot no Excel.

| **Demonstrativo de lucros e perdas** | **Objeto de custo** |                |               |               |  **Total**    |
|-----------------------------|-----------------|----------------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002**      | **CC003**     | **CC004**     |               |
| **Custo primário**            | **10.100,00**   | **14.200,00**  | **14.000,00** | **8.500,00**  | **46.800,00** |
| 1001 de &nbsp;&nbsp;&nbsp;&nbsp;                            | 100,00          | 200.000         | 6.000,00      | 2.000,00      | **8.300,00**  |
| 1002 de &nbsp;&nbsp;&nbsp;&nbsp;                            | 10.000,00       | 10.000,00      | 8.000,00      | 6.500,00      | **34.500,00** |
|1003 de &nbsp;&nbsp;&nbsp;&nbsp;                             | 0,00            | 4.000,00       | 0,00          | 0,00          | **4.000,00**  |
|**Custo secundário**                            | **-10.100,00**  | **-14.200,00** | **17.082.75** | **7.217,25**  | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC001                            | 10.100,00 de \-     | 3.535,00       | 5.555,00      | 1.010,00      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC002                             | 0,00            | 17.735,00 de \-    | 11.527,75     | 6.207,25      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC003                            | 0,00            | 0,00           | 0,00          | 0,00          | 0,00          |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC004                             | 0,00            | 0,00           | 0,00          | 0,00          | 0,00          |
| **Total**                   | **0,00**        | **0,00**       | **31.082,75** | **15.717,25** | **46.800,00** |

Usar **Política de acúmulo de custo** e **Elementos de custo previsto do tipo secundário** permite deixe o custo primário por objeto de custo para o relatório interno como custo primário que permanece após o **Cálculo de custos indiretos**.

Se o mesmo exemplo tinha sido executado sem criar a **Política de acúmulo de custo,** o resultado do relatório seria como o mostrado a seguir. O custo flui corretamente, mas a rastreabilidade e as informações sobre como o custo flui entre os centros de custos são perdidas.

| **Demonstrativo de lucros e perdas** | **Objeto de custo** |           |               |               |          **Total**  |
|-----------------------------|-----------------|-----------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002** | **CC003**     | **CC004**     |               |
| **Custo primário**            | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |
|1001 de &nbsp;&nbsp;&nbsp;&nbsp;                              | 0,00            | 0,00      | 6.207,75      | 2.092,25      | **8.300,00**  |
| 1002 de &nbsp;&nbsp;&nbsp;&nbsp;                             | 0,00            | 0,00      | 22.275,00     | 12.225,00     | **34.500,00** |
|1003 de &nbsp;&nbsp;&nbsp;&nbsp;                              | 0,00            | 0,00      | 2600,00       | 1.400,00      | **4.000,00**  |
|**Custo secundário**                            | **0,00**        | **0,00**  | **0,00**      | **0,00**      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC001                             | 0,00            | 0,00      | 0,00          | 0,00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC002                             | 0,00            | 0,00      | 0,00          | 0,00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC003                             | 0,00            | 0,00      | 0,00          | 0,00          | 0,00          |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC004                             | 0,00            | 0,00      | 0,00          | 0,00          | 0,00          |
| **Total**                   | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |

Dependendo dos requisitos de relatório e rastreabilidade de sua organização, você pode determinar o nível correto de elementos de custo secunDiários e criar regras de acúmulo de custo, de acordo com suas necessidades.

A separação clara entre **Alocação de custo** e **Políticas de acúmulo de custo** fornece a flexibilidade para fazer atualizações contínuas sem se afetarem.



## <a name="additional-resources"></a>Recursos adicionais
-  [Dimensões de objeto de custo](cost-objects.md)
-  [Dimensões do elemento de custo](cost-elements.md)
-  [Hierarquias de dimensões](dimension-hierarchy.md)
-  [Cálculo de custos indiretos](overhead-calculation.md)
