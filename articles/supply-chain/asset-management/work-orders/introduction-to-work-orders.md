---
title: Introdução a ordens de serviço
description: Este tópico oferece uma visão geral de ordens de serviço no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b8340d3f4fd98e02e372fd5ac68f1ae107819304
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626399"
---
# <a name="introduction-to-work-orders"></a>Introdução a ordens de serviço

[!include [banner](../../includes/banner.md)]



As ordens de serviço são usadas para gerenciar trabalhos de manutenção, fornecer as informações necessárias sobre eles e registrar o consumo neles. Cada ordem de serviço pode conter um ou mais trabalhos de ordem de serviço e um ou mais ativos podem ser conectados a cada ordem de serviço. Cada trabalho de ordem de serviço define um trabalho de manutenção agendado no ativo.

As ordens de serviço podem ser criadas das seguintes maneiras:

- Para planos de manutenção baseados em calendário, nos quais a configuração "Criação automática" é ativada automaticamente, usando [Agendar planos de manutenção](../preventive-and-reactive-maintenance/schedule-maintenance-plans.md).

- Para rounds de manutenção em que a configuração "Criação automática" é ativada automaticamente, usando [Agendar rounds de manutenção](../preventive-and-reactive-maintenance/maintenance-rounds.md).

- Para trabalhos de manutenção preventivos ou solicitações de manutenção, em [Agendamento de manutenção](../preventive-and-reactive-maintenance/maintenance-schedule.md).

- Manualmente

- Na página **Todas as solicitações de manutenção**, **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção de local funcional**.

>[!NOTE]
>Os trabalhos de ordem de serviço relacionados ao mesmo ativo estão relacionados à mesma ID de projeto.

## <a name="all-work-orders"></a>Todas as ordens de serviço

Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** para abrir a página de listagem **Todas as ordens de serviço**. Esta página mostra todas as ordens de serviço e algumas das informações relacionadas a cada um.

A ilustração a seguir mostra um exemplo da página de listagem **Todas as ordens de serviço**.

![Figura 1](media/01-work-orders.png)

Para exibir uma lista apenas de ordens de serviço ativas, selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Ordens de serviço ativas**. 

Para exibir uma lista de trabalhos de ordem de serviço que contêm ativos instalados em locais funcionais aos quais você está relacionado como trabalhador, selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Meus trabalhos de manutenção da ordem de serviço do local funcional**. (A relação entre trabalhadores e locais funcionais é configurada na página **Trabalhadores**. Para obter mais informações, consulte [Trabalhadores de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md)).

Aqui estão algumas maneiras pelas quais você pode usar a página **Todas as ordens de serviço**:

- Na exibição de grade, selecione um link na coluna **Ordem de serviço** para mostrar a exibição de detalhes do registro selecionado. Você pode selecionar **Editar** para abrir o registro para edição.

- Na exibição de detalhes, você verá informações detalhadas relacionadas à ordem de serviço.  

- Na exibição de detalhes, selecione a guia **Linhas** para ver os detalhes do trabalho da ordem de serviço ou selecione a guia **Cabeçalho** para ver os detalhes da ordem de serviço.  

- Expanda o painel **Informações relacionadas** no lado direito da página para ver informações adicionais relacionadas à ordem de serviço selecionada.

A ilustração a seguir mostra um exemplo da exibição de detalhes **Todas as ordens de serviço**.

![Figura 2](media/02-work-orders.png)


Os botões no Painel de Ação estão organizados em guias. A tabela a seguir descreve brevemente os botões relacionados ao Gerenciamento de Ativos:



| Nome do botão                     | Descrição                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Edição                            | Edite a ordem de serviço selecionada.                                                                                                                                                                                                                                           |
| Novos                             | Crie uma ordem de serviço.                                                                                                                                                                                                                                                  |
| Delete                          | Exclua a ordem de serviço selecionada.                                                                                                                                                                                                                                         |
| Grupo de ordens de serviço                 | Adicione a ordem de serviço selecionada a um grupo de ordens de serviço ou remova-o do grupo de ordens de serviço.                                                                                                                                                                                           |
| Ajustar                          | Ajuste as informações sobre o início e o final esperado, nível de serviço, funcionário de manutenção responsável ou grupo de funcionários responsáveis nas ordens de serviço selecionadas.                                                                                                                                     |
| Ordem de serviço relacionada              | Crie uma ordem de serviço relacionada ao trabalho selecionado. Isso é útil se você deseja registrar ordens de serviço primárias e secundárias.                                                                                                                              |
| Copiar ordem de serviço                 | Crie uma ordem de serviço com base em uma ordem de serviço existente.                                                                                                                                                                                                               |
| Histórico de eventos                   | Veja o histórico de registro da ordem de serviço.                                                                                                                                                                                                                |
| Anotações do trabalho de manutenção da ordem de serviço                           | Crie uma descrição em uma ordem de serviço ou insira notas ou comentários nela. Primeiro, selecione **Adicionar o carimbo de data/hora** para adicionar seu nome de usuário e um carimbo de data/hora à nota. As notas são mostradas na guia **Descrição** da guia rápida **Detalhes da linha** da página **Ordem de serviço**.         |
| Ferramentas                           | Crie uma lista de ferramentas necessárias em uma ordem de serviço. As ferramentas são configuradas como recursos em **Administração da organização** > **Recursos** > **Recursos**.                                                                                                      |
| Lista de verificação de manutenção           | Veja a lista de verificação do ativo conectado à ordem de serviço.                                                                                                                                                                                                              |
| Falha do ativo                     | Exiba ou registre informações de falha em um ativo. Essas informações serão usadas para gerenciamento de falhas.                                                                                                                                                                                      |
| Tempo de inatividade de manutenção            | Especifique o tempo de inatividade de manutenção para uma ordem de serviço.                                                                                                                                                                                                                               |
| Avaliação de condição            | Registre medições de avaliação de condição em uma ordem de serviço.                                                                                                                                                                                                             |
| Contadores de ativos                 | Crie ou exiba registros de contador no ativo.                                                                                                                                                                                                                     |
| Previsão                        | Exiba ou crie previsões em uma ordem de serviço.                                                                                                                                                                                                                               |
| Diários                        | Exiba ou crie diários de ordem de serviço. As linhas do diário podem ser copiadas das previsões.                                                                                                                                                                                         |
| Transações do Projeto            | -Veja todas as transações lançadas relacionadas a ordens de serviço criadas para o ativo.                                                                                                                                                                                             |
| Atualizar o estado da ordem de serviço           | Atualize o estado do ciclo de vida da ordem de serviço.                                                                                                                                                                                                                                                |
| Log de estados de ciclo de vida                      | Exiba um log que mostre os estados do ciclo de vida da ordem de serviço selecionada.                                                                                                                                                                                                                   |
| Documentos do ativo                | Veja a lista de documentos anexados aos ativos relacionados a uma ordem de serviço. Esses documentos estão configurados em **Gerenciamento de ativos** > **Configuração** > **Documentos do ativo**.                                                                                                 |
| Plano                        | Agende as ordens de serviço selecionadas.                                                                                                                                                                                                                                      |
| Expedir            | Agende a ordem de serviço selecionada para um funcionário.                                                                                                                                                                                                                        |
| Excluir agenda                 | Exclua o agendamento da ordem de serviço selecionado.                                                                                                                                                                                                                          |
| Trabalhos de manutenção da ordem de serviço agendados             | Abra a página da lista **Trabalhos de manutenção de ordens de serviço agendadas**.                                                                                                                                                                                                                             |
| Requisição de compra da ordem de serviço | Abra a página da lista **Requisição de compra de ordem de serviço**.                                                                                                                                                                                                                 |
| Compra da ordem de serviço             | Abra a página da lista **Compra de ordem de serviço**.                                                                                                                                                                                                                             |
| Controle de Custo                    | Compare custos reais e de orçamento na ordem de serviço.                                                                                                                                                                                                                |
| Controle de horas                    | Compare as horas previstas e as horas reais na ordem de serviço.                                                                                                                                                                                                                |
| Relatório de ordens de serviço               | Imprima um relatório de ordem de serviço.                                                                                                                                                                                                                                                |
| Consumo da ordem de serviço          | Imprima um relatório de consumo.                                                                                                                                                                                                                                               |


Os botões no grupo **Projeto** na guia **Ordem de serviço** do Painel de Ação estão relacionados à funcionalidade de previsões, diários e faturamento no módulo **Gerenciamento e contabilidade do projeto**.

>[!NOTE]
>Para incluir previsões criadas em uma ordem de serviço ao executar o agendamento do planejamento mestre, use o modelo de previsão selecionado na página **Parâmetros de gerenciamento de ativos**.

