---
title: Introdução a ordens de serviço
description: Este tópico oferece uma visão geral de ordens de serviço no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9483c50a15fca566b1f5e089297795bbbe09c042
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875512"
---
# <a name="introduction-to-work-orders"></a>Introdução a ordens de serviço

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

As ordens de serviço são usadas para realizar gerenciamento, fornecer as informações necessárias e registrar o consumo nos trabalhos de manutenção. Uma ordem de serviço pode conter um ou mais trabalhos de ordem de serviço e um ou mais ativos podem ser conectados a uma ordem de serviço. Cada linha da ordem de serviço define um trabalho de manutenção agendado no ativo.

As ordens de serviço podem ser criadas automática ou manualmente:

- Usando automaticamente o formulário **Agendar planos de manutenção**, para planos de manutenção baseados em calendário definidos como "Criação automática".  

- Usando automaticamente o formulário **Agendar rounds de manutenção**, para rounds de manutenção definidos como "Criação automática".  

- Crie usando o agendamento de manutenção, que pode consistir em solicitações de manutenção ou trabalhos de manutenção preventivos.  

- Crie uma ordem de serviço manualmente.  

- Crie uma ordem de serviço usando **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção de local funcional**.

>[!NOTE]
>Os trabalhos de ordem de serviço relacionados ao mesmo ativo estão relacionados à mesma ID de projeto.

## <a name="all-work-orders"></a>Todas as ordens de serviço

Clique em **Gerenciamento de ativo** > **Comum** > **Ordens de serviço** > **Todas as ordens de trabalho** para abrir a lista. **Todas as ordens de serviço** contêm uma lista de todas as ordens de serviço e exibe algumas das informações relacionadas a uma ordem de serviço.

![Figura 1](media/01-work-orders.png)

- Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Ordens de serviço ativas** para ver uma lista de ordens de serviço ativas.

- Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Meus trabalhos de manutenção da ordem de serviço do local funcional** para ver uma lista de trabalhos de ordem de serviço contendo ativos instalados em locais funcionais, você está relacionado como funcionário (configurado em [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md)).

- Na lista **Todas as ordens de trabalho** (exibição de grade), clique em um link na coluna **Ordem de serviço** para mostrar a exibição Detalhes do registro selecionado. Clique no botão **Editar** para abrir para edição.  

- Na exibição Detalhes, você verá informações detalhadas relacionadas à ordem de serviço.  

- Na exibição Detalhes, selecione o link **Linhas** para ver os detalhes do trabalho da ordem de serviço ou selecione o link **Cabeçalho** para ver os detalhes da ordem de serviço.  

- O painel vertical **Informações relacionadas** à direita da tela contém informações adicionais relacionadas à ordem de serviço. Expanda o painel para ver informações relacionadas à ordem de serviço selecionada.  


![Figura 2](media/02-work-orders.png)


Os botões do painel de ações são organizados em guias no painel de ações. Veja uma breve descrição dos botões relacionados ao gerenciamento de ativos da empresa:



| Nome do botão                     | Descrição                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Edição                            | Edite a ordem de serviço selecionada.                                                                                                                                                                                                                                           |
| Novos                             | Crie uma ordem de serviço.                                                                                                                                                                                                                                                  |
| Excluir                          | Exclua a ordem de serviço selecionada.                                                                                                                                                                                                                                         |
| Grupo de ordens de serviço                 | Adicione a ordem de serviço selecionada a um grupo de ordens de serviço ou remova-o do grupo de ordens de serviço.                                                                                                                                                                                           |
| Ajustar                          | Ajuste as informações sobre o início e o final esperado, nível de serviço, funcionário de manutenção responsável ou grupo de funcionários responsáveis nas ordens de serviço selecionadas.                                                                                                                                     |
| Ordem de serviço relacionada              | Crie uma ordem de serviço relacionada ao trabalho selecionado. Isso é útil se você deseja registrar ordens de serviço primárias e secundárias.                                                                                                                              |
| Copiar ordem de serviço                 | Crie uma ordem de serviço com base em uma ordem de serviço existente.                                                                                                                                                                                                                |
| Histórico de eventos                   | Veja o histórico de registro na ordem de serviço.                                                                                                                                                                                                                |
| Anotações do trabalho de manutenção da ordem de serviço                           | Crie uma descrição ou insira notas ou comentários em uma ordem de serviço. Comece clicando no botão **Adicionar o carimbo de data/hora** para adicionar seu nome de usuário e um carimbo de data/hora à nota. As notas são exibidas no formulário **Ordem de serviço** > Guia Rápida **Detalhes da linha** > guia **Descrição**. |
| Ferramentas                           | Crie uma lista de ferramentas necessárias em uma ordem de serviço. As ferramentas são configuradas como recursos em **Administração da organização** > **Comum** > **Recursos** > **Recursos**.                                                                                                      |
| Lista de verificação de manutenção           | Veja a lista de verificação do ativo conectado à ordem de serviço.                                                                                                                                                                                                              |
| Falha do ativo                     | Exiba ou registre informações de falha em um ativo a ser usado para gerenciamento de falhas.                                                                                                                                                                                        |
| Tempo de inatividade de manutenção            | Especifique o tempo de inatividade de manutenção para uma ordem de serviço.                                                                                                                                                                                                                               |
| Avaliação de condição            | Registre medições de avaliação de condição em uma ordem de serviço.                                                                                                                                                                                                             |
| Contadores de ativos                 | Crie ou exiba registros de contador no ativo.                                                                                                                                                                                                                     |
| Previsão                        | Exiba ou crie previsões em uma ordem de serviço.                                                                                                                                                                                                                               |
| Diários                        | Exiba ou crie diários de ordem de serviço. As linhas do diário podem ser copiadas das previsões.                                                                                                                                                                                         |
| Transações do Projeto            | Veja todas as transações lançadas relacionadas a ordens de serviço criadas para o ativo.                                                                                                                                                                                             |
| Atualizar o estado da ordem de serviço                | Atualize o estado do ciclo de vida da ordem de serviço.                                                                                                                                                                                                                                                |
| Log de estados de ciclo de vida                       | Log exibindo os estados do ciclo de vida da ordem de serviço selecionada.                                                                                                                                                                                                                   |
| Documentos do ativo                | Veja a lista de documentos anexados aos ativos relacionados a uma ordem de serviço. Esses documentos estão configurados em **Gerenciamento de ativos** > **Configuração** > **Documentos do ativo**.                                                                                                 |
| Plano                        | Agende as ordens de serviço selecionadas.                                                                                                                                                                                                                                      |
| Expedir            | Agende a ordem de serviço selecionada para um funcionário.                                                                                                                                                                                                                        |
| Excluir agenda                 | Exclua o agendamento da ordem de serviço selecionado.                                                                                                                                                                                                                          |
| Trabalhos de manutenção da ordem de serviço agendados             | Abra a página da lista **Trabalhos de manutenção de ordens de serviço agendadas**.                                                                                                                                                                                                                             |
| Requisição de compra da ordem de serviço | Abra a página da lista **Requisição de compra de ordem de serviço**.                                                                                                                                                                                                                 |
| Compra da ordem de serviço             | Abra a página da lista **Compra de ordem de serviço**.                                                                                                                                                                                                                             |
| Controle de Custo                    | Compare custos reais e de orçamento na ordem de serviço.                                                                                                                                                                                                                |
| Controle de horas                    | Compare as horas previstas e as horas reais na ordem de serviço.                                                                                                                                                                                                                |
| Relatório de ordens de serviço               | Imprima o relatório de ordem de serviço.                                                                                                                                                                                                                                                |
| Consumo da ordem de serviço          | Imprima o relatório de consumo.                                                                                                                                                                                                                                               |


Os botões na guia **Ordem de serviço** > **Projeto** estão relacionados à funcionalidade no módulo **Gerenciamento e contabilidade do projeto** em relação a previsões, diários e faturamento.

>[!NOTE]
>As previsões criadas em uma ordem de serviço podem ser incluídas durante a execução do agendamento do planejamento mestre usando o modelo de previsão selecionado no formulário **Parâmetros de gerenciamento de ativos**.

