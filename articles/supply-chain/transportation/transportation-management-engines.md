---
title: Mecanismos de gerenciamento de transporte
description: Os mecanismos de gerenciamento de transporte definem a lógica usada para gerar e processar taxas de transporte no Gerenciamento de transporte.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSGenericEngine, TMSMileageEngine, TMSRateEngine, TMSTransitTimeEngine, TMSZoneEngine
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dff811723e25952b4c5af20262010ff4b910be7f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553990"
---
# <a name="transportation-management-engines"></a>Mecanismos de gerenciamento de transporte

[!include [banner](../includes/banner.md)]

Os mecanismos de gerenciamento de transporte definem a lógica usada para gerar e processar taxas de transporte no Gerenciamento de transporte. 

Um mecanismo de gerenciamento de transporte calcula tarefas, como a taxa de transporte da transportadora. O sistema do mecanismo permite alterar as estratégias de cálculo no tempo de execução com base nos dados no Microsoft Dynamics 365 for Finance and Operations. Um mecanismo de gerenciamento de transporte é semelhante a um plug-in relacionado a um contrato de transportadora específico.

## <a name="what-engines-are-available"></a>Quais mecanismos estão disponíveis?
A tabela a seguir mostra os mecanismos de gerenciamento de transporte disponíveis no Microsoft Dynamics 365 for Finance and Operations.

| Mecanismo de gerenciamento de transporte | descrição                                                                                                                                                                                                                                                                                                                 |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mecanismo de taxa**                  | Calcula taxas.                                                                                                                                                                                                                                                                                                           |
| **Mecanismo genérico**               | Mecanismos simples auxiliares usados por outros mecanismos que não requerem dados do Microsoft Dynamics 365 for Finance and Operations, por exemplo, um mecanismo de divisão. Os mecanismos de divisão são usados para reduzir o custo final do transporte de ordens e linhas específicas, com base nas dimensões, como volume e peso. |
| **Mecanismo de quilometragem**               | Calcula a distância do transporte.                                                                                                                                                                                                                                                                                     |
| **Mecanismo de tempo em trânsito**          | Calcula o tempo necessário para viajar do início até o destino.                                                                                                                                                                                                                                       |
| **Mecanismo de zona**                  | Calcula a zona com base no endereço atual e calcula o número de zonas que devem ser cruzadas para viajar do endereço A ao endereço B.                                                                                                                                                                    |
| **Tipo de nota de frete**            | Padroniza a fatura de frete e as linhas da nota de frete, e é usado para correspondência automática de nota de frete.                                                                                                                                                                                                                |


<a name="what-engines-must-be-configured-to-rate-a-shipment"></a>Quais mecanismos devem ser configurados para avaliar uma remessa?
---------------------------------------------------

Para avaliar uma remessa usando uma transportadora específica, você deve configurar vários mecanismos de gerenciamento de transporte. O **Mecanismo de taxa** é obrigatório, mas outros mecanismos de gerenciamento de transporte podem ser necessários para oferecer suporte ao **Mecanismo de taxa**. Por exemplo, o **Mecanismo de taxa** pode ser usado para recuperar dados do **Mecanismo de quilometragem** para calcular a taxa com base na quilometragem entre a origem e o destino.

## <a name="whats-required-to-initialize-a-transportation-management-engine"></a>O que é necessário para inicializar um mecanismo de gerenciamento de transporte?
Um mecanismo de gerenciamento de transporte exige que você configure os dados de inicialização para que funcionem de uma maneira específica. A configuração pode incluir os seguintes tipos de dados:
-   Referências a outros mecanismos de gerenciamento de transporte. Para obter detalhes, consulte o exemplo de configuração nesta seção.
-   Referências aos tipos do .NET que são usados pelo mecanismo de gerenciamento de transporte.
-   Dados simples da configuração.

Na maioria dos casos, você pode clicar no botão **Parâmetros** nos formulários de configuração do mecanismo de gerenciamento de transporte para configurar os dados de inicialização. **Exemplo de configuração de um mecanismo de taxa que faz referência a um mecanismo de quilometragem** O exemplo a seguir mostra a configuração necessária para um mecanismo de taxa com base no tipo de mecanismo .NET Microsoft.Dynamics.Ax.Tms.Bll.MileageRateEngine e as referências a um mecanismo de quilometragem.

|          Parâmetro           |                                                                                  Descrição                                                                                  |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <em>RateBaseAssigner</em>   | O tipo do .NET que interpretará os dados da atribuição de base da taxa para um esquema específico. A sintaxe do valor de parâmetro consiste em dois segmentos limitados por uma barra vertical ( |
|  <em>MileageEngineCode</em>  |                       Código do mecanismo de quilometragem que identifica o registro do mecanismo de quilometragem no banco de dados do Microsoft Dynamics 365 for Finance and Operations.                        |
| <em>ApportionmentEngine</em> |                        Código do mecanismo genérico que identifica um mecanismo de divisão no banco de dados do Microsoft Dynamics 365 for Finance and Operations.                        |

<a name="how-is-metadata-used-in-transportation-management-engines"></a>Como os metadados são usados nos mecanismos de gerenciamento de transporte?
----------------------------------------------------------

Os mecanismos de gerenciamento de transporte que dependem dos dados definidos no Dynamics 365 for Finance and Operations podem usar diferentes esquemas de dados. O sistema de gerenciamento de transporte permite que diferentes mecanismos de gerenciamento de transporte usem as mesmas tabelas físicas genéricas de banco de dados. Para verificar se a interpretação de tempo de execução dos dados do mecanismo está correta, você pode definir metadados para as tabelas de banco de dados. Isso reduz os custos de criação de novos mecanismos de gerenciamento de transporte, uma vez que tabelas e estruturas de formulário adicionais não são necessárias no Operations.

## <a name="what-can-be-used-as-search-data-in-rate-calculations"></a>O que pode ser usado como dado de pesquisa nos cálculos de taxa?
Os dados que você usa para as calcular taxas no Microsoft Dynamics 365 for Finance and Operations são controlados pela configuração de metadados. Por exemplo, se você deseja pesquisar por taxas com base no CEP, é necessário configurar os metadados com base no tipo de pesquisa de um CEP.

## <a name="do-all-engine-configurations-require-metadata"></a>Todas as configurações do mecanismo exigem metadados?
Não, os mecanismos de gerenciamento de transporte usados para recuperar os dados necessários para o cálculo da taxa de sistemas externos não necessitam de metadados. Os dados de taxa desses mecanismos podem ser recuperados de sistemas de transporte de transportadoras externas, geralmente com um serviço da Web. Por exemplo, você pode usar um mecanismo de quilometragem que recupera dados diretamente dos mapas do Bing, de forma que não precise de metadados para este mecanismo.

| **Nota**                                                                                                                                                                                                                                                                                                                                                                     |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Os mecanismos de gerenciamento de transporte fornecidos com o para Finanças e Operações dependem dos dados que são recuperados pelo aplicativo. Os mecanismos que se conectam a sistemas externos não são incluídos no Operations. No entanto, o modelo de extensibilidade baseado em mecanismo permite criar extensões usando ferramentas do Microsoft Dynamics 365 for Finance and Operations Visual Studio. |

## <a name="how-do-i-configure-metadata-for-a-transportation-management-engine"></a>Como configurar metadados para um mecanismo de gerenciamento de transporte?
Os metadados para os mecanismos de gerenciamento de transporte são configurados de forma diferente para os diferentes tipos de mecanismos.

| Mecanismo de gerenciamento de transporte               | Configuração dos metadados                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mecanismo de taxa**                                | Exige um **Tipo base da taxa**. O tipo de base da taxa contém os metadados para os dados de base da taxa e os dados de atribuição da base da taxa. A estrutura dos metadados de base da taxa é determinada pelo tipo de mecanismo da taxa. A estrutura dos metadados de atribuição da base da taxa é determinada pelo tipo de atribuidor de base da taxa associado ao mecanismo de taxa. Você configura o tipo base da taxa de um mecanismo de taxa na página **Mecanismo de taxa** e na página **Mestre de taxa**. |
| **Mecanismo de zona**                                | Requer que os metadados sejam configurados diretamente na zona mestre.                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Mecanismo de tempo em trânsito** e **Mecanismo de quilometragem** | Recupera os metadados diretamente do formulário de configuração do mecanismo de quilometragem.                                                                                                                                                                                                                                                                                                                                                                                  |

  **Exemplo de metadados para um mecanismo de taxa** O mecanismo de gerenciamento de transporte requer a identificação do endereço de origem, destino do estado e o país/região, e a hora inicial e a empresa de remessa. Usando esses requisitos, os metadados se pareceriam com os dados na tabela a seguir. A tabela também inclui informações sobre qual tipo de dados de entrada é necessário.
-   Defina esta informação em **Gerenciamento de transporte** &gt; **Configuração** na página **Tipo base da taxa**.

| Seqüência | Nome                          | Tipo de Campo | Tipo de dados | Tipo de pesquisa    | Obrigatório |
|----------|-------------------------------|------------|-----------|----------------|-----------|
| 1        | CEP de origem            | Atribuição | Cadeia de caracteres    | CEP    | Selecionada  |
| 2        | Estado de destino             | Atribuição | Cadeia de caracteres    | Estadual          |           |
| 3        | CEP de destino | Atribuição | Cadeia de caracteres    | CEP    | Selecionada  |
| 4        | CEP final de destino   | Atribuição | Cadeia de caracteres    | CEP    | Selecionada  |
| 5        | País/região de destino           | Atribuição | Cadeia de caracteres    | País/região |           |





