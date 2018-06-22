---
title: "Parâmetros de integração do Project Service Automation"
description: "Você pode configurar como os dados devem ser padronizados ao integrar o Project Service Automation com o Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 32f7f70c5b1071cef5a3360ccc09fa2d95fbf9a9
ms.contentlocale: pt-br
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation-integration-parameters"></a>Parâmetros de integração do Project Service Automation

Na página **Parâmetros de integração do Project Service Automation**, você pode configurar como os dados devem ser padronizados ao integrar o Project Service Automation com o Finance and Operations. As tarefas a seguir devem ser configuradas para que os projetos sejam sincronizados com êxito do Project Service Automation no Finance and Operations.

> [!NOTE]
> A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Dynamics 365 for Finance and Operations versão 8.0.




| **Guia**                      | **Campo**                          | **Descrição**                    |
|------------------------------|------------------------------------|--------------------------------|
| **Geral**                  | **Tipo de projeto padrão**               | Selecione o padrão de **Tipo de projeto**, quando os projetos serão sincronizados do Project Service Automation se você não tiver fornecido um valor padrão no modelo de integração. Durante a sincronização, os novos projetos terão **Tipo de projeto** definido com esse valor e poderão ser atualizados quando as linhas de contrato de projeto forem sincronizadas a partir do Project Service Automation.               |
| **Geral**                  | **Categoria de tempo**                      | Selecione o padrão de **Categoria de tempo**, quando as previsões de horas serão sincronizadas a partir do Project Service Automation. Durante a sincronização, novas previsões de horas do projeto no Finance and Operations terão a **Categoria** definida com esse valor quando as previsões de horas e números reais de horas forem sincronizados a partir do Project Service Automation.   |
| **Geral**                  | **Categoria da taxa**                       | Selecione o padrão de **Categoria de taxa**, quando os valores reais de taxas são sincronizadas a partir do Project Service Automation. Durante a sincronização, novas transações de taxa no Finance and Operations terão a **Categoria** definida com esse valor quando os valores reais de taxas forem sincronizados a partir do Project Service Automation.          |
| **Padrões de grupo de projetos**   | **Tipo de projeto** | Clique em **Novo** para adicionar uma linha na qual você possa selecionar o tipo de projeto para o qual definirá o grupo de projetos padrão. Um tipo de projeto específico pode ser selecionado apenas uma vez na configuração.              
|                              | **Grupo de projetos**          | Selecione o grupo de projetos padrão para o tipo de projeto especificado. Quando novos projetos forem sincronizados a partir do Project Service Automation, o **Grupo de projetos** será o padrão com base no tipo de projeto, caso você não tenha fornecido um valor padrão no modelo de integração.  |
| **Padrões de tipo de cobrança**    | **Tipo de cobrança** | Clique em **Novo** para adicionar uma linha na qual você possa selecionar o tipo de cobrança para o qual definirá a propriedade de linha padrão. Um tipo de cobrança específico pode ser selecionado apenas uma vez na configuração.          |
|                              | **Propriedade da linha**| Selecione a propriedade de linha padrão para o tipo de cobrança especificado. Quando novas previsões de horas, novas previsões de despesas ou os novos valores reais forem sincronizados a partir do Project Service Automation, a **Propriedade da linha** será o padrão com base no tipo de cobrança.          |
| **Bloqueio de funcionalidade**    |                   | Selecione a funcionalidade para desabilitar no Finance and Operations para projetos e contratos originados no Project Service Automation. Por exemplo, você pode optar por desativar a capacidade de editar contratos e projetos, criar estruturas de detalhamento de trabalho e inserir folhas de ponto no Finance and Operations. Os campos relacionados à contabilidade continuarão habilitados, mesmo se a configuração do parâmetro torná-los indisponíveis. Por padrão, todas as funcionalidades serão habilitadas.           |

