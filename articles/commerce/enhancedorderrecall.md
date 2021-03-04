---
title: Cancelar operação de ordem no PDV
description: Este tópico explica recursos disponíveis para aprimorar as páginas de cancelamento de ordens no PDV.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 42b11ff16757d633b868dfdf248341193a44378f
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665289"
---
# <a name="recall-order-operation-in-pos"></a>Cancelar operação de ordem no PDV

[!include [banner](includes/banner.md)]

A operação **Cancelar ordem** no ponto de venda (PDV) do Commerce oferece recursos atualizados de pesquisa e filtragem de ordens e informações específicas da ordem. Este recurso está disponível nas versões 10.0.15 e posterior do Commerce.

Para habilitar essa funcionalidade, ative a **Operação Cancelar ordem aprimorada no PDV** no espaço de trabalho **Gerenciamento de recursos** do Commerce Headquarters. Depois de habilitar o recurso, será recomendável atualizar os [layouts de tela](pos-screen-layouts.md) no PDV para aproveitar alguns dos recursos alterados.

A configuração do botão da operação **Cancelar ordem** permite que as organizações implantem a operação com uma exibição predefinida.

![Configuração da grade de botões](media/recallorderbuttongrid.png)

As opções de vídeo são as seguintes.
- **Nenhum** – essa opção implanta a operação sem nenhum vídeo específico. Quando um usuário abre a operação com essa configuração, ele será solicitado a procurar e encontrar ordens ou escolher um filtro de ordem predefinido.
- **Ordens a serem atendidas** – quando um usuário inicia a operação, uma consulta será executada automaticamente para pesquisar e exibir uma lista de ordens a serem atendidas pela loja. Essas ordens são configuradas para remessa de armazenamento ou entrega em armazenamento, e as linhas dessas ordens ainda não foram retiradas nem empacotadas.
- **Ordens a serem retiradas** – quando um usuário inicia a operação, uma consulta será executada automaticamente para pesquisar e exibir uma lista de ordens a serem configuradas para retira na loja atual do usuário.
- **Ordens a serem remetidas** – quando um usuário inicia a operação, uma consulta será executada automaticamente para pesquisar e exibir uma lista de ordens a serem configuradas para remessa da loja atual do usuário.

Ao iniciar a operação **Cancelar ordem** no PDV, se o vídeo estiver configurado como **Nenhum**, um usuário poderá pesquisar e recuperar ordens de uma das seguintes maneiras.
- Pesquisar códigos de barras da ordem. Isso pesquisará os campos número da ordem, referência do canal e ID do recibo para conciliações.
- Selecione o ícone de **Pesquisar ordens** ou **Pesquisar e filtrar** na AppBar para usar o mecanismo de filtragem para localizar ordens que atendam aos critérios do filtro.
- Escolha em um filtro predefinido do menu suspenso **Mostrar Ordens** (ordens a serem atendidas, ordens a serem retiradas ou ordens a serem remetidas).

![RecallOrderMainMenu](media/recallordermain.png)

Depois que os critérios de pesquisa forem aplicados, o aplicativo exibirá uma lista de ordens de venda conciliadas.

![RecallOrderDetail](media/orderrecalldetail.png)

Um usuário pode selecionar uma ordem na lista para exibir detalhes adicionais. O painel de informações, no lado direito da tela, exibe especificações sobre a ordem selecionada, incluindo detalhes da linha da ordem, detalhes de entrega e detalhes de preenchimento.

Da AppBar, um usuário pode selecionar uma operação. Dependendo do status da ordem, determinadas operações podem não estar habilitadas.

- **Devolução** – executa uma devolução para uma ou mais faturas relacionadas à ordem do cliente selecionada.

- **Cancelar** – emita um cancelamento completo da ordem de venda selecionada.

- **Atender** – transfere o usuário para a página atendimento de ordem, que será filtrada previamente para a ordem selecionada. Somente as linhas de ordem que estão abertas para preenchimento pela loja do usuário para a ordem selecionada serão exibidas.

- **Editar** – permite que os usuários façam alterações na ordem de cliente selecionada.

- **Retirada** – lança o fluxo de retirada, que permite que o usuário escolha os produtos a serem retirados e cria a transação de venda de retirada.


[!INCLUDE[footer-include](../includes/footer-banner.md)]