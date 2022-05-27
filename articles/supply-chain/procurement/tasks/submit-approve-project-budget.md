---
title: Criar e enviar um fluxo de trabalho de orçamento do projeto
description: Este procedimento mostra como criar e enviar o orçamento para um projeto.
author: GalynaFedorova
ms.date: 11/22/2021
ms.topic: article
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e554fb578371f52f665ef348d6fa81fd27196a9e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671018"
---
# <a name="create-and-submit-a-project-budget-workflow"></a>Criar e enviar um fluxo de trabalho de orçamento do projeto

[!include [banner](../../includes/banner.md)]

Ao criar um orçamento do projeto, você pode inserir receitas e custos estimados para o projeto e usar os valores para controlar as transações reais do projeto. O orçamento do projeto requer que todos os orçamentos originais e revisões devem sejam enviados ao fluxo de trabalho do projeto para aprovação. O fluxo de trabalho aumenta o seu controle sobre o orçamento e cria um registro de histórico de alteração. Após [criar um projeto](/dynamicsax-2012/appuser-itpro/create-a-project), use este procedimento para criar e enviar o orçamento.

1. Vá para **Módulos** > **Gerenciamento e contabilidade do projeto** > **Projetos** > **Todos os projetos**.
1. Na lista de projetos, selecione o projeto.
1. Na página detalhes do projeto, selecione a guia **Plano**.
1. No grupo de **Orçamento**, selecione **Orçamento do projeto**.
1. Na Guia Rápida **Geral**, insira as seguintes informações:
   - Na caixa **Descrição**, digite um valor.
   - Selecione a opção para o **Orçamento original**.
   - Selecione a opção para o **Orçamento restante**.
1. Expanda a FastTab **Custos** e selecione **Novo**. Em seguida, defina as seguintes configurações:
   - Selecione uma opção para **Tipo de transação**.
   - Selecione uma **Categoria** apropriada.
   - Insira um valor no **Orçamento original**.
1. Expanda a FastTab **Receitas** e selecione **Novo**. Em seguida, defina as seguintes configurações:
   - Selecione uma opção para **Tipo de transação**.
   - Selecione uma **Categoria**.
   - Insira um valor para **Orçamento original**.
1. Selecione **Salvar**.
1. Selecione **Fluxo de trabalho \> Enviar**.
1. Na página **Revisar fluxo de trabalho de orçamento original - Enviar**, informe um **Comentário** e selecione **Enviar**.
