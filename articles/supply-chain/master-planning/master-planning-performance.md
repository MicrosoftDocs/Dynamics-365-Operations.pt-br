---
title: Aumentar o desempenho de planejamento mestre
description: Este tópico explica as várias opções que podem ajudar a melhorar o desempenho do planejamento mestre ou a solução de problemas.
author: t-benebo
manager: tfehr
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 380329cbeaa1fc2a2691c8165bc57483d1420aa1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005068"
---
# <a name="improve-master-planning-performance"></a>Melhorar o desempenho de planejamento mestre

[!include [banner](../includes/banner.md)]

Este tópico explica as várias opções que podem ajudar a melhorar o desempenho do planejamento mestre ou a solução de problemas. Inclui informações sobre os parâmetros e definições e também sobre configurações e ações recomendadas. Também contém um resumo de todos os parâmetros importantes que você deve considerar quando tiver trabalhos de planejamento mestre de execução longa.

Este tópico é criado para os administradores de sistema ou usuários de TI que têm a capacidade de resolver problemas. Também é destinado aos planejadores de suprimento ou de produção porque tem informações sobre parâmetros que estão relacionados às necessidades de planejamento comercial. 

## <a name="parameters-related-to-master-planning-performance"></a>Parâmetros relacionados ao desempenho do planejamento mestre

Vários parâmetros influenciam o tempo de execução do planejamento mestre e devem ser considerados.

### <a name="number-of-threads"></a>Número de threads

O parâmetro **Número de threads** permite ajustar o processo de agendamento do planejamento mestre para ajudá-lo a melhorar o desempenho no conjunto de dados específico. Este parâmetro especifica o número total de threads que serão usados para executar o planejamento mestre. Isso causa paralelização da execução do planejamento mestre que ajuda a reduzir o tempo de execução. 

É possível definir o parâmetro **Número de threads** na caixa de diálogo **Execução do planejamento mestre**. Para abrir esta caixa de diálogo, vá para **Planejamento mestre \> Planejamento mestre \> Executar \> Planejamento mestre** ou selecione **Executar** no espaço de trabalho **Planejamento mestre**. Para determinar o melhor valor para este parâmetro, você terá que contar com um processo de tentativa e erro. Entretanto, você pode usar as seguintes fórmulas para calcular um valor inicial:

- **Se seu setor for de fabricação:** (Número de threads) = (Número de ordens planejadas ÷ 1.000)
- **Caso contrário:** (Número de threads) = (Número de itens ÷ 1.000)

O número de auxiliares usados durante o planejamento mestre deve ser menor ou igual ao número máximo dos threads que são permitidos no servidor de lote. Se o número de auxiliares exceder o número de threads no servidor de lote, os threads adicionais não executarão nenhum trabalho.

> [!NOTE]
> Definir o parâmetro **Número de threads** como **0** (zero) aumenta o tempo de execução do planejamento mestre. Portanto, recomendamos que você sempre defina um valor maior que 0.

### <a name="number-of-tasks-in-helper-task-bundle"></a>Números de tarefas no pacote de tarefas do auxiliar

Alterar a configuração **Número de tarefas no pacote de tarefas** (isto é, o tamanho do pacote), você pode reduzir o tempo de execução. Essa configuração controla o número de itens planejados juntos por um único auxiliar.

Você pode definir o parâmetro **Número de tarefas no pacote de tarefas** na seção **Desempenho** na guia **Geral** da página **Parâmetros de planejamento mestre** (**Planejamento mestre \> Configuração \> Parâmetros de planejamento mestre**). O melhor valor para este parâmetro dependerá de seus dados. Portanto, recomendamos que você inicie com um valor **1** e, em seguida, use o processo de tentativa e erro para determinar o melhor valor para sua configuração.

Geralmente, recomendamos que você aumente o número de tarefas quando o número de itens for muito grande (em centenas de milhares). Caso contrário, será necessário diminuir o número de tarefas. Para os seguintes setores específicos, considere essas recomendações:

- Nos setores de varejo e distribuição, onde há muitos itens independentes, use muitos auxiliares, pois não há dependência entre os itens. 
- No setor de fabricação, onde há muitas listas de materiais (BOMs) e subcomponentes compartilhados, use menos auxiliares, pois as dependências entre os itens podem causar tempo de espera.

> [!TIP]
> Se tiver problemas de desempenho, recomendamos reduzir a configuração **Número de auxiliares no pacote de tarefas** para **1**. Em seguida, você pode iniciar o processo de tentativa e erro para localizar o melhor valor para sua configuração. Geralmente, os problemas de desempenho ocorrem quando um item leva mais tempo para processar do que os itens restantes. Nesse caso, você verá que duas tarefas subsequentes que têm um status **Cobertura** na execução do planejamento mestre têm diferentes tempos de execução. Em casos extremos, essa diferença pode chegar a 30 minutos. Você pode inferir a quantidade de tempo que as tarefas têm para obtê-las olhando a duração de cada tarefa.

### <a name="use-of-cache"></a>Uso do cache

O parâmetro **Uso do cache** permite que você ajuste o processo de agendamento do planejamento mestre para ajudá-lo a melhorar a execução no conjunto de dados específico. Por exemplo, você pode ajustá-lo para obter os resultados a seguir:

- Se mais armazenamento em cache for feito, mais dados serão coletados na memória de dados. A expectativa é que os dados serão usados novamente mais tarde. Se os dados estiverem na memória, você pode salvar algumas solicitações do banco de dados. Entretanto, se mais armazenamento em cache for feito, aumentarão os requisitos de memória.
- Se menos armazenamento em cache for feito, os mesmos dados terão que ser buscados no banco de dados com mais frequência. Além disso, o Servidor de Objetos de Aplicativo (AOS) armazena poucos dados na memória por todo o processo.

É difícil prever a melhor opção porque cada caso dependerá não apenas dos dados, mas também do hardware. Por exemplo, como menos armazenamento em cache causa carga adicional no servidor de banco de dados, provavelmente não é recomendado usar essa opção se o servidor de banco de dados já estiver sobrecarregado.

Você pode definir o parâmetro **Uso do cache** na seção **Desempenho** na guia **Geral** da página **Parâmetros de planejamento mestre** (**Planejamento mestre \> Configuração \> Parâmetros de planejamento mestre**). A eficiência do armazenamento em cache depende muito dos dados do cliente. Por exemplo, se os dados armazenados em cache nunca forem necessários, você apenas desperdiçará memória se armazená-los até o final do processo de planejamento. Nesse caso, se você configurar menos armazenamento em cache, o desempenho poderá aumentar, porque o AOS requer menos memória e os recursos do servidor serão liberados para outras tarefas.

> [!TIP]
> Geralmente, recomendamos que você defina o parâmetro **Uso do cache** como **Máximo** porque o parâmetro é um recurso de aprimoramento de desempenho. Recomendamos que você defina o parâmetro como **Mínimo** se for executado no local e tiver memória limitada (aproximadamente 2 gigabytes \[GB\]).

### <a name="number-of-orders-in-firming-bundle"></a>Número de ordens em pacote de confirmação

O parâmetro **Número de ordens em pacote de confirmação** especifica o número total de ordens que serão processadas de cada vez por cada thread/lote. Ele causa paralelização do processo de confirmação automática.

Você pode definir o parâmetro **Número de ordens em pacote de confirmação** na seção **Desempenho** na guia **Geral** da página **Parâmetros de planejamento mestre** (**Planejamento mestre \> Configuração \> Parâmetros de planejamento mestre**). A paralelização do processo de confirmação automática é baseada nas ordens que devem ser processadas juntas. Por exemplo, se este parâmetro for definido como **50**, cada thread ou tarefa em lotes coletará 50 pedidos de cada vez e os processará juntos. Recomenda-se usar um processo da tentativa e erro para localizar o melhor valor. Entretanto, você pode usar a seguinte fórmula para calcular um valor inicial:

(Número de ordens por pacote) = (Número de itens de demanda ÷ Número de threads)

> [!NOTE]
> Se você definir o parâmetro **Número de ordens em pacote de confirmação** como **0** (zero), não ocorrerá paralelização do processo de confirmação automática. Todo o processo será executado em uma única tarefa em lotes e terá um tempo de execução cumulativo. Portanto, o tempo de execução do planejamento mestre aumentará. Por este motivo, recomendamos que você defina este parâmetro para um valor que seja maior que **0** (zero).

### <a name="time-fences"></a>Limites de tempo

Os limites de tempo especificam até que ponto, no futuro, os cálculos e outros requisitos devem ser calculados pelo planejamento mestre. Quanto maior o intervalo de tempo, mais tempo levará para que o planejamento mestre seja executado. Portanto, defina os intervalos de tempo de acordo com os requisitos de negócios. Para obter mais informações sobre intervalos de tempo, consulte [Configurar planejamento mestre](master-planning-setup.md).

### <a name="actions"></a>Ações

Entre os intervalos de tempo, você também pode localizar o parâmetro **Mensagem de ação**. O cálculo de mensagens de ação causa um tempo de execução mais longo para o planejamento mestre. Se as mensagens de ação não forem analisadas e aplicadas regularmente (diariamente, semanalmente e assim por diante), desative o cálculo durante a execução do planejamento mestre. Para desativar o cálculo, na página **Planos mestre** (**Planejamento mestre \> Configuração \> Planos \> Planos mestre**), defina o intervalo de tempo da **Mensagem de ação** como **0** (zero). Além disso, certifique-se de que a configuração **Mensagem de ação** esteja desativada para todos os grupos de cobertura.

### <a name="futures"></a>Futuros

O cálculo de futuros causa um tempo de execução mais longo para o planejamento mestre. Se estiver planejando BOMs, ou se os atrasos não tiverem que ser propagados do suprimento para a demanda durante o planejamento, desative os cálculos futuros durante o planejamento mestre. Para desativar os cálculos, defina os intervalos de tempo **Futuros** como **0** (zero) para o plano mestre que você está executando. Além disso, certifique-se de que a configuração **Futuros** está desativada para todos os grupos de cobertura.

## <a name="one-heavy-routine-at-a-time"></a>Uma rotina pesada de cada vez

Quando agendar um planejamento mestre, não agende nenhum outro trabalho em lotes ao mesmo tempo. Tenha bastante cuidado para não agendar outras rotinas pesadas, como o fechamento de estoque, ao mesmo tempo.

## <a name="review-the-session-log"></a>Revise o log da sessão

O sistema pode coletar informações adicionais sobre as tarefas executadas durante o planejamento mestre. Para que o sistema colete estas informações, ative a configuração **Rastrear tempo de processamento** na caixa de diálogo **Execução do planejamento mestre**. As informações coletadas podem ajudá-lo a encontrar gargalos na execução. Por exemplo, quando o parâmetro **Números de tarefas no pacote de tarefas do auxiliar** for definido como **1**, você pode identificar o item que tem o maior tempo de execução. Também é possível comparar o tempo de execução de vários threads que têm um status de **Cobertura** e comparar a duração de cada tarefa.

Para revisar as execuções do planejamento mestre de seu sistema, siga uma dessas etapas.

- No espaço de trabalho **Planejamento mestre** selecione um plano mestre no campo suspenso e, em seguida, no bloco **Planejamento mestre**, selecione **Histórico**. Selecione um trabalho, depois **Consultas** na Guia Rápida e, em seguida, **Duração de tarefa do processo**.
- Na página **Planos mestres** , selecione um plano no painel esquerdo e depois selecione, **Histórico** na Guia Rápida. Selecione um trabalho, depois **Consultas** na Guia Rápida e, em seguida, **Duração de tarefa do processo**.

Ao examinar o log da sessão, considere o seguinte:

- **Atualizar** não deve levar muito tempo (geralmente, pode levar até 30 minutos), porém é de thread único.
- **Copiar plano** não deve demorar muito tempo (deve demorar cerca de um minuto).
- **Confirmação automática** geralmente leva cerca de 30 minutos. No entanto, isso pode levar várias horas, dependendo do número de pedidos e da complexidade dos itens.
- **Confirmação automática** deve levar menos tempo do que **Cobertura**.
- **Cobertura** deve demorar mais tempo em relação ao resto.
- **Ação** e **Mensagem futura** pode demorar muito, dependendo dos dados e do número de BOMs.

## <a name="filtering-of-items"></a>Filtragem de itens

Filtros que são aplicados na caixa de diálogo **Execução do planejamento mestre** afetam a duração da execução do planejamento mestre. Vá para **Planejamento mestre \> Planejamento mestre \> Executar \> Planejamento mestre** ou selecione **Executar** no espaço de trabalho **Planejamento mestre**. Para excluir os itens da execução, recomendamos que você filtre por estado do ciclo de vida do item (não por números do item). Ao filtrar por estado do ciclo de vida, o processo de atualização leva menos tempo do que quando você filtra por números de item.

## <a name="automatically-filter-by-items-with-direct-demand"></a>Filtrar automaticamente pelos itens com demanda direta

Para melhorar o tempo de execução do planejamento mestre, você pode optar por incluir somente itens com demanda direta. Este filtro só pode ser usado para um planejamento mestre completo executado com nenhum outro filtro aplicado no campo **Registros a serem incluídos**. Uma execução de planejamento mestre com filtros ignorará a opção **Filtrar automaticamente pelos itens com demanda direta**.

O campo **Filtrar automaticamente pelos itens com demanda direta** é encontrado na página **Parâmetros de planejamento mestre** e pode ser usado com as configurações de pré-processamento e pós-processamento.

### <a name="pre-processing"></a>Pré-processamento
O **Pré-processamento: Filtrar automaticamente pelos itens com demanda direta** garante que a fase de pré-processamento do planejamento mestre só inclua itens que atendam a pelo menos uma das seguintes condições:
  - O item tem um recebimento ou uma saída esperado, como uma ordem de compra, ordem de venda, cotação, ordem de transferência ou ordem de produção. 
  - O item tem cobertura de item com estoque de segurança (estoque mínimo disponível).
  - A previsão de demanda após hoje existe para o item.
  - O fornecimento de previsão após hoje existe para o item.
  - O item inclui quaisquer linhas de continuidade do módulo de call center que ainda devem ser criadas.

> [!NOTE]
> Um item que esteja fisicamente disponível no estoque em andamento não mostrará uma transação de necessidade, pois não há demanda para o item.

### <a name="post-processing"></a>Pós-processamento
A opção **Pós-processamento: Filtrar automaticamente pelos itens com demanda direta** somente é relevante se você definir **Necessidade de versão da BOM** nos grupos de cobertura. Caso contrário, não será necessário habilitar o parâmetro. 

Antes de iniciar a etapa de cobertura, há uma etapa de pré-implementação durante a qual os itens com a configuração de cobertura **Necessidade de versão da BOM** habilitados serão reprocessados. Isso é feito para garantir que os itens da versão da BOM necessários sejam planejados. Os itens considerados para a demanda durante o pré-processamento não têm mais nenhuma demanda e, portanto, devem ser excluídos da execução de planejamento.

## <a name="performance-checklist-summary"></a>Resumo da lista de verificação de desempenho

- **Número de threads** – Defina para um valor maior que **0** (zero).
- **Números de tarefas no pacote de tarefas do auxiliar** – Defina para um valor que seja maior que **0** (zero). (Use as fórmulas fornecidas anteriormente neste tópico).
- **Uso do cache** – Defina como **Máximo**, a menos que seu sistema esteja com pouca memória.
- **Número de ordens em pacote de confirmação** – Defina um valor maior que **0** (zero). (Use a fórmula fornecida anteriormente neste tópico).
- **Limites de tempo** – Ajuste às suas necessidades comerciais.
- **Ações e futuros** – Desative ações e futuros, caso não os utilize.
- **Uma rotina pesada de cada vez** – Não execute o planejamento mestre junto com outra rotina pesada.
- **Revise o log da sessão.**
- **Filtragem de itens** – Use o estado do ciclo de vida para excluir itens da execução do planejamento mestre. (Não use os números do item).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]