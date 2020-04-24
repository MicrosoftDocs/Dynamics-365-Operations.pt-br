---
title: Introdução aos ativos
description: Este tópico oferece uma visão geral de ativos em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2e5f3e4f428a231760b1169a860b230c1a76a64e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212655"
---
# <a name="introduction-to-assets"></a>Introdução aos ativos

[!include [banner](../../includes/banner.md)]

 

Este tópico oferece uma visão geral de ativos em Gerenciamento de Ativos. Um *ativo* é qualquer tipo de equipamento, como uma máquina ou parte da máquina, que exige manutenção, serviço ou reparo.

Um ativo é atualizado automaticamente com informações relacionadas. Por exemplo, essas informações relacionadas podem ser relativas a ordens de serviço novas ou atualizadas. Você pode criar ativos usando o item de menu **Todos os ativos** ou o item de menu **Ativos pendentes**. Este tópico explica como criar ativos usando o item de menu **Todos os ativos**. Para obter informações sobre como criar ativos usando o item de menu **Ativos pendentes**, consulte [Criar ativos com base em ordens de compra](../objects/create-objects-based-on-purchase-orders.md).

## <a name="all-assets"></a>Todos os ativos

Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos**. A página de lista **Todos os ativos** mostra todos os ativos e algumas informações relacionadas a eles. Para exibir somente ativos que estão ativos, selecione **Ativos ativos**. Para exibir somente ativos que estão instalados em locais funcionais aos quais você está relacionado como um trabalhador de manutenção, selecione **Meus ativos ativos**. (Essa relação é configurada na página **Trabalhadores**. Para obter mais informações, consulte [Trabalhadores de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md).)

Na exibição de grade **Todos os ativos**, selecione um link na coluna **Ativo** para exibir os detalhes do registro selecionado. Para editar o registro, selecione o botão **Editar**. A exibição de detalhes mostra informações detalhadas relacionadas ao ativo. Um painel **Informações relacionadas** à direita contém informações adicionais relativas ao ativo. Expanda o painel para mostrar as informações relacionadas para o ativo selecionado.

Os botões no Painel de Ação estão organizados em guias. A tabela a seguir descreve brevemente os botões relacionados ao Asset Management.

| Nome do botão          | Descrição                                                                                                                                                       |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Edição                 | Edite o ativo selecionado.                                                                                                                                         |
| Novos                  | Crie um novo ativo.                                                                                                                                                |
| Excluir               | Exclua o ativo selecionado.                                                                                                                                       |
| Mover ativo           | Mova ativos para outra estrutura de ativos ou para outro local na mesma estrutura de ativos.                                                                                         |
| Substituir ativo        | Substitua um ativo filho em uma hierarquia de ativos por outro outro.                                                                                                  |
| Instalar ativo        | Instale um ativo em um local funcional.                                                                                                                          |
| Copiar ativo           | Copie uma hierarquia de ativos em outro ativo.                                                                                                                          |
| Solicitações             | Abra a página de lista **Solicitações de ativos**, em que você pode exibir solicitações de manutenção que foram criadas para o ativo selecionado.                                                                         |
| Histórico de eventos        | Exiba uma visão geral de vários registros feitos no ativo.                                                                                                         |
| BOM de ativos            | Exiba uma lista de todos os itens (peças sobressalentes e itens) usados em um ativo.                                                                                  |
| Ordens de serviço          | Abra a página de lista **Ordens de serviço ativas**, em que você pode exibir ordens de serviço para o ativo.                                                                                        |
| Lista de Verificação            | Exiba uma visão geral das listas de verificação de manutenção e medidas que foram registradas no ativo.                                                                                                 |
| Tempo de inatividade de manutenção | Crie ou exiba registros de tempo de inatividade de manutenção no ativo.                                                                                                       |
| Transações do Projeto | Exiba todas as transações lançadas relativas a ordens de trabalho que foram criadas para o ativo.                                                                                       |
| Medidas de ativos       | Crie ou exiba medidas de ativo no ativo.                                                                                                               |
| Agendamento de manutenção | Abra a página de lista **Agenda de manutenção aberta**, em que você pode exibir planos de manutenção, solicitações de manutenção e rounds de manutenção que estão associados ao ativo e que têm o status **Criado**. |
| Atualizar estado do ativo   | Atualize o estado de ciclo de vida do ativo. Você pode selecionar vários ativos na página **Todos os ativos** e atualizar o estado do ciclo de vida do ativo para todos ao mesmo tempo.              |
| Log de estados de ciclo de vida  | Abra um log que mostre os estados de ciclo de vida do ativo selecionado.                                                                                                                 |
| Documentos do ativo      | Exibir uma lista dos documentos anexados a um ativo. Esses documentos são configurados em **Gerenciamento de ativos** \> **Configuração** \> **Documentos de ativo**.                 |
| Atributos           | Crie ou exiba atributos de ativo.                                                                                                                             |
| Imagem                | Selecione imagem para o ativo.                                                                                                                                   |
| Ativos pai        | Exiba o histórico do ativo pai para o ativo selecionado.                                                                                                                |
| Locais funcionais | Exiba o histórico do local funcional para o ativo selecionado.                                                                                                          |
| Avaliação de condição | Registre medidas de avaliação de condição no ativo.                                                                                                         |
| Falhas               | Abra a página de lista **Falhas de ativo**, em que você pode exibir falhas que foram registradas no ativo.                                                                                             |
| Controle de Custo         | Compare custos reais e de orçamento no ativo.                                                                                                              |
| Controle de horas         | Compare horas previstas e horas reais no ativo.                                                                                                              |
| KPIs do ativo           | Calcule e exiba indicadores chave de desempenho (KPIs) para o ativo.                                                                                              |
| Tipos de trabalho            | Exiba uma visão geral dos tipos padrão de trabalho atuais para o ativo.                                                                                                            |
| Tipos de severidade    | Exiba ou atualize tipos de severidade do ativo.                                                                                                                              |
| Peças sobressalentes          | Exiba uma lista de peças sobressalentes aprovadas e alternativas que podem ser usadas no ativo.                                                                               |
| Consumo de ativos    | Imprima um relatório que mostre os registros de consumo no ativo.                                                                                                |
| Falha do ativo          | Imprima um relatório que mostre os registros com falha no ativo.                                                                                                      |
