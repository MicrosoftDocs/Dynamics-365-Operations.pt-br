---
title: Visão geral da solução Invoice capture
description: Este artigo fornece informações sobre a solução Invoice capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76441220b93744527f412110db536601a2fa1dd9
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691126"
---
# <a name="invoice-capture-solution"></a>Solução Invoice capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo fornece informações sobre a solução Invoice capture que cria automaticamente faturas do fornecedor a partir de imagens de fatura digital.

O departamento de Contas a pagar (AP) gerencia e processa as faturas de bens e serviços recebidos. O contador de AP verifica os dados nas faturas do fornecedor pelos seguintes motivos:

- Para evitar esforço extra, se forem necessários ajustes ou correções durante o fechamento do período
- Para pagar faturas de fornecedor a tempo e evitar perda financeira devido a erro ou fraude

O OCR (reconhecimento óptico de caracteres) tem sido amplamente usado por setores diferentes nos últimos anos. Agora, é comum que textos impressos sejam digitalizados, para que possam ser editados eletronicamente, pesquisados, armazenados com de forma mais compacta e exibidos online. O texto digital pode ser usado em processos de máquina como computação cognitiva, tradução automática, conversão de texto em fala, dados essenciais e mineração de texto.

A evolução da tecnologia de inteligência artificial (AI) ativou as soluções de OCR modernas para ler diferentes formatos de faturas de fornecedores diferentes sem exigir muita intervenção humana. Mais empresas estão reconhecendo que podem economizar esforços e melhorar a precisão ao processar faturas por meio de automação, em vez de executar processamento manual.

## <a name="system-landscape"></a>Cenário do sistema

A ilustração a seguir mostra os principais componentes e etapas na solução do Invoice Capture.

[![Componentes e etapas na solução do Invoice capture.](./media/Invoice-capture2.png)](./media/Invoice-capture2.png)

## <a name="required-roles"></a>Funções necessárias

A tabela a seguir mostra as funções necessárias para configurar e usar a solução Invoice capture.

| Função          | Ações | Sistemas | Nomes da função |
|---------------|---------|---------|-----------|
| Administrador | <ul><li>Configurar ambientes no Microsoft Power Platform.</li><li>Implantar soluções no Microsoft Power Platform.</li><li>Configurar conexões entre o Dynamics 365 e o AI Builder.</li><li>Configurar localizações do Azure Data Lake Storage.</li></ul> | <ul><li>Dynamics 365</li><li>Microsoft Power Platform</li><li>Azure Data Lake Storage</li></ul> | <ul><li>Administrador do Dynamics 365</li><li>Administrador do Power Platform</li><li>Proprietário de dados do Blob de Armazenamento</li></ul> |
| Criador do IA      | <ul><li>Manter fluxos.</li><li>Criar modelos de IA personalizados.</li></ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Responsáveis pelos cidadãos</li></ul> |
| Auxiliar do AP      | <ul><li>Analise e execute ações na área de preparo da fatura de fornecedor.</li><ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Nova função de auxiliar do AP no Power Platform</li></ul> |
| Auxiliar do AP      | <ul><li>Executar operações diárias como um auxiliar de AP.</li><li>Navegue até a área de preparo da fatura do fornecedor.</li></ul> | <ul><li>Dynamics 365</li></ul> | <ul><li>Auxiliar de contas a pagar</li></ul> |
  
Para obter mais informações sobre como instalar o Invoice capture, consulte [Instalar Invoice capture](../accounts-payable/install-invoice-capture.md).  
