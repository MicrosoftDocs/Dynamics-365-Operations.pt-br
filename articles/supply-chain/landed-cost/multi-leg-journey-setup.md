---
title: Configuração de percurso de vários trechos
description: Este tópico descreve como configurar percursos de vários trechos para o módulo de Custo de entrega.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMLegTable, ITMJourneyTable, ITMActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e1377b7453622e5bed711753fc2d99258d3c5951
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833752"
---
# <a name="multi-leg-journey-setup"></a>Configuração de percurso de vários trechos

[!include [banner](../../includes/banner.md)]

Este tópico descreve como configurar percursos de vários trechos para o módulo de **Custo de entrega**.

## <a name="legs"></a>Itinerários

Os trechos são usados para identificar partes separadas de um percurso. Cada trecho é criado ao selecionar portas de envio "para" e "de" e o método de transporte usado para esse trecho. Os prazos de entrega podem ser associados a cada trecho. Os prazos de entrega podem ajudar a rastrear uma remessa e também podem ser usados para calcular a data de entrega estimada dos bens em uma viagem. Além disso, quando um trecho de um percurso é concluído, o status da viagem, o contêiner de embarque e as linhas da ordem de compra associada podem ser atualizados por meio da configuração do controle de rastreamento. Os trechos podem ser usados por um único modelo de percurso ou podem ser reutilizados por vários modelos de percurso. Carregamento de contêineres, alfândega e transporte local são geralmente configurados como trechos e uma porta de envio não específica é usado para eles.

Para trabalhar com trechos, acesse **Custo de entrega \> Configuração de percurso de vários trechos \> Trechos**. Dessa forma, será possível exibir, abrir, criar e excluir registros de trechos. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Itinerário | Digite um identificador exclusivo para o nome/número do trecho do percurso. |
| descrição | Insira uma descrição do trecho do percurso. Normalmente, essa descrição identifica as portas "de" e "para" ou a etapa do percurso. |
| Porta de origem | Insira o ponto de origem das mercadorias no trecho. |
| Porta de destino | Insira o ponto de destino das mercadorias no trecho. |
| Método de entrega | Insira o método de transporte do trecho. |

## <a name="journey-templates"></a>Modelos de percurso

Um modelo de percurso define o percurso de vários trechos entre duas portas pelas quais as mercadorias percorrem durante uma viagem. Os trechos do percurso são combinados para identificar o tempo necessário para que as mercadorias percorram todo o trajeto, desde o ponto de origem do fornecedor até o depósito de destino final. Quando os trechos são inseridos no modelo de percurso em uma ordem específica, os prazos de entrega identificarão a data de cada trecho e status do trajeto, do contêiner e das linhas de compra do trajeto. Use o [Centro de controle de acompanhamento](delivery-information-setup.md) para configurar os prazos de entrega associados a cada trecho que compõe o modelo de percurso. O modelo do percurso também é usado quando os custos automáticos de um trajeto são configurados. Quando o percurso é definido, o custo associado ao transporte de mercadorias pode ser definido na página de custos automáticos.

Para trabalhar com modelos de percurso, acesse **Custo de entrega \> Configuração de percurso de vários trechos \> Modelos de percurso**. Dessa forma, será possível exibir, abrir, criar e excluir modelos de percurso.

Para cada modelo de percurso, defina os seguintes campos no cabeçalho.

| Campo | descrição |
|---|---|
| Modelo de diário | Digite um identificador exclusivo para o nome/número do modelo do percurso. O modelo do percurso geralmente descreve o ponto de origem e o ponto de destino do percurso. |
| descrição | Insira uma descrição do modelo do percurso. A descrição geralmente indica as portas "de" e "para" e o tipo de percurso. |

Na seção **Linhas**, adicione uma linha para cada trecho da jornada e coloque as linhas em ordem. Use as setas **Para cima** e **Para baixo** na barra de ferramentas para alterar a ordem das linhas. A tabela a seguir descreve os campos disponíveis para cada linha.

| Campo | descrição |
|---|---|
| Itinerário | Selecione um trecho a ser adicionado ao percurso. |
| descrição | A descrição do trecho. |
| Porta de origem | A porta que é o ponto de origem das mercadorias no trecho. Esta porta é a porta "para", que é usada para determinar os custos automáticos de um trajeto. |
| Porta de destino | A porta de destino final das mercadorias no trecho. |
| Modo de entrega | O modo de entrega que é usado para o trecho. |
| Percurso da porta | Se a porta especificada para o trecho for usada para determinar os custos automáticos, marque esta caixa de seleção para identificá-la como a porta "percurso de". Esta porta será mostrada no cabeçalho do trajeto. |
| Percurso até a porta | Se a porta especificada para o trecho for usada para determinar os custos automáticos, marque esta caixa de seleção para identificá-la como a porta "percurso para". Esta porta será mostrada no cabeçalho do trajeto. |
| Empresa transportadora | Selecione a empresa transportadora usada para o trecho. |

## <a name="activities"></a>Atividades

As configurações na página **Atividades** estabelecem os tipos de atividades que podem ocorrer na porta de destino de um trecho. Os usuários que trabalham na página **Todos os contêineres de remessa** podem selecionar entre esses valores quando estimarem a duração de cada atividade e registrarem a duração real para fins de comparação.

Para configurar as atividades, acesse **Custo de entrega \> Configuração de percursos de vários trechos \> Atividades**. Em seguida, você pode adicionar, remover e editar atividades usando os botões no Painel de Ações.

A tabela a seguir descreve os campos disponíveis para cada atividade na grade.

| Campo | descrição |
|---|---|
| Atividade | O nome da atividade. |
| descrição | Uma descrição da atividade. |
| Empresa transportadora | A conta do fornecedor da empresa transportadora associada à atividade. |
