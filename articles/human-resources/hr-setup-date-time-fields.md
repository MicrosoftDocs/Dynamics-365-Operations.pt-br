---
title: Entender os campos de data e hora
description: Entenda o que esperar ao usar os campos Data e Hora no Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: efda2b54f9228ac539e6ba2d18f85bf3ad15a6ff
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802422"
---
# <a name="understand-date-and-time-fields"></a>Entender os campos de data e hora

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Os campos **Data e Hora** são um conceito fundamental no Dynamics 365 Human Resources. É importante compreender como trabalhar com dados de **Data e Hora** em formulários, no Dataverse e em fontes externas.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Compreendendo a diferença entre os tipos de dados do campo Data e Data e Hora

Os campos **Data e Hora** contêm informações de fuso horário, enquanto os campos **Data** não. Os campos **Data** exibem as mesmas informações em qualquer local. Quando você insere uma data no campo **Data**, o Human Resources registra a mesma data no banco de dados.

Ao exibir os dados em um campo **Data e Hora**, o Human Resources ajusta a data e hora com base no fuso horário do usuário definido no formulário **Opções do usuário** (**Comum > Configuração > Opções do usuário**). As informações de data e hora que você insere nesse campo podem não ser as mesmas que são registradas na base de dados.

[![Formulário Opções do usuário](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Compreendendo os campos Data e Hora nos formulários 

Os dados de **Data e Hora** exibidos na tela não serão os mesmos que os dados armazenados no banco de dados se o fuso horário do usuário não estiver definido como Tempo Universal Coordenado (UTC). Os dados dos campos **Data e Hora** sempre são armazenados em UTC.

[![UTC de formulário Trabalhador](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Compreenda os campos Data e Hora no banco de dados 

Quando o Human Resources registra um valor de **Data e Hora** no banco de dados, os dados são armazenados em UTC. Isso permite que os usuários vejam todos os dados de **Data e Hora** relacionados ao fuso horário definido nas opções do usuário.
 
No exemplo acima, a hora de início é um momento específico, e não uma data. Ao alterar o fuso horário do usuário conectado de GMT +12:00 para GMT UTC, o mesmo registro mostra 30/04/2019 12:00:00 em vez de 01/05/2019 12:00:00.
  
No exemplo abaixo, o início do funcionário 000724 torna-se ativo no mesmo horário independentemente do fuso horário. O funcionário estará ativo em 30/04/2019 no fuso horário GMT, que é o equivalente a 01/05/2019 no fuso horário GMT+12:00. Ambos fazem referência ao mesmo momento e não a uma data específica. 

[![GMT de formulário Trabalhador](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Dados de Data e Hora no Data Management Framework, Excel, Dataverse e Power BI 

Os relatórios do Data Management Framework, do suplemento do Excel, do Dataverse e do Power BI foram desenvolvidos para interagir com os dados diretamente no nível do banco de dados. Como não há um cliente para ajustar dados de **Data e Hora** ao fuso horário do usuário, todos os valores de **Data e Hora** estão em UTC, o que pode resultar em algumas suposições incorretas ao inserir ou exibir dados.  
 
O banco de dados supõe que dados de **Data e Hora** enviados via DMF, Excel, ou Dataverse estejam em UTC. Isso poderá ocasionar certa confusão quando o valor de **Data e hora** enviado não for exibido conforme esperado, pois o fuso horário do usuário que está visualizando os dados não está definido como UTC. 
 
O mesmo pode ocorrer de maneira reversa mediante a exportação de dados. Os dados de **Data e Hora** na entidade exportada do DMF podem ser diferentes dos exibidos no cliente do Dynamics. 
 
Ao usar fontes externas, como o DMF, para exibir ou criar dados, é importante se lembrar de que os valores de **Data e Hora** são considerados em UTC por padrão, seja qual for o fuso horário do computador do usuário ou as configurações atuais de fuso horário do usuário. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Exemplos do mesmo registro sendo exibido em diferentes áreas do produto 

**Human Resources com fuso horário do usuário definido como UTC**

[![Formulário de trabalhador definido como UTC](./media/worker-form3.png)](./media/worker-form3.png)

**Human Resources com fuso horário do usuário definido como GMT +12:00** 

[![Formulário de trabalhador definido como GMT](./media/worker-form4.png)](./media/worker-form4.png)

**Excel via OData**

[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Preparação do DMF**

[![Preparação do DMF](./media/DMFStaging.png)](./media/DMFStaging.png)

**Exportar DMF**

[![Exportação de DMF](./media/DMFexport.png)](./media/DMFexport.png)

**Excel via Dataverse**

[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Consulte também

[Dados de data e hora](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Fusos horários de preferência do usuário](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]