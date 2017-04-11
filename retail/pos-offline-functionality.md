---
title: Recursos offline do POS
description: "Este artigo fornece informações sobre o modo offline de Retail Modern POS, no qual dispositivos de POS trocam automaticamente do canal da base de dados para base de dados offline se o servidor do Retail estiver indisponível. Este artigo também inclui informações de configuração geral para o modo offline e explica a sincronização de dados que ocorre entre a base de dados offline e a base de dados do canal."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27041
ms.assetid: 20b51874-8912-40cf-9296-864df707315a
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ef4d20b3302e4a420c7013b77a57ebdfa99fe6a3
ms.lasthandoff: 03/31/2017


---

# <a name="pos-offline-functionality"></a>Recursos offline do POS

Este artigo fornece informações sobre o modo offline de Retail Modern POS, no qual dispositivos de POS trocam automaticamente do canal da base de dados para base de dados offline se o servidor do Retail estiver indisponível. Este artigo também inclui informações de configuração geral para o modo offline e explica a sincronização de dados que ocorre entre a base de dados offline e a base de dados do canal.

<a name="overview"></a>Visão Geral
--------

Em O retail moderno varejo, um dispositivo (POS) do ponto de venda insira o modo offline sempre que o servidor de varejo não está disponível. Portanto, se a conexão com o servidor de varejo é perdida, retail POS modernos alternância automaticamente o base de dados offline. Durante uma transação de venda, se uma solicitação de dados não tiver êxito no intervalo de tempo configurado no perfil offline, o Retail Modern POS alterna automaticamente para o banco de dados offline e continua a transação de venda. Enquanto o dispositivo POS estiver no modo offline, o Retail Modern POS tenta se reconectar com o servidor de varejo após o intervalo de tentativa de reconexão configurado no perfil offline. Esta tentativa de reconexão ocorre somente no início de uma transação.

### <a name="determining-the-connection-mode-of-retail-modern-pos"></a>Determinando o modo de conexão do Retail Modern POS

O cabeçalho de status no Retail Modern POS indica o status de conexão atual, e a janela **Status de conexão** exibe o status da última tentativa de sincronizar com o banco de dados offline. [![Connection status](./media/status.png)](./media/status.png)

### <a name="creating-a-button-to-manually-switch-between-online-and-offline-modes"></a>Criando um botão para alternar manualmente entre os modos online e offline

Você pode adicionar um botão ao Retail Modern POS para alternar manualmente entre os modos online e offline. Crie um botão para a operação de POS **917 – Status de conexão do banco de dados**. O nome deste botão passa a ser **Desconectar** quando o Retail Modern POS está conectado ao servidor de varejo, e **Conectar** quando está desconectado. Você pode usar este botão para exibir a conexão, e para desconectar-se do servidor de varejo ou conectar-se a ele. [botão desconexão![em moderno de POS (]. /media/details-1024x537.png)](. /media/details.png)

## <a name="setup"></a>Configurar
Para habilitar o suporte offline de um dispositivo POS (registro), definir Sim ** suporte offline ** padrão ** ** ** registro ** na página. Uma nova entidade base de dados de canal é criada e adicionada ao grupo dos dados de canal de armazenamento. Em seguida, execute todos os planos de distribuição necessários para gerar os pacotes de dados do banco de dados offline. Em seguida, instala a versão offline POS POS. moderno O processo de instalação cria o base de dados offline. Adicionalmente, instalação Microsoft SQL Server 2014 expresso se necessário. A sincronização de dados offline começa após o primeiro logon no Retail Modern POS.

## <a name="data-synchronization"></a>Sincronização de dados
O agendador do Retail é usado para enviar dados mestre ao banco de dados offline. Por padrão, quando um plano de distribuição é executada, as alterações nos dados são enviadas ao banco de dados de canal e ao banco de dados offline. O Retail Modern POS inclui a biblioteca de sincronização do async, que baixa todos os pacotes de dados disponíveis e os insere no banco de dados offline. Se alguma transação offline for criada, o Retail Modern POS a carregará no servidor de varejo, de modo que possa ser inserida no banco de dados do canal. A sincronização offline de dados pode ocorrer somente se o Retail Modern POS estiver sendo executado. [![Offline synchronization](./media/offline-sync-1024x521.png)](./media/offline-sync.png)


