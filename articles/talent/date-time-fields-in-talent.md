---
title: Trabalhar com data e hora no Microsoft Dynamics 365 for Talent
description: Entenda o que esperar ao usar os campos Data e Hora no Microsoft Dynamics 365 for Talent. Obtenha clareza sobre o que esperar ao interagir com dados de data e hora em um formulário no Dynamics 365 for Talent, em uma fonte externa, ou no Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-06-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b4c652992272ed1a5aecbb4c78f0d11f077149d1
ms.sourcegitcommit: 46bded82aa072adfedcf443629c2adc69f512c09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2019
ms.locfileid: "1791194"
---
# <a name="date-and-time-fields-in-talent"></a>Campos de data e hora no Talent

[!include [banner](includes/banner.md)]

Os campos**Data e Hora** são um conceito fundamental no Dynamics 365 for Talent. É importante compreender como trabalhar com dados de **Data e Hora** em um formulário do Dynamics 365, no Common Data Service e em fontes externas.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Compreendendo a diferença entre os tipos de dados do campo Data e Data e Hora

Os campos **Data e Hora** contêm informações de fuso horário, enquanto os campos **Data** não. Os campos **Data** exibem as mesmas informações em qualquer local. Quando você insere uma data no campo **Data**, o Talent registra a mesma data no banco de dados.

Ao exibir os dados em um campo **Data e Hora**, o Talent ajusta a data e hora com base no fuso horário do usuário definido no formulário **Opções do usuário** (**Comum > Configuração > Opções do usuário**). As informações de data e hora que você insere nesse campo podem não ser as mesmas que são registradas na base de dados.

[![Formulário Opções do usuário](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Compreendendo os campos Data e Hora nos formulários 

Ao inserir dados no campo **Data e Hora**, os dados exibidos na tela não serão os mesmos que aqueles armazenados no banco de dados se o fuso horário do usuário não estiver definido como Tempo Universal Coordenado (UTC). Os dados dos campos **Data e Hora** sempre são armazenados em UTC.

[![Formulário Trabalhador](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Compreenda os campos Data e Hora no banco de dados 

Quando o Talent registra um valor de **Data e Hora** no banco de dados, os dados são armazenados em UTC. Isso permite que os usuários vejam todos os dados de **Data e Hora** relacionados ao fuso horário definido nas opções do usuário.
 
No exemplo acima, a hora de início é um momento específico, e não uma data. Ao alterar o fuso horário do usuário conectado de GMT +12:00 para GMT UTC, o mesmo registro que foi criado exibirá 30/04/2019 12:00:00 em vez de 01/05/2019 de 12:00:00.
  
No exemplo abaixo, o início do funcionário 000724 torna-se ativo no mesmo horário independentemente do fuso horário. O funcionário estará ativo em 30/04/2019 no fuso horário GMT, que é o equivalente a 01/05/2019 no fuso horário GMT+12:00. Ambos fazem referência ao mesmo momento e não a uma data específica. 

[![Formulário Trabalhador](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a>Dados de Data e Hora no Data Management Framework, Excel, Common Data Service e Power BI 

Os relatórios do Data Management Framework, do suplemento do Excel, do Common Data Service e do Power BI foram desenvolvidos para interagir com os dados diretamente no nível do banco de dados. Como não há um cliente para ajustar os dados de **Data e Hora** ao fuso horário do usuário, todos os valores de **Data e Hora** estão em UTC, o que pode resultar em algumas suposições incorretas na inserção ou na exibição de dados.  
 
O banco de dados supõe que os dados de **Data e Hora** enviados pelo DMF, Excel, ou Common Data Service são assumidos estejam em UTC. Isso poderá ocasionar certa confusão quando o valor de **Data e hora** enviado não for exibido conforme esperado, pois o fuso horário do usuário que está visualizando os dados não está definido como UTC. 
 
O mesmo pode ocorrer de maneira reversa mediante a exportação de dados. Os dados de **Data e Hora** na entidade exportada do DMF podem ser diferentes daqueles exibidos no cliente do Dynamics. 
 
Ao usar fontes externas, como o DMF, para exibir ou criar dados, é importante se lembrar de que os valores de **Data e Hora** são considerados em UTC por padrão independentemente do fuso horário do computador do usuário ou das configurações atuais de fuso horário do usuário. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Exemplos do mesmo registro sendo exibido em diferentes áreas do produto 

**Talent com fuso horário do usuário definido como UTC**

[![Formulário Trabalhador](./media/worker-form3.png)](./media/worker-form3.png)

**Talent com fuso horário do usuário definido como GMT +12:00** 

[![Formulário Trabalhador](./media/worker-form4.png)](./media/worker-form4.png)

**Excel via OData**

[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Preparação do DMF**

[![Preparação do DMF](./media/DMFStaging.png)](./media/DMFStaging.png)

**Exportar DMF**

[![Preparação do DMF](./media/DMFexport.png)](./media/DMFexport.png)

**Excel via Common Data Service**

[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)

### <a name="see-also"></a>Consulte também

[Dados de data e hora](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Fusos horários de preferência do usuário](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 