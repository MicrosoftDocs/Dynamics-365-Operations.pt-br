---
title: Planos de manutenção
description: Este tópico explica os planos de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4e9dca4b9b163e73c33ec2dc88b8aea2cecd9bef
ms.sourcegitcommit: 6476f27c8d3dced7c2e9a7344a4e378b51a1983e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2019
ms.locfileid: "1922197"
---
# <a name="maintenance-plans"></a>Planos de manutenção

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Um plano de manutenção define quando um trabalho de manutenção preventiva pré-planejada deve ser executado em um ativo. Os planos de manutenção podem estar relacionados a ativos, tipos de ativos, locais funcionais ou tipos de locais funcionais, mas primeiro você cria os planos de manutenção a serem usados em sua empresa.

Um plano de manutenção pode ter várias linhas de plano de manutenção. O intervalo e tipo de trabalho de manutenção são especificados na linha do plano de manutenção. Há dois tipos de linhas de plano de manutenção:

- Tempo  
- Contador  

As linhas do plano de manutenção do tipo "Tempo" são usadas para manutenção planejada recorrente com base em um intervalo de tempo fixo. As linhas do plano de manutenção do tipo "Contador" são usadas para manutenção planejada ou manutenção reativa com base nos registros do contador de ativos. Um plano de manutenção pode ter várias linhas de plano de manutenção dos dois tipos.

>[!NOTE]
>Se nenhum valor de contador tiver sido registrado para um tipo de contador em um ativo, as linhas do plano de manutenção serão omitidas.

Primeiro, você cria os planos de manutenção necessários para seus trabalhos de manutenção preventiva e seleciona os tipos de ativos, ativos, tipos de locais funcionais e locais funcionais que devem estar relacionados a cada plano de manutenção. Posteriormente, se necessário, você também pode adicionar planos de manutenção a um ativo ou a um local funcional, que é feito na Guia Rápida **Todos os ativos** > selecionar ativo > **Planos de manutenção do ativo** ou na Guia Rápida **Todos os locais funcionais** > selecionar local funcional > **Planos de manutenção**.

Se você adicionar um plano de manutenção a tipos de ativos ou tipos de locais funcionais, isso significa que, ao criar novos ativos ou locais funcionais com esses tipos de ativos ou tipos de locais funcionais, o ativo ou local funcional será automaticamente adicionado ao plano de manutenção. A data de início da relação para um plano de manutenção será a data atual que talvez precise ser ajustada.

## <a name="set-up-maintenance-plans"></a>Configurar planos de manutenção

Esta seção descreve como configurar linhas do plano de manutenção e oferece exemplos de como elas podem ser usadas.

1. Clique em **Gerenciamento de ativos** > **Configuração** > **Manutenção preventiva** > **Planos de manutenção**.

2. Clique em **Novo** para criar uma nova sequência.

3. Insira uma ID no campo **Sequência de manutenção** e um nome no campo **Nome**.

4. No campo **Data do plano**, insira a data de início da qual o planejamento pode ser feito no plano de manutenção. Observe que as linhas do plano de manutenção baseadas no tempo podem ter outras datas do plano.

5. Selecione "Sim" no botão de alternância **Ativo** para ativar o plano de manutenção.

>[!NOTE]
>Se você desativar um plano de manutenção, nenhum lançamento de agendamento será criado no agendamento de manutenção, quando você executar um trabalho do plano de manutenção do agendamento.

6. Os campos **Dias de tolerância antes de** e **Dias de tolerância depois de** são relacionados às linhas do plano de manutenção nas quais a caixa de seleção **Suprimir trabalhos de manutenção sobrepostos** é selecionada (consulte a etapa 17). Os campos "Tolerância" são usados para estender o intervalo em dias em que, se vários planos de manutenção se sobrepõem, o trabalho mais abrangente/maior é criado como uma linha de agendamento de manutenção, durante o agendamento do plano de manutenção, enquanto trabalhos sobrepostos mais frequentes são omitidos, durante o agendamento do plano de manutenção. Insira o número de dias no campo **Dias de tolerância antes de**, por exemplo, "2".

7. Se você inseriu um valor em **Dias de tolerância antes de**, insira também o número de dias no campo **Dias de tolerância após**, por exemplo, "2".

>[!NOTE]
>O exemplo descrito nesta e na etapa anterior significa que, se várias linhas do plano de manutenção se sobrepuserem, e **Suprimir trabalhos de manutenção sobrepostos** for selecionado para uma ou mais linhas, o período de omissão das linhas de agendamento de manutenção será estendido para um total de cinco dias (a data de início prevista na linha de agendamento de manutenção *e* dois dias antes *e* dois dias depois dessa data).

8. Os campos no grupo **Detalhes** na Guia Rápida **Detalhes** mostram várias linhas do plano de manutenção configuradas no plano de manutenção e vários ativos e locais funcionais relacionados ao plano de manutenção.

9. Na Guia Rápida **Linhas**, clique em **Adicionar linha de tempo** ou **Adicionar linha do contador de ativos** para criar uma nova linha do plano de manutenção.

10. Insira uma descrição para a linha no campo **Descrição da ordem de serviço**. A descrição é transferida para as ordens de serviço relacionadas.

11. No campo **Tipo de trabalho de manutenção**, selecione o tipo de trabalho para o qual a linha do plano de manutenção está relacionada.

12. Nos campos **Grade do tipo de trabalho de manutenção** e **Ofício**, selecione a grade e o ofício relacionado ao tipo de trabalho de manutenção.

13. Nos campos **Concluir em dias** e **Concluir em horas** você pode inserir a data de término esperada em dias ou horas. A data de término esperada é inserida em relação à data de início esperada, que é calculada quando as linhas de agendamento de manutenção são criadas. Por exemplo, você pode inserir "7" no campo **Concluir em dias** para indicar que o trabalho relacionado deve ser concluído dentro de uma semana da data de início esperada.

14. No campo **Tipo do intervalo**, selecione o tipo de intervalo a ser usado na linha do plano de manutenção, por exemplo, "Repetido..." ou "Uma vez...". Consulte a tabela [Visão geral dos tipos de intervalo](## Interval types overview) abaixo para obter uma descrição da relação entre os tipos de intervalo e os tipos de linha.

15. O campo **Período** se relaciona aos tipos de linhas baseadas no tempo. Selecione o tipo de período relacionado à frequência do período.

16. No campo **Frequência do período**, insira o número de vezes que a linha deve ser usada para planejar trabalhos de manutenção preventiva. Exemplo: Se você criou uma linha do tipo "Contador" e seu contador é quantidade em produção e você inserir o número "20000" neste campo, novas linhas da sequência de manutenção serão criadas durante o agendamento de manutenção preventiva, toda vez que for esperada uma produção de mais de 20.000 itens.

17. A caixa de seleção **Suprimir trabalhos de manutenção sobrepostos** é relacionada aos tipos de linhas baseadas no tempo e no contador. Marque a caixa de seleção para excluir as entradas do agendamento de manutenção que foram criadas na mesma data. Isso é relevante, por exemplo, se você criou uma linha de inspeção de 1 mês, de 6 meses e de 1 ano. Para a inspeção de 1 ano, você quer que apenas esta inspeção seja feita, e não as outras duas inspeções, que também se encaixariam no prazo. Para configurar este exemplo corretamente, você configura a linha de inspeção de 1 ano como a primeira linha, a linha de 6 meses como a segunda linha e a linha de 1 mês como a terceira linha e você marca a caixa de seleção **Suprimir trabalhos de manutenção sobrepostos** para linhas de 1 mês e de 6 meses. Dessa forma, você garante que, ao atingir a marca de 1 ano, as inspeções de um mês e seis meses sejam omitidas e uma linha de agendamento de manutenção seja criada apenas para a linha de inspeção de 1 ano.

>[!NOTE]
>O exemplo descrito nesta etapa mostra que o trabalho mais abrangente, que contém o maior número de tarefas e que não é realizado com tanta frequência, deve sempre ser inserido como a primeira linha. Os trabalhos mais frequentes são então inseridos como linhas separadas na ordem da frequência, colocando o trabalho mais frequente no final da lista.

18. O campo **Contador** se relaciona aos tipos de linha com base no contador. Selecione o tipo de contador a ser usado na linha. Se um tipo de contador não estiver ativo em um ativo relacionado, a linha do plano de manutenção será omitida.

19. O campo **Limite de tempo do contador de ativos, em dias** se refere aos tipos de linhas baseadas no contador. Insira um número que define quantos dias os registros do contador regressivo são verificados quando o agendamento do plano de manutenção for concluído. Isso significa em quanto tempo os dados (registros do contador existentes) são usados como base para calcular a tendência que determina quantas linhas de agendamento de manutenção são criadas.

>*Exemplo:* Se for esperado que sejam efetuados registros de contador uma vez por mês, você pode inserir o número '365' neste campo, pois o agendamento do plano de manutenção sempre será baseado nos últimos 12 meses e, portanto, criará linhas de agendamento de manutenção com base na tendência do último ano. Por outro lado, se você inserir o número '10' nesse campo, espera-se que os registros do contador sejam feitos com mais frequência, por exemplo, diariamente. Isso significa que ao agendar o plano de manutenção, os registros do contador dos últimos 10 dias são usados como base para o agendamento das linhas de agendamento de manutenção.

20. O campo **Data do plano** se relaciona aos tipos de linhas baseadas no tempo. Se a linha do plano de manutenção tiver outra data de planejamento diferente do plano de manutenção, selecione uma data no campo **Data do plano** na linha.

21. No campo **Nível de serviço**, selecione um nível de serviço da ordem de serviço como uma delimitação adicional na linha do plano de manutenção para ser usado como um nível de serviço em ordens de serviço.

22. Marque a caixa de seleção **Criação automática** se quiser que uma ordem de serviço seja criada automaticamente, de acordo com a linha do plano de manutenção selecionada ao agendar planos de manutenção.

23. Se tiver marcado a caixa de seleção **Criação automática**, você poderá selecionar um tipo de ordem de serviço para a ordem de serviço criada automaticamente no campo **Tipo de ordem de serviço**. Se tiver marcado a caixa de seleção **Criação automática** e não selecionar um tipo de ordem de serviço neste campo, será usado o tipo de ordem de serviço selecionado no link **Gerenciamento de ativos** > **Configuração** > **Parâmetros de gerenciamento de ativos** > **Ordens de serviço** campo > **Tipo de ordem de serviço preventiva**.

24. Use os campos **Estação de** e **Estação até** para criar uma linha do plano de manutenção baseada no tempo de repetição dentro do período de 12 meses. *Exemplo:* O equipamento usado para manutenção de áreas verdes requer manutenção a cada primavera, dentro de um período predefinido. Insira a data de início do período a ser repetida no campo **Estação de**.

25. Insira a data de término do período a ser repetida no campo **Estação até**.

26. No campo **Período resultante** será exibido o período atual a ser repetido. Quando o período atual tiver passado, e você iniciar um novo ano, o período exibido neste campo será atualizado para refletir o próximo período na sequência de repetição.

27. Na Guia Rápida **Ativos**, selecione os ativos que devem ser relacionados ao plano de manutenção.

28. Na Guia Rápida **Tipos de ativos**, selecione os tipos de ativos que devem ser relacionados ao plano de manutenção.

29. Na Guia Rápida **Locais funcionais**, selecione os locais funcionais que devem ser relacionados ao plano de manutenção. Se necessário, você pode criar a configuração mais específica selecionando um tipo de ativo relacionado, um fabricante e um modelo.

30. Na Guia Rápida **Tipos de locais funcionais**, selecione os tipos de locais funcionais que devem ser relacionados ao plano de manutenção.

>[!NOTE]
>Quando as ordens de trabalho são criadas manualmente nos ativos que serão cobertos por uma garantia do fornecedor, uma caixa de diálogo será exibida para que o usuário fique ciente da garantia. A criação da ordem de serviço pode ser cancelada. A verificação de uma relação da garantia é omitida para as ordens de serviço que são criadas automaticamente.

## <a name="interval-types-overview"></a>Visão geral dos tipos de intervalo

| Descrição e Tipo de intervalo                                                                                                                                                                                                                                                                                                                                                                                                       | Tipo de Linha: Horário                                                                                                                                                                                                                                                                                                                                                           | Tipo de Linha: Contador                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Tipo de intervalo: Repetido a partir da data do plano** A contagem começa a partir da data do plano usada. Ao agendar planos de manutenção, linhas de agendamento de manutenção são criadas quando o intervalo é atingido.                                                                                                                                                                                                                | É usada a **Data do plano** na linha do plano de manutenção. Se nenhuma data do plano for selecionada na linha, será usada a **Data do plano** do plano de manutenção. Exemplo: se o número "3" for inserido no campo **Frequência do período** e "Ano" for selecionado no campo **Período**, uma nova linha de agendamento de manutenção será criada a cada 3 anos.                             | Será usada a **Data do plano** para o plano de manutenção. Se o contador for substituído, a data de substituição mais recente será usada como a data do plano.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Tipo de intervalo: Repetido a partir da data de início** A contagem começa da data de início na relação do ativo. A data é selecionada na exibição de detalhes **Todos os ativos** > Guia Rápida **Planos de manutenção do ativo** > campo **Data de início** ou na exibição de detalhes **Todos os locais funcionais** > Guia Rápida **Planos de manutenção** > campo **Data de início**. Ao agendar planos de manutenção, uma linha do agendamento de manutenção é criada quando o intervalo é atingido. | A data de início da linha do plano de manutenção no ativo ou local funcional é usada. Se este campo ficar em branco, a **Data do plano** de manutenção é usada.                                                                                                                                                                                                 | A data de início da linha do plano de manutenção no ativo ou local funcional é usada. Se este campo ficar em branco, a **Data do plano** de manutenção é usada.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Tipo de intervalo: Repetido a partir da última ordem de serviço** A contagem começa a partir da data e da hora de término reais da ordem de serviço mais recente concluída no ativo com esses tipo de trabalho de manutenção/grade do tipo de trabalho de manutenção/combinação de ofício específicos. A data e a hora são mostradas no campo **Final real** na exibição de detalhes **Todas ordens de serviço**.                                                                                                                                 | A data e a hora de término reais da ordem de serviço concluída no ativo com esses tipo de trabalho de manutenção/grade do tipo de trabalho de manutenção/combinação de ofício específicos. Se nenhuma ordem de serviço concluída for encontrada, uma das datas usadas no tipo de intervalo "Repetido a partir da data de início" descrita acima será usada.                                                                                             | A data e a hora reais de conclusão de ordem de serviço ativo *e* na grade do tipo de trabalho de manutenção/trabalho de manutenção/combinação de ofício. é usada. Se a data e hora inicial estiver em branco na ordem de serviço, uma das datas usadas no tipo de intervalo "Repetido a partir da data de início" descrita acima será usada.                                                                                                                                                                                                                                                                                                                                                                           |
| **Tipo de intervalo: Depois da data do plano** Consulte a descrição do tipo de intervalo "Repetido a partir da data do plano". A única diferença é que este tipo de intervalo deve ser usado apenas uma vez.                                                                                                                                                                                                                                                   | Consulte a descrição do tipo de intervalo "Repetido a partir da data do plano" acima. Esse intervalo geralmente é usado para uma manutenção ocasional ou trabalho de serviço.                                                                                                                                                                                                                             | Consulte a descrição do tipo de intervalo "Repetido a partir da data do plano" acima. Esse intervalo geralmente é usado para uma manutenção ocasional ou trabalho de serviço. **Observação: 1** O tipo de intervalo é relevante apenas se o contador for substituído cada vez que você executar um trabalho de manutenção ou de serviço. Se, por algum motivo, um contador foi substituído antes do fim do intervalo planejado, uma nova hora será calculada para o trabalho a partir do momento da substituição do contador. **Observação: 2** Se o contador for substituído ao concluir o trabalho de manutenção ou de serviço, este tipo de intervalo funcionará como o tipo de intervalo "Repetido a partir da data do plano" acima.                                             |
| **Tipo de intervalo: Uma vez a partir da data de início** Consulte a descrição do tipo de intervalo "Repetido a partir da data de início" acima. A única diferença é que este tipo de intervalo deve ser usado apenas uma vez.                                                                                                                                                                                                                                                 | Consulte a descrição do tipo de intervalo "Repetido a partir da data de início" acima. Esse intervalo geralmente é usado para uma manutenção ocasional ou trabalho de serviço.                                                                                                                                                                                                                            | Consulte a descrição do tipo de intervalo "Repetido a partir da data de início" acima. Esse intervalo geralmente é usado para uma manutenção ocasional ou trabalho de serviço. A **Observação 1** acima também se aplica a este tipo de intervalo. **Observação: 3** Se o contador for substituído ao concluir o trabalho de manutenção ou de serviço, este tipo de intervalo funcionará como o tipo de intervalo "Repetido a partir da data de início" acima.                                                                                                                                                                                                                                                                                                |
| **Tipo de intervalo: Uma vez atingido acima** Este tipo de intervalo somente é relacionado aos contadores e é usado para indicar o limite superior configurado na linha do plano de manutenção. As entradas do agendamento de manutenção têm a data e hora de início esperadas do registro do contador, o que significa que essas entradas serão criadas com uma data de início esperada igual ou anterior à data do sistema.                                                | N/D                                                                                                                                                                                                                                                                                                                                                                       | O intervalo do contador indica um limite superior. Se esse limite for excedido ao criar um registro do contador, uma linha de agendamento de manutenção será criada quando você agendar uma manutenção preventiva.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Tipo de intervalo: Uma vez atingido abaixo** Este tipo de intervalo somente é relacionado aos contadores e é usado para indicar o limite inferior configurado na linha do plano de manutenção. As entradas do agendamento de manutenção têm a data e hora de início esperadas do registro do contador, o que significa que essas entradas serão criadas com uma data de início esperada igual ou anterior à data do sistema.                                                 | N/D                                                                                                                                                                                                                                                                                                                                                                       | O intervalo do contador indica um limite inferior. Se esse limite for excedido ao criar um registro do contador, uma linha de agendamento de manutenção será criada quando você agendar uma manutenção preventiva.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Tipo de intervalo: Vinculado a partir da data de início** Este tipo de intervalo cria uma linha de agendamento de manutenção apenas uma vez. Um plano de manutenção pode conter mais linhas de plano de manutenção que usam esse tipo de intervalo e essas linhas são vinculadas. Normalmente, você cria um plano de manutenção que contém linhas somente deste tipo de intervalo. As linhas de agendamento de manutenção são criadas identificando a linha do plano de manutenção que tem a primeira data e hora de início esperadas.                                                                                                                                                                                                                                                                                                                                                                                           | Consulte a descrição de "Uma vez a partir da data de início" acima. Exemplo: você cria duas linhas em um plano de manutenção para um trabalho de serviço em um carro: uma linha baseada no tempo com um período de 1 ano e uma linha baseada no contador com um limite de 25.000 km. Uma linha do agendamento de manutenção é criada para o limite que foi atingido primeiro. Para esse tipo de linha você cria a linha com o período de 1 ano.                                                                                                                                                                                   | Consulte a descrição de "Uma vez a partir da data de início" acima. Exemplo: você cria duas linhas em um plano de manutenção para um trabalho de serviço em um carro: uma linha baseada no tempo com um período de 1 ano e uma linha baseada no contador com um limite de 25.000 km. Uma linha do agendamento de manutenção é criada para o limite que foi atingido primeiro. Para esse tipo de linha você cria a linha com o período de 25.000 km. Exemplo de criação de duas linhas de contador: Você também pode configurar um plano de manutenção com duas linhas vinculadas baseadas no contador, nas quais a primeira linha tem um limite de 10.000 itens produzidos e a segunda linha refere-se à máquina ou centro de trabalho que requer serviço após a execução de 3.000 horas.                                                                                                                                                           |
| **Tipo de intervalo: Vinculado da última ordem de serviço** Este tipo de intervalo cria novas linhas de agendamento de manutenção após cada ordem de serviço concluída. Um plano de manutenção pode conter mais linhas que usam esse tipo de intervalo e essas linhas são vinculadas. Normalmente, você criará um plano de manutenção que contenha linhas de plano de manutenção somente desse tipo de intervalo. As linhas de agendamento de manutenção são criadas identificando a linha do plano de manutenção que tem a primeira data e hora de início esperadas.                                                                                                                                                                                                                                                                        | Este tipo de intervalo funciona basicamente como "Vinculado a partir da data de início". A única diferença é a data na qual o tipo de intervalo é baseado. A data usada é a data e hora real na ordem de serviço mais recente concluída no ativo *e* a combinação de tipo de trabalho de manutenção/grade do tipo de trabalho de manutenção/ofício.                                                                                                                                                                                                                                                           | Este tipo de intervalo funciona basicamente como "Vinculado a partir da data de início". A única diferença é a data na qual o tipo de intervalo é baseado. A data usada é a data e hora real na ordem de serviço mais recente concluída no ativo *e* a combinação de tipo de trabalho de manutenção/grade do tipo de trabalho de manutenção/ofício.                                                                                                                   |


>[!NOTE]
>Quando as linhas de agendamento de manutenção são criadas para as linhas do plano de manutenção baseadas no tempo, o tempo esperado é sempre o início do dia. Para linhas do plano de manutenção baseadas no contador, o tempo esperado pode ser qualquer um durante o dia.

Abaixo você encontrará exemplos de configuração de linhas do plano de manutenção baseadas no contador e baseadas no tempo:

**Exemplo 1 - Linha do plano de manutenção baseada no tempo:** Um trabalho de lubrificação pode ser configurado em um intervalo fixo, ocorrendo uma vez por semana. Para essa finalidade, selecione "Repetido a partir da data do plano" no campo **Tipo de intervalo**. Veja um exemplo na ilustração a seguir.

![Figura 1](media/02-preventive-maintenance.png)

**Exemple 2 - Linha do plano de manutenção baseada no tempo:** Um trabalho de inspeção pode ser configurado para ser executado aproximadamente uma vez por semana. Para essa finalidade, selecione "Repetido a partir da última ordem de serviço" no campo **Tipo de intervalo**. Veja um exemplo na ilustração a seguir.

![Figura 2](media/03-preventive-maintenance.png)

**Exemplo 3 - Linha do plano de manutenção baseada no contador:** A ilustração gráfica a seguir mostra um contador de horas para o qual uma nova linha de agendamento de manutenção é criada a cada 250 horas decorridas. O tipo de intervalo desta linha com base no contador é "Repetido a partir da data de início". A data de início é a data de início dos ativos relacionados na exibição de detalhes **Todos os ativos** > Guia Rápida **Planos de manutenção do ativo** > campo **Data de início** ou na exibição de detalhes **Local funcional** Guia Rápida > **Planos de manutenção** > campo **Data de início**. Este é um exemplo de um plano de manutenção *preventiva* porque a linha do agendamento de manutenção é criada automaticamente cada vez que o limite (+ 250) for atingido.

![Figura 3](media/04-preventive-maintenance.png)


**Exemplo 4 - Linha do plano de manutenção baseada no contador:** A ilustração gráfica a seguir mostra uma diminuição no valor do contador, medindo o desgaste da pastilha de freio. Uma linha do agendamento de manutenção é criada quando um registro do contador abaixo de 20 mm é criado na pastilha de freio. O tipo de intervalo desta linha com base no contador é "Uma vez atingido abaixo" ou "Uma vez a partir da última data de início". Este é um exemplo de um plano de manutenção *reativo* porque a linha do agendamento de manutenção não é criada até que uma medição abaixo de 20 mm seja registrada.

![Figura 4](media/05-preventive-maintenance.png)


**Exemplo 5 - Linha do plano de manutenção baseada no contador:** A ilustração gráfica a seguir mostra um contador com um limite de -18° Celsius. Uma linha do agendamento de manutenção é criada quando for feito um registro do contador acima de -18° Celsius. O tipo de intervalo desta linha com base no contador é "Uma vez atingido acima". Este é um exemplo de um plano de manutenção *reativo* porque a linha do agendamento de manutenção não é criada até que seja registrada uma medição maior que -18° Celsius.

![Figura 5](media/06-preventive-maintenance.png)

- Quando você cria um novo ativo, e esse ativo usa um tipo de ativo relacionado a um plano de manutenção, o plano de manutenção é inserido automaticamente na Guia Rápida **Todos os objetos** > **Planos de manutenção do ativo**. Além disso, em **Padrões do tipo de ativo**, na Guia Rápida **Planos de manutenção**, os planos de manutenção relacionados serão inseridos automaticamente.  
- Se você adicionar ou remover tipos de ativos ou tipos de locais funcionais nos **Planos de manutenção**, essa alteração somente será refletida em novos ativos criados após você fazer a alteração.  
- Se você adicionar ou remover ativos ou locais funcionais nos **Planos de manutenção**, essa alteração será atualizada automaticamente na Guia Rápida **Todos os ativos** > **Planos de manutenção do ativo** ou na Guia Rápida **Todos os locais funcionais** > **Planos de manutenção**.  

A ilustração a seguir mostra um exemplo de um plano de manutenção "Assistência a caminhões" na página **Planos de manutenção**.

![Figura 6](media/07-preventive-maintenance.png)


## <a name="add-a-maintenance-plan-to-an-asset"></a>Adicionar um plano de manutenção a um ativo

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos** ou **Ativos ativados**.

2. Selecione o ativo no qual deseja configurar um plano de manutenção e clique em **Editar**.

3. Na Guia Rápida **Planos de manutenção do ativo**, clique em **Adicionar linha** para adicionar um plano de manutenção ao ativo.

4. No campo **Plano de manutenção**, selecione o plano de manutenção relevante.

5. No campo **Data de início**, selecione a data a partir da qual o planejamento dos trabalhos de manutenção preventiva pode ser realizado. 

6. Clique em **Salvar**. O campo **Ativo** será atualizado automaticamente.

A ilustração a seguir mostra um exemplo de planos de manutenção configurados em um ativo na página **Todos os ativos**.

![Figura 7](media/08-preventive-maintenance.png)

