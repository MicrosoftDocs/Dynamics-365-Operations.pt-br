---
title: Parâmetros de gerenciamento de ativos
description: Em Gerenciamento de Ativos, os parâmetros gerais relacionadas a ativos, ordens de trabalho e ao agendamento de ordens de trabalho devem estar configurados.
author: josaw1
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99ef5169d2c6a31efd3e7a7c92beade994f6e5f5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252000"
---
# <a name="asset-management-parameters"></a>Parâmetros de gerenciamento de ativos

[!include [banner](../../includes/banner.md)]

Em Gerenciamento de Ativos, os parâmetros gerais relacionadas a ativos, ordens de trabalho e ao agendamento de ordens de trabalho devem estar configurados. Este tópico explica como configurá-los. Selecione **Gerenciamento de ativos** > **Configuração** > **Parâmetros de gerenciamento de ativos** para abrir a página.

> [!NOTE]
> Se você deseja configurar um sistema que inclua dados de demonstração para testar os recursos do Gerenciamento de ativos, consulte [Implantar um ambiente de demonstração](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) para instruções.

## <a name="the-assets-tab"></a>A guia Ativos

A guia **Ativos** fornece as seguintes configurações:

- **Local funcional padrão** é o local funcional padrão, que é selecionado automaticamente em ativos quando você cria novos ativos.  
- No campo **Calendário padrão**, selecione um calendário a ser usado para calcular KPIs de ativo, caso nenhum recurso seja selecionado em um ativo.  
- No campo **Exibir** , selecione a exibição padrão que é mostrada quando você abre **Exibição de ativo** (**Gerenciamento de ativos** > **Comum** > **Ativos** > **Exibição de ativo**).
- **Tipo de solicitação padrão** é o tipo de solicitação de manutenção padrão, que é selecionado automaticamente quando você cria uma nova solicitação.  
- As previsões sobre tipos de trabalho são armazenadas no projeto selecionado no campo **Previsão de projeto**. Para cada tipo de trabalho, uma nova atividade é criada automaticamente na previsão de projeto. As previsões do tipo de trabalho são salvas na previsão de projeto.  
- No campo **Modelo**, selecione o modelo de previsão usado em previsões de tipo de trabalho e ordem de serviço.

## <a name="the-work-orders-tab"></a>A guia Ordens de serviço

A guia **Ordens de serviços** fornece as seguintes configurações:

- **Tipo de ordem de serviço padrão** define as configurações padrão ao criar uma ordem de serviço.  
- **Tipo de ordem de serviço preventiva** define o tipo de ordem de serviço usado ao criar ordens de serviço a partir dos planos de manutenção. Se este campo estiver em branco, será usado o tipo da ordem de serviço no campo **Tipo de ordem de serviço padrão**.  
- No campo **Máscara da ordem de serviço relacionada**, você define o número máximo de ordens de serviço que podem ser relacionadas a uma ordem de serviço. Por exemplo, ## permite ter até 99 ordens de serviço relacionadas. Se você definir uma máscara conforme descrito aqui, as ordens de serviço relacionadas estarão numeradas [ID de ordem de serviço à qual uma ordem de serviço está relacionada]-01, -02, -03 etc. Se você não definir uma máscara neste campo, a ordem de serviço relacionada obterá a próxima ID sequencial da ordem de serviço.  
- Selecione **Sim** de **Copiar falhas** para copiar as falhas registradas automaticamente em ordens de serviço relacionadas a solicitações de manutenção. 
- No campo **Nível**, defina o nível de local funcional que é automaticamente inserido em uma ordem de serviço se todos os trabalhos de ordem de serviço relacionadas estiverem relacionadas ao mesmo local funcional. Se nem todos os trabalhos de ordem de serviço estiverem relacionados ao mesmo local funcional no nível definido, o campo **Local funcional** ficará em branco na ordem de serviço. Por exemplo, se você inserir o número "1" neste campo, que é o nível superior de uma estrutura de local funcional. Se você inserir o número "0" neste campo, significa que não definiu um nível de local funcional específico. Mas todos os trabalhos de ordem de serviço em uma ordem de serviço devem estar relacionados ao mesmo local funcional para que esse local funcional seja adicionado à ordem de serviço.  
- Diários usados para lançar consumo em uma ordem de serviço podem ser selecionados na Guia Rápida **Geral** nos campos **Hora**, **Item** e **Despesa**.  
- No campo **Origem de idioma de produto**, selecione o idioma a ser usado para nomes de produto em Gerenciamento de Ativos. Você pode selecionar o idioma configurado na conta da empresa ou a configuração de idioma para o usuário atualmente conectado.  
- Selecione **Yes** de **Atualização em tempo real** se desejar atualizar automaticamente alterações com os padrões do tipo de trabalho, os planos de manutenção e os rounds de manutenção.
  - Se você selecionar **Não**, as alterações nos padrões de tipo de trabalho, planos de manutenção e rounds de manutenção não serão atualizadas automaticamente em Gerenciamento de Ativos.
  - Selecione **Não** no botão de alternância se tiver grandes quantidades de dados sendo sincronizadas; por exemplo, vários ativos ou locais funcionais configurados em planos ou rounds de manutenção, ou um grande número de planos ou rounds de manutenção.  
  - Se você fizer alterações em padrões de tipo de trabalho, em planos de manutenção ou em rounds de manutenção, tiver selecionado **Não** para a atualização em tempo real, um aviso talvez não seja exibido se as alterações influenciarem:
    - Configuração de locais funcionais em planos ou rounds de manutenção  
    - Configuração de objetos em planos ou rounds de manutenção  
    - Configuração de planos de manutenção  
    - Configuração de rounds de manutenção  
- Na Guia Rápida **Categoria**, as categorias padrão relativas ao consumo em ordens de serviço podem ser definidas.  

## <a name="the-work-order-scheduling-tab"></a>A guia Agendamento da ordem de serviço

A guia **Agendamento da ordem de guia** fornece as seguintes configurações na guia rápida **Geral**:

- **Limite de tempo de agenda** define o período em dias, calculado da data de início esperada da ordem de serviço, em que trabalhos de ordem de serviço são planejados.  
- O **Plano mestre** se refere a recursos no módulo **Administração da organização**. Se você selecionar um plano mestre neste campo, poderá ver as reservas de capacidade relacionadas a ordens de serviço em **Reservas de capacidade** (**Administração de organização** > **Recursos** > **Recursos** > selecionar recurso > guia **Recurso** > botão **Reservas de capacidade**). Se você deixar este campo em branco, poderá ver a capacidade máxima relacionada a ordens de serviço em **Capacidade máxima** (**Administração da organização** \> **Recursos** \> **Recursos** \> selecionar recurso \> guia **Recurso** \> botão **Capacidade máxima**).  

>[!NOTE]
>A seleção em relação ao uso de um plano mestre no módulo **Gerenciamento de ativos** e o formulário relacionado usado para obter uma visão geral das reservas de capacidade ou de capacidade máxima seguem a configuração padrão. Dependendo de sua configuração no campo **Plano mestre**, você poderá acessar informações de capacidade em **Reservas de capacidade** ou **Capacidade máxima** no módulo **Administração da organização**. Não é possível criar uma configuração em que reservas de capacidade sejam mostradas em ambas as exibições.  

Os campos descritos na lista abaixo listam todas as classificações calculadas, que são usadas para calcular a prioridade da ordem de serviço durante o agendamento da ordem de serviço.

- **Prioridade** - Uma pontuação de classificação calculada juntamente com a pontuação de classificação nos campos **Severidade** e **Data inicial**. O número neste campo é dividido pelo número no campo **Prioridade** em uma ordem de serviço. Por exemplo, se o valor "5,00" for inserido neste campo e uma ordem de serviço tiver prioridade "20", a pontuação de classificação para prioridade será 0,25.  
- **Severidade** - Uma pontuação de classificação calculada juntamente com a pontuação de classificação nos campos **Prioridade** e **Data inicial**. O número neste campo é multiplicado pelo número no campo **Severidade** em uma ordem de serviço. Por exemplo, se o valor "10,00" for inserido neste campo e uma ordem de serviço tiver severidade "5", a pontuação de classificação para severidade será 50.  
- **Data inicial** - Uma pontuação de classificação calculada juntamente com a pontuação de classificação nos campos **Prioridade** e **Severidade**. Este campo indica a pontuação diária como um valor negativo e é comparado ao campo **Início esperado** em uma ordem de serviço. Por exemplo, se o valor "10,00" for inserido neste campo e a data de início esperada de uma ordem de serviço for daqui a três dias, o resultado da classificação será menos 30,00. A adição dos resultados de 0,25 e 50 dos exemplos nos campos **Prioridade** e **Severidade** descritos acima oferece um total de mais 20,25. O número é comparado a todas as outras pontuações de classificação de ordem de serviço durante o agendamento da ordem de serviço. As pontuações de classificação mais altas são planejadas primeiro.  
- **Trabalhador responsável** - Uma pontuação classificada calculada junto com os valores de pontuação de classificação **Grupo de trabalhadores responsáveis**, **Trabalhador preferido**, **Grupo de trabalhadores preferidos**, **Local do ativo** e **Data inicial**. Se o valor "50,00" for inserido neste campo e um trabalhador responsável for selecionado em uma ordem de serviço, o trabalhador terá 50 pontos no cálculo de trabalho geral durante o agendamento da ordem de serviço.  
- **Grupo de trabalhadores responsáveis** - Uma pontuação classificada calculada junto com os valores de pontuação de classificação **Grupo de trabalhadores responsáveis**, **Trabalhador preferido**, **Grupo de trabalhadores preferidos**, **Local do ativo** e **Data inicial**. Se o valor "50,00" for inserido neste campo e um trabalhador responsável for selecionado em uma ordem de serviço, o trabalhador terá 50 pontos no cálculo de trabalho geral durante o agendamento da ordem de serviço.  
- **Limitar ao responsável** - Limita o número de trabalhadores disponíveis para o agendamento de ordem de serviço. Selecione **Não** se desejar calcular uma pontuação para todos os trabalhadores, independentemente de estarem configurados como trabalhadores responsáveis ou fazerem parte de um grupo de trabalhadores responsáveis. Selecione **Sim** se desejar calcular uma pontuação para trabalhadores que estão configurados como trabalhador responsável na ordem de serviço e/ou incluídos em um grupo de trabalhadores responsáveis selecionado na ordem de serviço.  
- **Trabalhador preferido** - Uma pontuação classificada calculada junto com os valores de pontuação de classificação **Grupo de trabalhadores responsáveis**, **Trabalhador preferido**, **Grupo de trabalhadores preferidos**, **Local do ativo** e **Data inicial**. As quatro pontuações de classificação são calculadas e adicionadas juntas para fornecer uma pontuação usada para selecionar que trabalhador deve ser atribuído à qual ordem de serviço durante o agendamento de ordem de serviço. Se o valor "10,00" for inserido neste campo e um trabalhador for selecionado como trabalhador preferido em uma ordem de serviço, o trabalhador terá 10 pontos no cálculo de trabalhador geral durante o agendamento da ordem de serviço.  
- **Grupo de trabalhadores preferidos** - Uma pontuação classificada calculada junto com os valores de pontuação de classificação **Grupo de trabalhadores responsáveis**, **Trabalhador preferido**, **Grupo de trabalhadores preferidos**, **Local do ativo** e **Data inicial**. Se o valor "10,00" for inserido neste campo e um trabalhador for atribuído a um grupo de trabalhadores preferidos selecionado em uma ordem de serviço, o trabalhador terá 10 pontos no cálculo de trabalhador geral durante o agendamento da ordem de serviço.  
- **Limitar ao preferido** - Limita o número de trabalhadores disponíveis para o agendamento de ordem de serviço. Selecione **Não** se desejar calcular uma pontuação para todos os trabalhadores, independentemente de estarem configurados como trabalhadores preferidos ou fazerem parte de um grupo de trabalhadores preferidos. Selecione **Sim** se apenas você desejar calcular uma pontuação para os trabalhadores configurados como trabalhadores preferidos e/ou incluídos em um grupo de trabalhadores preferidos.  
- **Local** - Uma pontuação classificada calculada junto com os valores de pontuação de classificação **Grupo de trabalhadores responsáveis**, **Trabalhador preferido**, **Grupo de trabalhadores preferidos**, **Local do ativo** e **Data inicial**. Se o valor "3.000,00" for inserido neste campo, um trabalhador terá 3.000 pontos no cálculo se ele estiver localizado na mesma fábrica ou instalação que o ativo em que um trabalho será agendado.  
  - Se sua empresa usar locais funcionais, os trabalhadores receberão a pontuação total se estiverem no local funcional relacionado ao ativo. Se o local funcional do ativo tiver um ativo principal, os funcionários desse local funcional obterão 1/2 da pontuação. Se esse local também tiver um responsável, os trabalhadores desse local obterão 1/3 da pontuação. Se esse local também tiver um responsável, os trabalhadores desse local obterão 1/4 da pontuação e assim por diante.  
  - Se sua empresa usar o local do ativo, o que não recomendamos, o local, a área e a zona serão usados para calcular pontuações do local. Os trabalhadores receberão a pontuação total se estiverem no local, na área e na zona relacionados ao ativo. Se o local do trabalhador corresponder apenas ao local e à área, a pontuação de classificação para o trabalhador será 2/3 da pontuação total. Se o local do trabalhador corresponder apenas ao local, a pontuação de classificação para o trabalhador será 1/3 da pontuação total.  
- **Limitar ao local** - Limita o número de trabalhadores disponíveis para o agendamento de ordem de serviço. Selecione **Não** se desejar calcular uma pontuação para todos os trabalhadores em todos os locais funcionais. Selecione **Sim** se você apenas quiser calcular uma pontuação para os trabalhadores associados ao local funcional da ordem de serviço.

>[!NOTE]
>Os campos "Limitar a" aceleram o agendamento da ordem de serviço, limitando o número de pontos calculados para trabalhadores.

**Data inicial do trabalhador** - Uma pontuação classificada calculada junto com os valores de pontuação de classificação **Grupo de trabalhadores responsáveis**, **Trabalhador preferido**, **Grupo de trabalhadores preferidos**, **Local do ativo** e **Data inicial**. Este campo indica a pontuação diária como um valor negativo e é comparado ao campo **Início esperado** em uma ordem de serviço. Exemplo: Se o valor "10,00" for inserido neste campo e a data de início esperada de uma ordem de serviço for amanhã, o resultado da classificação será menos 10,00.

  - Supondo que nenhum trabalhador responsável e do grupo de trabalhadores responsável foram selecionados em uma ordem de serviço para agendamento - você adiciona e subtrai os valores de pontuação de classificação dos exemplos nos campos acima **Trabalhador preferido**, **Grupo de trabalhadores preferidos**, **Local do ativo** e **Data inicial**, obtendo um total de 3.010,00. Isso significa uma alta pontuação para o trabalhador que já está selecionado como trabalhador preferido e também incluído no grupo de trabalhadores preferidos na ordem de serviço. O trabalhador está localizado também na mesma instalação que o ativo para o qual o trabalho precisa ser agendado. Isso significa que há uma grande possibilidade de o trabalhador em questão ser selecionado para concluir o trabalho durante o agendamento da ordem de serviço.  
  - Se o valor "0,00" for inserido em um dos oito campos anteriores, a pontuação de classificação não será usada durante o agendamento da ordem de serviço.  

## <a name="the-document-types-tab"></a>A guia Tipos de documento

Selecione os tipos de documentos que devem estar disponíveis para imprimir anexos relacionados a um relatório de ordem de serviço. Isso é feito selecionando um tipo de documento na seção **Disponível** e selecionando ![seta para frente](media/15-setup-for-objects.png). Se desejar remover um tipo de documento selecionado, selecione o tipo de documento na seção **Selecionado** e selecione ![seta voltar](media/16-setup-for-objects.png) .

## <a name="the-number-sequences-tab"></a>A guia Sequências numéricas

Selecione as sequências numéricas necessárias nesta seção. Há duas sequências numéricas para ativos: uma para ativos criados manualmente e outra para ativos criados por meio de ativos pendentes.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]